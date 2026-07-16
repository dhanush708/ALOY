# Release Notes — ALOY Version 1.0

This document outlines the major features, architectural highlights, performance optimizations, validation results, known limitations, and roadmap for the official **ALOY Version 1.0** production release.

---

## 🌟 Major Features

1. **Async Event Bus Microkernel**:
   A reactive, publish/subscribe core system executing decoupling services concurrently for memory retrieval, security checking, and agent coordination.
2. **Autonomous Multi-Agent FSM Grid**:
   Coordinating specialized agent state machines:
   - **Planner**: Decomposes goals into checklist steps.
   - **Coder**: Implements code modifications.
   - **Tester**: Executes unit tests in Python/pytest.
   - **Debugger**: Performs automated loop refactoring on failure.
   - **Documenter**: Updates docstrings and documentations.
   - **Learner**: Persists lessons learned from debugging.
3. **Multi-Tier Hybrid Memory**:
   L2 cosine similarity vector search (`sqlite-vec`) fused with exact keyword indices (SQLite FTS5) using Reciprocal Rank Fusion (RRF) scoring:
   $$\text{RRF Score} = \frac{1}{60 + \text{Rank}_{\text{FTS}}} + \frac{1}{60 + \text{Rank}_{\text{Vector}}}$$
4. **6-Layer Progressive Knowledge Router**:
   Escalates query resolution logically: Episodic Memory → Workspace Files → Documentation Cache → Semantic Web Search.
5. **Secure Execution Sandbox**:
   Workspace directory boundary enforcement preventing unauthorized filesystem traversal, guarded by explicit user authorization prompts for all terminal/Docker tools.

---

## 🚀 Major Improvements & Performance

- **Semantic Search Gating**: Cached Git and GPU hardware properties, reducing subsequent health check calls to **< 5ms**.
- **Asynchronous Internet Verification**: Pings external networks in the background to prevent blocking UI rendering.
- **Concurrent DuckDuckGo Scraper**: Rewrites search variations and executes queries in parallel, returning consolidated data in **under 2 seconds**.
- **Query Broadening Retries**: Automatically broadens search criteria up to 3 times on empty web search returns.
- **Topic Drift Detection**: Automatically maps context for follow-up conversational queries without triggering redundant search calls.
- **VRAM / GPU Acceleration Check**: Automatic startup checks mapping models safely to available hardware limits.

---

## 🧪 Validation Results

- **Automated Tests**: **531 passing pytest cases** covering microkernel, events, agents, memory, and database layers.
- **Clean Machine Simulation**: Validated database generation (WAL mode), SQLite vector migrations, and browser auto-launch on Windows 11 target machines without development tools or Python environments.
- **Shutdown verification**: Verified graceful `SIGBREAK` (console close) and `SIGTERM` cleanup, successfully deleting the local `running.tmp` lockfile.

---

## ⚠️ Known Limitations

- **Platform Target**: Desktop executable currently targets Windows 10/11 environments only.
- **VRAM Requirements**: 14B model variants require 8+ GB VRAM. VRAM-constrained machines must use smaller parameters (e.g. 7B) mapped via settings.
- **Workspace Lock**: Active agent sessions lock the workspace to a single goal at a time to prevent file conflicts.

---

## 🗺️ Future Roadmap

- **v1.1**: Dynamic tool plugins, smaller installer bundles, and memory JSON export/import UI.
- **v1.2**: Collaborative split-workspace agent grids and cross-session state sync.
- **v1.5**: Autonomous prompt compilation and adaptive model routing algorithms.
