# Release Notes — ALOY v1.0.0

**Release Date:** July 15, 2026  
**Download:** [GitHub Releases](https://github.com/dhanush708/aloy/releases/tag/v1.0.0)

---

## 🎉 ALOY Version 1.0.0 — First Public Release

This is the first official public release of **ALOY: Advanced Local-First Agentic Operating System**.

ALOY was designed, architected, engineered, implemented, tested, documented, packaged, and released end-to-end by **Dhanush A.** as an independent software engineering project.

---

## What's Included

### Core System
- Async event bus microkernel with full service lifecycle management.
- SQLite database with WAL mode, connection pooling, and auto-migration registry.
- `sqlite-vec` vector extension for semantic memory search.
- Graceful startup and shutdown with health checks and lockfile management.

### Conversation Engine
- Real-time SSE streaming with inline cursor animation.
- Automatic conversation naming from first message context.
- Branched conversation timelines with full history navigation.
- Markdown rendering with syntax-highlighted code blocks, tables, and LaTeX math.

### Memory System
- Multi-tier hybrid memory (vector + FTS5 full-text search).
- Reciprocal Rank Fusion (RRF) scoring for combined memory retrieval.
- Background contradiction auditing and memory consolidation.
- Memory decay scoring with tag groups and semantic clustering.

### Knowledge Router & Search Pipeline
- 6-layer progressive routing: Episodic Memory → Workspace → Documentation Cache → Web Search.
- Semantic search classification — automatically identifies queries requiring live web data.
- Concurrent multi-query scraper — rewrites query variations and executes them in parallel (using DDG scraping), resolving in under 2 seconds.
- Multi-factor source ranker scoring domain authority, temporal freshness, relevance, and applying a +15 points official source bonus.
- Query broadening retries on empty search results.
- Topic drift classification to maintain continuity across follow-up queries without redundant searches.

### Reasoning Engine
- Multi-stage reasoning pipeline: Draft → Refine → Verify.
- Real-time visible reasoning console with step-by-step thought output.
- Hallucination mitigation through evidence injection and strict source verification.

### Agent Runtime Grid
- Multi-agent FSM grid: Planner, Coder, Tester, Debugger, Documenter.
- Parallel task scheduler executing up to 4 concurrent worker tasks on a dynamic dependency graph.
- Git state checkpointing before destructive agent actions with one-click surgical rollback.
- Autonomous debug loop with configurable retry limits.

### Tool Sandbox
- Boundary-checked file editor with workspace isolation.
- Terminal shell executor with allowlist validation.
- Python code runner with timeout and output capture.
- Git tool with checkpoint integration.
- Docker control, web search, browser, PDF reader, SQLite tool.
- Explicit user authorization gate for all high-risk operations.

### Identity & Profile System
- Creator profile and ALOY identity seeded on first boot.
- User onboarding wizard with local-only profile storage.
- Profile export and import as JSON.

### User Interface
- Three themes: Dark, Light, OLED (pure black).
- Live hardware telemetry sidebar (CPU, RAM, GPU, VRAM usage).
- Dependency overlay — detects missing Ollama/models and guides installation.
- Crash recovery overlay with full conversation restore.

### Packaging
- Windows installer (`ALOY-Setup-1.0.0.exe`) via PyInstaller + Inno Setup.
- Desktop and Start Menu shortcuts.
- Windows Add/Remove Programs entry.
- Custom EULA acceptance at install time.
- Offline operation after Ollama and models are installed.

---

## System Requirements

- Windows 10 64-bit or higher
- Ollama running locally
- NVIDIA GPU with 8+ GB VRAM recommended (CPU-only supported)

---

## Known Issues in v1.0.0

See [docs/known-limitations.md](known-limitations.md) for the full list.

---

## Upgrade Notes

This is the first release. No upgrade path from a previous version applies.

---

## Acknowledgements

This release builds on the excellent work of the open-source community. See [THIRD_PARTY_NOTICES.md](../THIRD_PARTY_NOTICES.md) for full attributions.
