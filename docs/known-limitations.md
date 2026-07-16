# Known Limitations — ALOY v1.0.0

**ALOY v1.0.0** | [Back to README](../README.md)

This document lists known limitations, constraints, and boundaries in the v1.0.0 release. These are not bugs — they are acknowledged design constraints or planned improvements for future versions.

---

## Platform Support

| Limitation | Details | Planned Improvement |
| :--- | :--- | :--- |
| **Windows only (installer)** | The `ALOY-Setup-1.0.0.exe` installer targets Windows 10/11 only. | macOS and Linux support planned for future releases |
| **Installer size** | The installer bundles the entire Python environment, making it larger than ideal. | Size optimizations planned for future updates |

---

## AI Model Constraints

| Limitation | Details | Notes |
| :--- | :--- | :--- |
| **Ollama required** | ALOY cannot function without Ollama installed and running. | By design — all inference is local |
| **VRAM requirements** | Large models (14B parameter size) require 8+ GB VRAM. | Use smaller model variants (e.g. 7B parameters) if VRAM-constrained |
| **Cold start latency** | The first inference request after loading a model can take 10–30 seconds (model warm-up). | Expected behavior from Ollama |
| **Context window limits** | Long conversations may be truncated if they exceed the model's context window. | The system compresses older history to fit; this may affect continuity |
| **Training cutoff** | Local models have a training knowledge cutoff date. ALOY uses web search to supplement recent knowledge, but this depends on network availability. | Use the knowledge router's web search for recent topics |

---

## Memory System

| Limitation | Details | Notes |
| :--- | :--- | :--- |
| **Memory database growth** | The `data/aloy.db` database grows as memories accumulate. It does not auto-prune. | Manual memory management available in Settings |
| **Vector search approximation** | Semantic memory search uses L2 distance approximation — not always exact. | High-quality results in practice; exact recall not guaranteed |

---

## Agent Grid

| Limitation | Details | Notes |
| :--- | :--- | :--- |
| **Agent loop limits** | Agents stop retrying after the configured maximum attempts, even if the task is not complete. | Avoids infinite loops; you can re-trigger manually |
| **Single-session workspace locks** | While tasks within an active session run in parallel (up to 4 concurrent worker tasks), the workspace is locked to a single active session goal. | Multi-goal session concurrency is planned for future updates |
| **Docker tool requires Docker Desktop** | The Docker tool requires Docker Desktop to be installed separately. | Not installed with ALOY |

---

## Web Search

| Limitation | Details | Notes |
| :--- | :--- | :--- |
| **DuckDuckGo HTML Scraping only** | Live web search uses DuckDuckGo HTML scraping. Results depend on search indexing. | Multiple search providers planned for future updates |
| **Rate limiting** | Heavy web search usage may be rate-limited by search engines. | Use web search for genuinely time-sensitive queries only |

---

## User Interface

| Limitation | Details | Notes |
| :--- | :--- | :--- |
| **Browser-based UI** | ALOY runs in your default browser. It is not a native desktop application. | By design — enables rich Markdown and SSE streaming |
| **Single user only** | ALOY is designed for single-user, single-machine use. Multi-user setups are not supported. | By design |

---

## Reporting New Issues

If you encounter something not listed here, please [open a bug report](https://github.com/dhanush708/aloy/issues/new/choose).
