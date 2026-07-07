# Roadmap

**ALOY** | [Back to README](../README.md)

This document outlines the planned evolution of ALOY across major version milestones.

---

## ✅ Version 1.0.0 — July 2026 (Released)

The first public release of ALOY. Core AI operating system with full local inference, multi-agent coding, hybrid memory, and Windows packaging.

**Highlights:**
- Event bus microkernel architecture
- Multi-agent FSM grid (Planner, Coder, Tester, Debugger, Documenter)
- Hybrid vector + FTS5 memory with RRF scoring
- 6-layer knowledge router with live web search
- SSE streaming conversation engine
- Dark, Light, and OLED UI themes
- Windows installer (`ALOY-Setup-1.0.0.exe`)

---

## 🔜 Version 1.1 — Q3 2026 (Planned)

Focus: **Developer Experience & Installer Quality**

- **Dynamic Tool Plugins**: Allow workspace directories to define their own custom tools loaded at runtime
- **Smaller Installer**: Rebuild packaging pipeline with a dedicated virtualenv to exclude unused Python packages and significantly reduce installer size
- **Screenshot Gallery**: Add real UI screenshots to the public repository
- **Model Configuration UI**: Easier in-app model management (add, remove, test models)
- **Memory Export**: Export/import full memory snapshots as JSON for backup and migration
- **Improved Web Search**: Multiple search provider support (Bing, Google via SerpAPI)

---

## 🔭 Version 2.0 — Q1 2027 (Planned)

Focus: **Collaborative Multi-Agent Workspaces**

- **Shared Workspaces**: Multiple agent teams working on split components of a project simultaneously
- **Cross-Session State Sync**: Agents share intermediate state and results across workspace splits
- **Advanced Agent Roles**: Architect, Security Auditor, Performance Profiler
- **macOS Support**: Official packaging and testing for macOS (Apple Silicon and Intel)
- **Plugin Marketplace**: Community-contributed tool plugins

---

## 🚀 Version 3.0 — Q4 2027 (Vision)

Focus: **Self-Evolving Kernel**

- **Autonomous Prompt Evolution**: The microkernel analyzes its own performance and autonomously refines system prompts to improve response quality
- **Adaptive Model Routing**: The model router learns from past task outcomes and adjusts routing decisions automatically
- **Linux Support**: Official Ubuntu/Debian packaging
- **Embedded Agent API**: Local REST API for third-party integrations

---

## What Drives Prioritization?

- Community bug reports and feature requests
- Creator's engineering judgment on technical feasibility
- User feedback from the v1.0 release

To suggest a feature or vote on roadmap items, open a [Feature Request](https://github.com/dhanush708/aloy/issues/new/choose).

---

## Version History

| Version | Date | Status |
|:---|:---|:---|
| 1.0.0 | July 2026 | ✅ Released |
| 1.1 | Q3 2026 | 🔜 Planned |
| 2.0 | Q1 2027 | 🔭 Planned |
| 3.0 | Q4 2027 | 🚀 Vision |
