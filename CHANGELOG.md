# Changelog

All notable changes to ALOY will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/) and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

---

## [1.0.0] — 2026-07-01

### 🎉 Initial Public Release

ALOY Version 1.0.0 is the first official public release of the ALOY Advanced Local-First Agentic Operating System.

---

### Added

**Core System**
- Async event bus microkernel with publish/subscribe service orchestration
- Full application lifecycle management (startup, health checks, graceful shutdown)
- SQLite database with WAL mode, connection pooling, and automated migration registry
- `sqlite-vec` vector extension for L2-distance semantic search

**Conversation Engine**
- Real-time SSE streaming with inline cursor animation
- Automatic conversation naming from first user message context
- Branched conversation timelines — navigate and restore any previous state
- Markdown rendering with code syntax highlighting, tables, and math formulas

**Memory System**
- Multi-tier hybrid memory combining vector search and FTS5 full-text indexing
- Reciprocal Rank Fusion (RRF) scoring for optimal memory retrieval
- Memory decay scoring — frequently accessed memories surface higher
- Background contradiction auditing to clean conflicting facts
- Memory tag groups and semantic clustering

**Knowledge Router**
- 6-layer progressive query routing (Episodic Memory → Workspace → Documentation → Web Search)
- Freshness detection — automatically identifies when live data is required
- DuckDuckGo live web search integration
- Search result synthesis with inline citations and source metadata

**Reasoning Engine**
- Multi-stage reasoning (Draft → Refine → Verify)
- Real-time reasoning console — visible thought steps as they execute
- Confidence scoring and hallucination mitigation

**Agent Runtime Grid**
- Multi-agent FSM grid with roles: Planner, Coder, Tester, Debugger, Documenter
- Git state checkpointing before every destructive agent action
- One-click rollback to any checkpoint
- Autonomous debug loop — agents retry failed tests up to the configured limit
- Structured step planning with JSON output validation

**Tool Sandbox**
- Boundary-checked file editor (absolute path resolution, workspace isolation)
- Terminal shell executor with allowlist validation
- Python runner with timeout and output capture
- Git tool with checkpoint integration
- Docker control (start, stop, build, exec)
- Web search tool, browser tool, PDF reader, image reader, SQLite tool

**Security System**
- Explicit user authorization gates for all high-risk operations
- Event bus freeze during pending confirmations (prevents concurrent execution)
- Prompt injection defense — `PromptIntegrityFilter` strips leaking XML tags from streams
- Capability check filters on all API endpoints

**Identity Engine**
- Creator profile and ALOY identity profile seeded on first boot
- User profile onboarding wizard (name, preferences, greeting)
- Profile export/export JSON for cross-machine migration

**UI/UX**
- Three themes: Dark, Light, OLED (pure black)
- Live hardware telemetry sidebar (CPU, RAM, GPU, VRAM, disk)
- Dependency overlay on startup — detects missing Ollama/models and guides installation
- Crash recovery overlay with conversation restore
- Premium typography using Outfit and Inter font families

**Packaging**
- Windows installer (`ALOY-Setup-1.0.0.exe`) built with PyInstaller + Inno Setup
- Desktop and Start Menu shortcuts
- Add/Remove Programs uninstall entry
- Custom EULA shown and accepted at install time
- No internet required after Ollama and models are installed

---

## What's Next

See [docs/roadmap.md](docs/roadmap.md) for future release plans.
