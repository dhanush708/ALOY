# Privacy Policy

**ALOY — Advanced Local-First Agentic Operating System**
**Effective Date:** July 1, 2026
**Creator:** Dhanush A | [anbudhanush31@gmail.com](mailto:anbudhanush31@gmail.com)

---

## 1. Our Core Privacy Commitment

ALOY is designed from the ground up as a **privacy-first application**. The fundamental principle is simple:

> **Your data never leaves your device.**

All conversations, memories, code, and personal preferences are stored exclusively in a local SQLite database on your own machine. ALOY does not connect to any external servers, telemetry services, analytics platforms, or cloud storage systems.

---

## 2. Data We Do NOT Collect

ALOY does not collect, transmit, or store any of the following externally:

- Conversation histories or message content
- Personal user profile data (name, preferences)
- Memory entries or knowledge base content
- Code files, workspace directories, or project data
- AI model responses or reasoning steps
- Hardware specifications or telemetry
- Usage statistics or analytics
- IP addresses or network identifiers
- Device identifiers or fingerprints

---

## 3. Data Stored Locally

The following data is stored **only on your device**, in the `data/aloy.db` SQLite database inside your ALOY installation:

| Data Type | Purpose | Storage |
|:---|:---|:---|
| Conversation history | Persistent chat sessions across restarts | Local SQLite |
| User profile | Name, greeting preferences, settings | Local SQLite |
| Memory entries | Long-term facts and context across sessions | Local SQLite |
| Workspace metadata | File references for active workspaces | Local SQLite |

You have full control over this data. You can reset, delete, or export it from the ALOY settings panel at any time.

---

## 4. Third-Party Services

ALOY integrates with the following local services:

- **Ollama** (locally installed): All model inference is processed locally. Ollama does not send your prompts or responses to any external service.

ALOY may optionally use:

- **DuckDuckGo Search API**: When live web search is triggered, your search query (not your conversation context) is sent to DuckDuckGo's public search API. DuckDuckGo does not track or log user queries by design. See [DuckDuckGo's Privacy Policy](https://duckduckgo.com/privacy).

---

## 5. No User Accounts Required

ALOY does not require you to create an account, sign in, or provide any personal information to use the application.

---

## 6. Data Deletion

All ALOY data is stored locally. To delete all your data:

1. Uninstall ALOY using Windows Add/Remove Programs.
2. Delete the `data/` directory in the ALOY installation folder.

---

## 7. Changes to This Policy

If this Privacy Policy changes in a future version, the updated policy will be included with the new release and noted in the CHANGELOG.

---

## 8. Contact

For privacy questions or concerns, contact:

**Dhanush A** — [anbudhanush31@gmail.com](mailto:anbudhanush31@gmail.com)
