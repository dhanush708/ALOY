# Security Policy

ALOY is a local-first desktop application. All your data, conversations, and AI inference stay entirely on your machine. This policy explains how security vulnerabilities are handled and how you can keep your installation secure.

---

## Supported Versions

| Version | Supported |
|:---|:---|
| 1.0.0 | ✅ Actively supported |

---

## Reporting a Vulnerability

**Please do NOT report security vulnerabilities via public GitHub Issues.**

If you discover a security vulnerability in ALOY, report it directly to the creator by email:

- **Email**: [anbudhanush31@gmail.com](mailto:anbudhanush31@gmail.com)
- **Subject Line**: `[SECURITY] ALOY Vulnerability Report`

**Include in your report:**
- A clear description of the vulnerability and its potential impact
- Step-by-step reproduction instructions
- Your operating system version and ALOY version
- Code snippets or proof-of-concept if applicable

Allow reasonable time for review, patching, and release before any public disclosure.

---

## Response Process

Upon receiving a report:

1. **Acknowledgement** — The creator will acknowledge receipt within 48 business hours.
2. **Investigation** — The vulnerability will be assessed for severity and impact.
3. **Patch & Release** — If verified, a patch will be developed and released as a new version.
4. **Advisory** — A public advisory may be published after the fix, with attribution if requested.

---

## Security Best Practices for Users

Because ALOY runs entirely on your local machine, your local environment is part of the security model:

- **Database Security**: The `data/aloy.db` SQLite file contains your personal memory and conversations. Ensure file system permissions prevent unauthorized access.
- **Ollama Binding**: By default, Ollama listens on `127.0.0.1` (localhost only). Do not change this to `0.0.0.0` unless you understand the implications.
- **Workspace Isolation**: Do not run ALOY in directories that contain sensitive credentials, private keys, or production configuration files.
- **Keep Updated**: Update ALOY, Ollama, and your GPU drivers regularly to receive the latest security fixes.
- **Tool Confirmation Gates**: ALOY requires explicit user approval for all high-risk operations (file edits, terminal commands, git operations). Do not approve requests you did not initiate.
