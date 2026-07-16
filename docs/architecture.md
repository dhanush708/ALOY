# Architecture Overview

**ALOY v1.0.0** | [Back to README](../README.md)

> This document describes ALOY's high-level architecture. Implementation details of proprietary subsystems are intentionally omitted.
> For full systems specifications and threat model security analysis, refer to the [ALOY Technical Whitepaper](aloy_technical_whitepaper.pdf).

---

## Design Philosophy

ALOY is built around three core design principles:

1. **Local-First**: All computation, storage, and inference happen on your device. No cloud dependency.
2. **Microkernel Architecture**: A central event bus decouples all subsystems, enabling modular and testable components.
3. **Privacy by Default**: No telemetry, no data collection, no external API calls (except optional privacy-respecting web search).

---

## High-Level System Map

```
┌─────────────────────────────────────────────────────────┐
│                        Browser UI                        │
│         (Vanilla JS SPA — Dark / Light / OLED)          │
└────────────────────────┬────────────────────────────────┘
                         │ HTTP + SSE
┌────────────────────────▼────────────────────────────────┐
│                    FastAPI Server                        │
│              (Async ASGI — Uvicorn)                      │
└────────────────────────┬────────────────────────────────┘
                         │
┌────────────────────────▼────────────────────────────────┐
│               Event Bus Microkernel                      │
│         (Async publish/subscribe — in-process)           │
└──┬──────────┬──────────┬──────────┬──────────┬──────────┘
   │          │          │          │          │
   ▼          ▼          ▼          ▼          ▼
Identity   Memory    Knowledge   Model     Security
Engine    Manager    Router     Router    Subsystem
            (Hybrid   (6-layer   (Task→    (Confirm-
            Vec+FTS5)  routing)   Model)    ation)
                         │          │
                         ▼          ▼
                     Web Search   Ollama
                     (Local       (Local)
                     Scraper)       │
                                    │
                               AI Models:
                           qwen3 / qwen2.5-coder /
                           deepseek-r1 / nomic-embed
```

---

## Request Lifecycle

A typical user message flows through the following stages:

```
1. User types a message and presses Send
         │
2. Browser sends POST /api/chat/stream (SSE)
         │
3. FastAPI routes to Conversation Engine
         │
4. Event Bus publishes "message.received"
         │
5. ┌─────────────────────────────────────┐
   │ Parallel subsystem invocations:     │
   │  • Identity Engine (profile check)  │
   │  • Memory Manager (hybrid search)   │
   │  • Knowledge Router (routing logic) │
   └─────────────────────────────────────┘
         │
6. Knowledge Router decides:
   ├── Use local memory? → inject context
   ├── Use workspace files? → inject content
   ├── Use docs cache? → inject docs
   └── Requires live web? → Launch Search Pipeline
         │
7. Search Pipeline executes:
   ├── Semantic Search Classification Check
   ├── Query Rewriting (2-3 keyword variations)
   ├── Parallel Search (DDG HTML scraping)
   ├── Multi-Factor Scoring (Domain, Freshness, Relevance)
   └── Retry Broadening (reformulate query if empty)
         │
8. Model Router selects the target model:
   ├── qwen3:14b — chat and dialogue
   ├── deepseek-r1:14b — logical reasoning and planning
   ├── qwen2.5-coder:14b — code and agents
   └── nomic-embed-text — embeddings only
         │
9. Prompt is assembled and sent to Ollama
         │
10. Response tokens stream back via SSE
         │
11. Prompt Integrity Filter scans stream
    (strips any leaking internal XML tags)
         │
12. Browser renders Markdown in real-time
```

---

## Agent Grid Architecture

When ALOY receives an autonomous goal, it activates the Agent Grid:

```
Goal Received
     │
     ▼
 PLANNER Agent
 (Decomposes goal → structured step JSON)
     │
     ▼
 CODER Agent
 (Writes code files via sandboxed tool executor)
     │
     ▼
 TESTER Agent
 (Generates and runs pytest cases)
     │
  ┌──┴──┐
  │     │
PASS   FAIL
  │     │
  │     ▼
  │  DEBUGGER Agent
  │  (Reads error → patches code)
  │     │
  │     └──► CODER (retry)
  │
  ▼
DOCUMENTER Agent
(Generates docstrings and documentation)
     │
     ▼
 COMPLETED
 (Git checkpoint saved, results returned)
```

All agent actions that modify files or run commands require explicit user approval via the Authorization Gate before execution.

---

## Memory Architecture

ALOY's hybrid memory system combines two complementary search technologies:

| Layer | Technology | Strength |
|:---|:---|:---|
| **Semantic Search** | sqlite-vec (L2 vector distance) | Finds conceptually similar memories |
| **Keyword Search** | SQLite FTS5 | Finds exact term matches |
| **Fusion** | Reciprocal Rank Fusion (RRF) | Combines both for optimal results |

Memory entries decay over time if not accessed, and the system runs background audits to detect and resolve contradictions between memories.

---

## Technology Stack

| Layer | Technology |
|:---|:---|
| Frontend | Vanilla JavaScript SPA, HTML5, CSS3 |
| Backend | Python 3.11, FastAPI, Uvicorn (ASGI) |
| Database | SQLite 3 (WAL mode), sqlite-vec, FTS5 |
| AI Inference | Ollama (local model server) |
| Packaging | PyInstaller + Inno Setup |

---

## Security Architecture

| Control | Implementation |
|:---|:---|
| **Tool Isolation** | All file paths resolved to absolute; workspace boundary enforced |
| **Authorization Gates** | Event bus freezes pending user confirmation click |
| **Prompt Integrity** | Stream scanner strips leaking `<identity>` / `<system>` XML tags |
| **Local-Only** | Zero external API calls except optional privacy-respecting web search |
