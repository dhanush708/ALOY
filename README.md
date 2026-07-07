<div align="center">

# ALOY

### Advanced Local-First Agentic Operating System

*Your AI companion that runs entirely on your machine.*

[![Version](https://img.shields.io/badge/Version-1.0.0-informational.svg?style=for-the-badge)](https://github.com/dhanush708/aloy/releases)
[![Platform](https://img.shields.io/badge/Platform-Windows%2010%2B-blue.svg?style=for-the-badge&logo=windows&logoColor=white)](https://github.com/dhanush708/aloy/releases)
[![License](https://img.shields.io/badge/License-Proprietary%20EULA-red.svg?style=for-the-badge)](LICENSE)
[![Ollama](https://img.shields.io/badge/Requires-Ollama-orange.svg?style=for-the-badge)](https://ollama.com)
[![Python](https://img.shields.io/badge/Python-3.11+-blue.svg?style=for-the-badge&logo=python&logoColor=white)](https://python.org)
[![Tests](https://img.shields.io/badge/Tests-233%20Passed-brightgreen.svg?style=for-the-badge&logo=pytest)](https://github.com/dhanush708/aloy)

</div>

<br/>

<div align="center">
  <img src="assets/aloy_banner.png" alt="ALOY — Advanced Local-First Agentic Operating System" width="100%"/>
</div>

<br/>

> **ALOY is a fully offline, privacy-first AI operating system.** It runs entirely on your device — no cloud, no subscriptions, no API keys. It thinks, plans, codes, tests, and learns locally.

---

## 📖 Table of Contents

1. [What is ALOY?](#-what-is-aloy)
2. [Why ALOY?](#-why-aloy)
3. [Key Features](#-key-features)
4. [Architecture Overview](#-architecture-overview)
5. [System Requirements](#-system-requirements)
6. [Download & Install](#-download--install)
7. [First Run Guide](#-first-run-guide)
8. [Screenshots](#-screenshots)
9. [Documentation](#-documentation)
10. [Roadmap](#-roadmap)
11. [Known Limitations](#-known-limitations)
12. [FAQ](#-faq)
13. [Bug Reporting & Support](#-bug-reporting--support)
14. [About the Creator](#-about-the-creator)
15. [Acknowledgements](#-acknowledgements)
16. [License](#-license)

---

## 🌟 What is ALOY?

**ALOY** is a local-first AI operating system — an offline assistant, coding partner, and autonomous multi-agent runtime that operates entirely on your own hardware.

It integrates:

- A **persistent event bus microkernel** that orchestrates all subsystems
- **Multi-tier hybrid memory** combining semantic vector search and full-text indexing
- A **sandboxed tool execution engine** with explicit authorization gates
- An **autonomous multi-agent FSM grid** capable of writing, testing, and debugging software end-to-end

**ALOY does not send anything to the cloud.** Every inference request runs locally through [Ollama](https://ollama.com). Every memory is stored in your local SQLite database. There is no telemetry, no subscription, and no API key required.

---

## 🧩 Why ALOY?

| Principle | What It Means For You |
|:---|:---|
| **Fully Offline** | Everything — models, embeddings, memory, agent execution — runs on your machine. No internet required after setup. |
| **Zero Data Collection** | Your conversations, code, and memories never leave your device. No telemetry. No analytics. No logging to external servers. |
| **Autonomous Agent Grid** | ALOY doesn't just generate code — it spawns a team of agents that write, test, debug, and document software autonomously until the task is done. |
| **Persistent Long-Term Memory** | ALOY remembers across sessions using hybrid vector + full-text memory with decay scoring, contradiction auditing, and background consolidation. |
| **Prompt Integrity** | Stream sanitizers and capability filters prevent system prompts, identity metadata, and internal tags from leaking to the UI. |
| **Premium Experience** | A polished dark/light/OLED interface with live hardware telemetry, real-time streaming, and animated reasoning output. |

---

## 🚀 Key Features

| Subsystem | What It Does |
|:---|:---|
| **Conversation Engine** | Real-time SSE streaming with inline cursor, automatic conversation naming, and branched history navigation |
| **Memory System** | Multi-tier vector + FTS5 search with Reciprocal Rank Fusion scoring, memory decay, tag groups, and background contradiction audits |
| **Reasoning Engine** | Multi-stage thought execution (Draft → Refine → Verify) with visible real-time reasoning console |
| **Knowledge Router** | 6-layer progressive routing (Episodic Memory → Workspace → Documentation → Live Web Search) to minimize hallucinations |
| **Agent Runtime Grid** | Planner, Coder, Tester, Debugger, and Documenter agents with Git state checkpointing and full rollback |
| **Tool Sandbox** | Boundary-checked file editors, terminal shells, Docker control, and Python runners — all gated by explicit user confirmation |
| **Premium UI/UX** | Dark, Light, and OLED themes with Outfit/Inter typography, live CPU/GPU/RAM gauges, and responsive panels |

---

## 🏗️ Architecture Overview

ALOY is structured around a **microkernel event bus** that decouples all subsystems. Every user message triggers a fully auditable pipeline:

```
User Message
     │
     ▼
 Event Bus (Async Microkernel)
     │
     ├──► Identity Engine      (user + creator profile resolution)
     ├──► Memory Manager       (hybrid vector + FTS5 retrieval)
     ├──► Knowledge Router     (6-layer query routing + web search)
     ├──► Model Router         (task-to-model assignment)
     │
     ▼
 Local Ollama Model (Phi-4 / Qwen2.5-Coder / nomic-embed-text)
     │
     ▼
 Prompt Integrity Filter       (stream sanitization)
     │
     ▼
 SSE Streaming Response        (Markdown rendered in browser)
```

**Agent Grid FSM Execution:**

```
IDLE → PLANNING → EXECUTING → TESTING → DEBUGGING → COMPLETED
                    │                        │
                    └──── ROLLED_BACK ◄──────┘
                          (auto re-plan from last checkpoint)
```

> For a detailed architecture document, see [docs/architecture.md](docs/architecture.md).

---

## 💻 System Requirements

| Requirement | Minimum | Recommended |
|:---|:---|:---|
| **Operating System** | Windows 10 (64-bit) | Windows 11 (64-bit) |
| **RAM** | 8 GB | 16 GB or more |
| **GPU** | CPU-only (slow) | NVIDIA GPU with 6+ GB VRAM |
| **Storage** | 5 GB free | 20 GB free (for models) |
| **Ollama** | Required | Latest version |
| **Python** | Not required (installer) | 3.11+ (source only) |

> [!IMPORTANT]
> ALOY requires [Ollama](https://ollama.com) to be installed and running before launch. ALOY will guide you through pulling the required models on first launch if they are not already installed.

---

## ⬇️ Download & Install

### Step 1 — Download Ollama

Download and install Ollama from [ollama.com](https://ollama.com). Run it and confirm it is active.

### Step 2 — Download ALOY

Go to the **[Releases](https://github.com/dhanush708/aloy/releases)** page and download the latest installer:

```
ALOY-Setup-1.0.0.exe
```

### Step 3 — Run the Installer

Double-click `ALOY-Setup-1.0.0.exe`. The installer will:
- Install ALOY to `Program Files\ALOY`
- Create a Desktop shortcut
- Create a Start Menu entry
- Register an uninstaller in Windows Add/Remove Programs

### Step 4 — Launch ALOY

Click the **ALOY** Desktop shortcut. Your browser will open automatically at the ALOY interface. On first launch, ALOY checks for Ollama and required models.

> [!NOTE]
> If you prefer to run from source, see the [Installation Guide](docs/installation.md) for developer setup instructions.

---

## 🚀 First Run Guide

1. **Ensure Ollama is running.** If it is not installed, download it from [ollama.com](https://ollama.com).

2. **Pull the required models** (ALOY will prompt you to do this if needed):
   ```bash
   ollama pull phi4:latest
   ollama pull qwen2.5-coder:7b
   ollama pull nomic-embed-text:latest
   ```

3. **Launch ALOY** via the Desktop shortcut.

4. **Complete the onboarding wizard.** ALOY will display a first-run setup screen where you enter your name and preferences. Everything is stored locally.

> [!NOTE]
> If Ollama is not detected or required models are missing, ALOY displays a dependency overlay with the exact `ollama pull` commands to run — no guesswork required.

---

## 📸 Screenshots

Here are placeholders for the core interfaces and visual panels in ALOY. These placeholder graphics will be replaced with real application screenshots upon the official v1.0.0 release.

### 1. Home Dashboard
![ALOY Home Dashboard](assets/screenshots/01-home.png)

### 2. Conversation & Chat Interface
![ALOY Conversation Interface](assets/screenshots/02-chat.png)

### 3. Multi-Agent Control Grid
![ALOY Agent Control Console](assets/screenshots/03-agent-panel.png)

### 4. Memory Management & Explorer
![ALOY Memory Management](assets/screenshots/04-memory.png)

### 5. System Settings
![ALOY System Settings](assets/screenshots/05-settings.png)

### 6. Knowledge Routing & Web Search
![ALOY Knowledge Routing & Web Search](assets/screenshots/06-search.png)

### 7. Windows Setup Installer Wizard
![ALOY Windows Setup Wizard](assets/screenshots/07-installation.png)

---

## 📚 Documentation

| Document | Description |
|:---|:---|
| [Installation Guide](docs/installation.md) | Full installation instructions for both end users and developers |
| [Architecture Overview](docs/architecture.md) | High-level architecture, subsystem design, and data flow |
| [FAQ](docs/faq.md) | Answers to common questions |
| [Roadmap](docs/roadmap.md) | Planned features and version timeline |
| [Release Notes](docs/release-notes.md) | What's new in each release |
| [Known Limitations](docs/known-limitations.md) | Current known issues and limitations |

---

## 🗺️ Roadmap

| Version | Timeline | Planned Focus |
|:---|:---|:---|
| **v1.0.0** | July 2026 | ✅ **Released** — Core AI OS, agent grid, hybrid memory, Windows installer |
| **v1.1** | Q3 2026 | Dynamic tool plugins; reduced installer size via virtualenv builds |
| **v2.0** | Q1 2027 | Collaborative multi-agent teams with split workspaces and shared state |
| **v3.0** | Q4 2027 | Self-evolving microkernel — autonomously improves its own backend prompts |

See [docs/roadmap.md](docs/roadmap.md) for full details.

---

## ⚠️ Known Limitations

- **Windows Only**: The Windows installer (`ALOY-Setup-1.0.0.exe`) targets Windows 10/11. Linux and macOS developer installations are possible from source but are not officially packaged for v1.0.
- **Ollama Dependency**: ALOY requires Ollama to be running. Without it, no inference is available.
- **VRAM Requirements**: Larger models (e.g. `qwen2.5-coder:7b`) require 8+ GB VRAM. CPU-only inference is supported but significantly slower.
- **Internet Search**: Live web search uses DuckDuckGo's public API. Results may vary in quality or availability based on network conditions.
- **First-Launch Performance**: The first conversation may be slower as models warm up in Ollama.

See [docs/known-limitations.md](docs/known-limitations.md) for the full list.

---

## ❓ FAQ

**Q: Does ALOY send my data anywhere?**
> No. ALOY is completely offline. Your conversations, memories, and code never leave your machine.

**Q: Do I need a GPU?**
> Not strictly. ALOY works with CPU-only Ollama, but responses will be significantly slower. An NVIDIA GPU with 6+ GB VRAM provides a much better experience.

**Q: What models does ALOY use?**
> ALOY uses `phi4:latest` for conversation and reasoning, `qwen2.5-coder:7b` for agent coding tasks, and `nomic-embed-text` for semantic memory embeddings. All are free, open-weight models served locally via Ollama.

**Q: Can I use different models?**
> Yes. Model assignments are configurable via the settings interface and config files.

**Q: Is ALOY open-source?**
> The public release is provided as a compiled installer under a custom proprietary EULA. The source code is not publicly available at this time.

**Q: How do I uninstall ALOY?**
> Use Windows "Add or Remove Programs" — search for ALOY and click Uninstall.

See [docs/faq.md](docs/faq.md) for more questions.

---

## 🐛 Bug Reporting & Support

Found a bug or need help?

1. **Open an issue** → [GitHub Issues](https://github.com/dhanush708/aloy/issues)
   - Use the **Bug Report** template for reproducible bugs
   - Use the **Feature Request** template for suggestions
   - Use the **Question** template for support questions

2. **For private support or commercial licensing inquiries**, contact the creator directly at [anbudhanush31@gmail.com](mailto:anbudhanush31@gmail.com).

When reporting a bug, please include:
- Your Windows version
- ALOY version
- Ollama version
- GPU / VRAM (if applicable)
- Steps to reproduce

> [!CAUTION]
> **Security vulnerabilities** must NOT be reported via public GitHub Issues. Email [anbudhanush31@gmail.com](mailto:anbudhanush31@gmail.com) privately. See [SECURITY.md](SECURITY.md).

---

## 👤 About the Creator

**ALOY Version 1.0** was designed, architected, engineered, implemented, tested, documented, packaged, and released end-to-end by **Dhanush A.** as an independent software engineering project.

<table>
<tr><td><strong>Creator</strong></td><td>Dhanush A.</td></tr>
<tr><td><strong>GitHub</strong></td><td><a href="https://github.com/dhanush708">github.com/dhanush708</a></td></tr>
<tr><td><strong>Contact</strong></td><td><a href="mailto:anbudhanush31@gmail.com">anbudhanush31@gmail.com</a></td></tr>
</table>

*All code, assets, interfaces, documentation, and branding remain the intellectual property of Dhanush A.*

---

## 🤝 Acknowledgements

ALOY is built on the shoulders of the open-source community. Thanks to the creators and maintainers of:

| Project | Purpose |
|:---|:---|
| [Python](https://python.org) | Core runtime |
| [FastAPI](https://fastapi.tiangolo.com) | Web server infrastructure |
| [Ollama](https://ollama.com) | Local LLM serving |
| [SQLite](https://sqlite.org) & [sqlite-vec](https://github.com/asg017/sqlite-vec) | Database and vector search |
| [Marked.js](https://marked.js.org) | Markdown rendering |
| [Mermaid](https://mermaid.js.org) | Architecture diagrams |
| [Pytest](https://pytest.org) | Testing framework |
| [PyInstaller](https://pyinstaller.org) | Windows packaging |

See [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) for full license attributions.

---

## 📄 License

ALOY is proprietary software. All rights reserved.

| Document | Link |
|:---|:---|
| End User License Agreement | [LICENSE](LICENSE) |
| Terms of Use | [TERMS_OF_USE.md](TERMS_OF_USE.md) |
| Privacy Policy | [PRIVACY_POLICY.md](PRIVACY_POLICY.md) |
| Disclaimer | [DISCLAIMER.md](DISCLAIMER.md) |
| Security Policy | [SECURITY.md](SECURITY.md) |
| Third-Party Notices | [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md) |

**Key terms:**
- ✅ Personal and non-commercial use is permitted
- ❌ Redistribution, rebranding, or commercial resale is prohibited
- ✅ Creator attribution must remain intact in all copies

---

<div align="center">

Made with dedication by **[Dhanush A.](https://github.com/dhanush708)**

⭐ If you find ALOY useful, please star this repository!

</div>
