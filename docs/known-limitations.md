# Known Limitations — ALOY v1.0.0

**ALOY v1.0.0** | [Back to README](../README.md)

This document lists known limitations, constraints, and rough edges in the v1.0.0 release. These are not bugs — they are acknowledged design constraints or planned improvements for future versions.

---

## Platform Support

| Limitation | Details | Planned Fix |
|:---|:---|:---|
| **Windows only (installer)** | The `ALOY-Setup-1.0.0.exe` installer targets Windows 10/11 only. | macOS support planned for v2.0; Linux for v3.0 |
| **Installer size** | The installer is larger than ideal because it bundles the entire Python environment. | v1.1 will build with a dedicated virtualenv to significantly reduce size |

---

## AI Model Constraints

| Limitation | Details | Notes |
|:---|:---|:---|
| **Ollama required** | ALOY cannot function without Ollama installed and running. | By design — all inference is local |
| **VRAM requirements** | `qwen2.5-coder:7b` requires 8+ GB VRAM. Lower VRAM machines can only run `phi4:latest`. | Use smaller model variants if VRAM-constrained |
| **Cold start latency** | The first inference request after loading a model can take 10–30 seconds (model warm-up). | Expected behavior from Ollama |
| **Context window limits** | Long conversations may be truncated if the conversation exceeds the model's context window. | The system trims older context to fit; this may affect continuity |
| **Training cutoff** | Local models have a training knowledge cutoff date. ALOY uses web search to supplement recent knowledge, but this depends on network availability. | Use the knowledge router's web search for recent topics |

---

## Memory System

| Limitation | Details | Notes |
|:---|:---|:---|
| **Memory database growth** | The `data/aloy.db` database grows as memories accumulate. It does not auto-prune. | Manual memory management available in Settings |
| **Vector search approximation** | Semantic memory search uses L2 distance approximation — not always exact. | High-quality results in practice; exact recall not guaranteed |

---

## Agent Grid

| Limitation | Details | Notes |
|:---|:---|:---|
| **Agent loop limits** | Agents will stop retrying after the configured maximum attempts, even if the task is not complete. | Avoids infinite loops; you can re-trigger manually |
| **Single-threaded agent execution** | Multiple agent goals cannot run simultaneously in v1.0. | Parallel agent teams planned for v2.0 |
| **Docker tool requires Docker Desktop** | The Docker tool requires Docker Desktop to be installed separately. | Not installed with ALOY |

---

## Web Search

| Limitation | Details | Notes |
|:---|:---|:---|
| **DuckDuckGo only** | Live web search uses DuckDuckGo's public API. Results depend on DDG's search quality. | Multiple search providers planned for v1.1 |
| **Rate limiting** | Heavy web search usage may be rate-limited by DuckDuckGo. | Use web search for genuinely time-sensitive queries only |

---

## User Interface

| Limitation | Details | Notes |
|:---|:---|:---|
| **Browser-based UI** | ALOY runs in your default browser. It is not a native desktop application. | By design — enables rich Markdown and SSE streaming |
| **Single user only** | ALOY is designed for single-user, single-machine use. Multi-user or multi-machine setups are not supported. | By design |

---

## Reporting New Issues

If you encounter something not listed here, please [open a bug report](https://github.com/dhanush708/aloy/issues/new/choose).
