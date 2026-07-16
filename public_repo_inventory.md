# ALOY-Public Documentation Repository Inventory

This document maps all files, assets, licenses, and documentation inside the public ALOY release repository (`C:\Users\DHANUSH ANBU\Desktop\ALOY-Public`).

---

## 1. Repository Directory Structure

```
ALOY-Public/
├── .github/
│   └── ISSUE_TEMPLATE/
│       ├── bug_report.yml
│       ├── config.yml
│       ├── feature_request.yml
│       └── question.yml
├── assets/
│   ├── aloy_banner.png
│   ├── logos/
│   │   ├── aloy.png
│   │   └── README.md
│   └── screenshots/
│       ├── 01-home.png
│       ├── 02-chat.png
│       ├── 03-agent-panel.png
│       ├── 04-memory.png
│       ├── 05-settings.png
│       ├── 06-search.png
│       ├── 07-installation.png
│       └── README.md
├── docs/
│   ├── architecture.md
│   ├── faq.md
│   ├── installation.md
│   ├── known-limitations.md
│   ├── release-notes.md
│   └── roadmap.md
├── CHANGELOG.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
├── DISCLAIMER.md
├── LICENSE
├── PRIVACY_POLICY.md
├── README.md
├── RELEASE_NOTES_v1.0.md
├── SECURITY.md
├── TERMS_OF_USE.md
└── THIRD_PARTY_NOTICES.md
```

---

## 2. File Inventory Details

### Root Level (Legal, Release, and Coordination Docs)
- **README.md** (10,220 bytes) — Main project overview, feature summary, system requirements, quick start guide, FAQ, EULA licensing.
- **LICENSE** (4,194 bytes) — Proprietary EULA (personal, non-commercial use only, distribution restrictions).
- **DISCLAIMER.md** (2,159 bytes) — Liability constraints on AI outputs, local execution, and autonomous agent executions.
- **PRIVACY_POLICY.md** (2,973 bytes) — Full description of the offline privacy model (no cookies, zero external telemetry, local SQLite storage).
- **SECURITY.md** (2,350 bytes) — Vulnerability reporting policy, sandboxing controls, and pgp keys.
- **TERMS_OF_USE.md** (2,334 bytes) — Licensing rules, restrictions on reverse engineering, and usage terms.
- **THIRD_PARTY_NOTICES.md** (3,519 bytes) — Attribution and open-source licenses for retained core Python packages (FastAPI, sqlite-vec, Uvicorn).
- **CHANGELOG.md** (3,809 bytes) — Documented progress history from alpha iterations leading to v1.0.0.
- **CONTRIBUTING.md** (1,831 bytes) — Contribution guidelines for developers.
- **CODE_OF_CONDUCT.md** (1,454 bytes) — Standards of behavior for community interactions.
- **RELEASE_NOTES_v1.0.md** (5,326 bytes) — Main release announcement highlighting event bus core, parallel agent scheduler, and hybrid memory calculations.

### Documentation Directory (`docs/`)
- **docs/architecture.md** (6,875 bytes) — High-level event-driven system map, request lifecycle tracing, FSM states of the Agent Grid, and hybrid RRF memory details.
- **docs/faq.md** (5,276 bytes) — Troubleshooting steps, GPU acceleration configurations, and memory management options.
- **docs/installation.md** (3,913 bytes) — Detailed Windows installer steps and development-mode source clone guide.
- **docs/known-limitations.md** (3,611 bytes) — Acknowledges single-goal workspace locking, VRAM requirements, and Windows OS targets.
- **docs/release-notes.md** (4,243 bytes) — Duplicate release details for in-folder doc navigation.
- **docs/roadmap.md** (2,731 bytes) — Future iteration plans (v1.1 Dynamic Tool Plugins, v1.2 Workspaces, v1.5 Prompt Self-Evolution).

### Assets & Screenshots (`assets/`)
- **assets/aloy_banner.png** (549,802 bytes) — Project branding visual banner.
- **assets/logos/aloy.png** (583,099 bytes) — High-resolution application icon.
- **assets/screenshots/** (7 files, ~70KB each) — Visual walkthrough of Home dashboard, Conversation client, Agent panel, Memory explorer, Settings interface, Search queries, and Onboarding installation steps.
