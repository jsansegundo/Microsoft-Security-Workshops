# Microsoft Security Envisioning Workshops — Agent Guide

This repo is 100 % static content (Office docs + markdown). No build, no tests, no runtime.

## Repository structure

```
├── Cloud Security Envisioning Workshop/     # Defender for Cloud, CSPM, multi-cloud
├── Data Security Envisioning Workshop/      # Microsoft Purview, DLP, IRM — v8.5.x
├── Modern SecOps Envisioning Workshop/      # Microsoft Sentinel, SIEM/SOAR
├── Threat Protection Envisioning Workshop/  # Defender XDR, Entra ID, Zero Trust
├── README.md                                # ⚠️ Master agent prompt – DO NOT edit unless asked
├── url.txt                                  # Official Microsoft download links for workshop kits
└── .gitignore
```

## Critical file: `README.md`

The README is **not** a human-readable intro. It is the system prompt that defines the AI's role, voice, session structure (4 × 2h), linguistic constraints, and deliverables. Never modify it unless the user explicitly requests changes.

## Conventions for generated deliverables

- Write AI-generated session outputs inside the matching workshop directory under `Entregables_SesionN/` (e.g., `Entregables_Sesion1/`, `Entregables_Sesion4/`).
- Language: **Spanish (Spain/peninsular)** only. Prohibited: Latin American variants (acá, computadora, voseo, etc.).
- Use the standard Microsoft workshop document numbering (00–13) when referring to kit files.
- Session 4 deliverables **must** include:
  - Breach analysis with business impact
  - Technical remediation plan
  - CFO-ready 3-scenario economic estimate (Conservative / Recommended / Aggressive)
  - Licensing optimization: prefer modular add-ons over suite upgrades; evaluate F1/F3 for frontline; flag orphaned licenses as quick wins.
- Reference `url.txt` for official Microsoft workshop resource URLs.

## Git

- Single commit / single branch (`master`) — no established branching or PR workflow.
- `.gitignore` ignores `*.tmp`, `*.log`, `__pycache__/`, `generar_docx.py`, and Office temp files.

## Persistent Project Knowledge

Before proposing changes or analysis, always use these documents as context:

- docs/architecture/architecture.md
- docs/security/security-review.md
- docs/roadmap/roadmap.md
- docs/implementation/backlog.md
- docs/implementation/phase-1.md
- docs/implementation/progress.md

These files are the persistent memory of the project and must be preferred over session memory.
