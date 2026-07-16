# Frequently Asked Questions (FAQ)

**ALOY v1.0.0** | [Back to README](../README.md)

---

## Installation & Setup

**Q: What are the minimum system requirements?**
> Windows 10 64-bit, 16 GB RAM, and Ollama installed. A dedicated GPU with 8+ GB VRAM is recommended for a good experience. CPU-only mode works but is significantly slower.

**Q: Do I need Python installed?**
> No — if you use the Windows installer (`ALOY-Setup-1.0.0.exe`). Python is bundled inside the installer. Python is only needed if you're running ALOY from source code.

**Q: Where do I download ALOY?**
> From the [GitHub Releases page](https://github.com/dhanush708/aloy/releases). Download `ALOY-Setup-1.0.0.exe` and run it.

**Q: Why do I need Ollama?**
> ALOY uses Ollama to run AI models locally on your machine. Without Ollama, ALOY cannot perform any AI inference. Download Ollama from [ollama.com](https://ollama.com) — it's free.

**Q: Which models should I pull?**
> Pull these for the full local experience:
> ```bash
> ollama pull qwen3:14b
> ollama pull qwen2.5-coder:14b
> ollama pull deepseek-r1:14b
> ollama pull nomic-embed-text:latest
> ```
> If you are VRAM-constrained, you can pull smaller versions of these models (like `qwen2.5-coder:7b`) and map them in settings.

---

## Privacy & Data

**Q: Does ALOY send my conversations to the internet?**
> No. ALOY is completely offline. Your conversations, code, and memories never leave your machine.

**Q: What data does ALOY collect?**
> None externally. All data is stored in a local SQLite database on your machine. See [PRIVACY_POLICY.md](../PRIVACY_POLICY.md) for full details.

**Q: Does ALOY phone home or check for updates?**
> No. ALOY does not make any automatic network requests. Check the [Releases page](https://github.com/dhanush708/aloy/releases) manually for updates.

---

## Usage

**Q: How do I reset ALOY's memory?**
> Go to **Settings** inside ALOY and use the memory management panel to clear or reset memory entries. You can also delete individual memories.

**Q: How do I change the AI models ALOY uses?**
> Go to **Settings** → **Models**. You can assign different Ollama models to different tasks (chat, coding, embeddings).

**Q: What is the Agent Grid?**
> The Agent Grid is ALOY's autonomous coding system. When you give ALOY a software goal (e.g., "build a FastAPI REST API"), it activates a team of AI agents that plan, write, test, debug, and document code automatically. All actions require your approval before execution.

**Q: How do I use ALOY for coding projects?**
> Open ALOY in your browser, click **New Workspace**, and point it at your project directory. ALOY will index your files and you can ask it coding questions or trigger autonomous agent tasks.

**Q: Can I run ALOY alongside other AI tools?**
> Yes. ALOY runs as a local web server on port 8000. It doesn't interfere with other applications.

---

## Performance

**Q: Responses are very slow. What can I do?**
> - Ensure Ollama is using your GPU (not CPU): run `ollama ps` and check the GPU column.
> - Update your GPU drivers.
> - Use smaller model variants (e.g., `qwen2.5-coder:7b` instead of `qwen2.5-coder:14b`).
> - Close memory-heavy applications to free VRAM.

**Q: My GPU is not being used. How do I fix this?**
> - Ensure you have CUDA-compatible GPU drivers installed.
> - Run `ollama run qwen3:14b` in a terminal and check if Ollama reports GPU acceleration.
> - Check Ollama's documentation for GPU troubleshooting.

---

## Troubleshooting

**Q: ALOY shows "Ollama not detected" on startup.**
> Ollama is not running. Open a terminal and run: `ollama serve`. Then click **Recheck** in ALOY.

**Q: The installer was flagged by Windows Defender.**
> This is a false positive common with PyInstaller-built applications. You can safely allow ALOY if you downloaded it from the official [GitHub Releases](https://github.com/dhanush708/aloy/releases) page. Consider submitting the file to Microsoft for review to help clear the false positive.

**Q: ALOY crashes on startup.**
> - Check that Ollama is running.
> - Ensure you have enough free disk space.
> - Try re-installing ALOY.
> - Report the issue with the crash recovery log (shown in the ALOY interface) at [GitHub Issues](https://github.com/dhanush708/aloy/issues).

**Q: How do I uninstall ALOY?**
> Use Windows **Settings → Apps → Installed Apps**, search for ALOY, and click Uninstall. Your local data in `data/aloy.db` will remain unless you manually delete it.

---

## Other

**Q: Is ALOY open-source?**
> The Windows installer release is proprietary under a custom EULA. Source code is not publicly available in v1.0. See [LICENSE](../LICENSE).

**Q: Can I use ALOY commercially?**
> Commercial use requires written permission from the creator. See [TERMS_OF_USE.md](../TERMS_OF_USE.md) or contact [anbudhanush31@gmail.com](mailto:anbudhanush31@gmail.com).

**Q: Will ALOY run on macOS or Linux?**
> Officially, only Windows is supported in v1.0. Running from source on macOS/Linux may work but is untested and unsupported in this release.

**Q: How do I report a bug?**
> Open an issue on [GitHub Issues](https://github.com/dhanush708/aloy/issues) using the Bug Report template, or email [anbudhanush31@gmail.com](mailto:anbudhanush31@gmail.com).
