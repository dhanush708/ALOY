# Installation Guide

**ALOY v1.0.0** | [Back to README](../README.md)

---

## System Requirements

| Requirement | Minimum | Recommended |
| :--- | :--- | :--- |
| **Operating System** | Windows 10 64-bit | Windows 11 64-bit |
| **RAM** | 16 GB | 32 GB |
| **GPU** | Dedicated GPU (6+ GB VRAM) | Dedicated GPU (8+ GB VRAM) |
| **Disk Space** | 5 GB free | 25 GB free |
| **Ollama** | Required (latest) | Required (latest) |
| **Python** | Not required (installer) | 3.11+ (source only) |

---

## Option 1 — Windows Installer (Recommended for All Users)

This is the easiest way to install ALOY. No Python setup required.

### Prerequisites

1. Install **Ollama** from [ollama.com](https://ollama.com) and ensure it is running.

2. Pull the required models:
   ```bash
   ollama pull qwen3:14b
   ollama pull qwen2.5-coder:14b
   ollama pull deepseek-r1:14b
   ollama pull nomic-embed-text:latest
   ```

### Installation Steps

1. Go to [GitHub Releases](https://github.com/dhanush708/aloy/releases).
2. Download `ALOY-Setup-1.0.0.exe`.
3. Run the installer and follow the prompts.
4. Accept the End User License Agreement.
5. Choose an installation directory (default: `C:\Program Files\ALOY`).
6. Click **Install**.

### First Launch

- Double-click the **ALOY** Desktop shortcut, or
- Find **ALOY** in the Start Menu.

Your default browser opens automatically at the ALOY interface (`http://127.0.0.1:8000`).

---

## Option 2 — Run from Source (Developers)

This method requires Python 3.11 or higher.

### Prerequisites

- [Python 3.11+](https://python.org)
- [Git](https://git-scm.com/)
- [Ollama](https://ollama.com)

### Steps

```powershell
# Clone the repository
git clone https://github.com/dhanush708/aloy.git
cd aloy

# Create a virtual environment
python -m venv venv
.\venv\Scripts\Activate.ps1     # Windows PowerShell
# source venv/bin/activate       # macOS / Linux

# Install dependencies
pip install -r requirements.txt

# Launch ALOY
python run.py
```

The server starts on `http://127.0.0.1:8000` and your browser opens automatically.

---

## Uninstalling ALOY

1. Open **Windows Settings** → **Apps** → **Installed Apps**.
2. Search for **ALOY**.
3. Click the three-dot menu → **Uninstall**.

This removes ALOY and all application files. Your user data (`data/aloy.db`) may remain if you installed to a custom directory.

---

## Updating ALOY

1. Download the latest installer from [GitHub Releases](https://github.com/dhanush708/aloy/releases).
2. Run the new installer over the existing installation.
3. The installer will close ALOY automatically before updating.

Your existing conversations and memories are preserved across updates.

---

## Troubleshooting

### ALOY won't start / browser doesn't open

- If ALOY crashes or fails to initialize, a native Windows error dialog will appear explaining the issue.
- Check `logs/startup.log` inside the ALOY installation directory for a full diagnostic traceback.
- Ensure Ollama is installed and running (`ollama serve` in a terminal).
- Try navigating manually to `http://127.0.0.1:8000` in your browser.
- Check Windows Defender or your antivirus — it may have flagged ALOY on first run (this is a false positive common with PyInstaller-built apps).

### "Ollama not detected" overlay appears

- Open a terminal and run: `ollama serve`
- If Ollama is not installed, download it from [ollama.com](https://ollama.com).
- Click **Recheck** in the ALOY overlay.

### Required models missing

- Run the missing `ollama pull <model>` commands shown in the ALOY overlay.
- Click **Recheck** when done.

### Very slow responses

- Ensure Ollama is using your GPU: run `ollama ps` while a model is loaded and check for GPU utilization.
- Ensure your GPU drivers are up to date.
- Consider using a smaller model variant (like `qwen2.5-coder:7b`) if VRAM is limited.

---

See [docs/faq.md](faq.md) for more troubleshooting help.
