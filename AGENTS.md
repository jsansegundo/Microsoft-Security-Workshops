# Microsoft Security Envisioning Workshops — Agent Guide

This repo is 100% static content (Office docs + markdown). No build, no tests, no runtime.

## Repository structure

```
├── Cloud Security Envisioning Workshop/     # Defender for Cloud, CSPM, multi-cloud
├── Data Security Envisioning Workshop/      # Microsoft Purview, DLP, IRM — v8.5.x
├── Modern SecOps Envisioning Workshop/      # Microsoft Sentinel, SIEM/SOAR
├── Threat Protection Envisioning Workshop/  # Defender XDR, Entra ID, Zero Trust
├── docs/                                     # Historical planning artifacts (Fase 1/2)
├── AGENTS.md                                 # This file
├── SYSTEM_PROMPT.md                          # ⚠️ Master agent prompt — DO NOT edit unless asked
├── CHANGELOG.md                              # Repo changelog
├── checksums.sig                             # SHA-256 hash of SYSTEM_PROMPT.md
├── url.txt                                   # Official Microsoft download links
└── .gitignore
```

## Critical file: `SYSTEM_PROMPT.md`

`SYSTEM_PROMPT.md` defines the AI's role, voice, session structure (4 × 2h), linguistic constraints, and deliverables. Never modify it unless the user explicitly requests changes. `README.md` is human-readable documentation — do not use it as agent instructions. Verify `SYSTEM_PROMPT.md` integrity with `sha256sum -c checksums.sig` before sessions.

## Kit file numbering per workshop

| Workshop | Numbering |
|----------|-----------|
| Cloud Security | 00–10 |
| Data Security | DS-00 to DS-90 |
| Modern SecOps | 00–13 |
| Threat Protection | 00–13 |

## Conventions for generated deliverables

- Write AI-generated session outputs inside the matching workshop directory under `Entregables_SesionN/` (e.g., `Entregables_Sesion1/`, `Entregables_Sesion4/`).
- Language: **Spanish (Spain/peninsular)** only — full linguistic rules in `SYSTEM_PROMPT.md`.
- Session 4 deliverables **must** include:
  - Breach analysis with business impact
  - Technical remediation plan
  - CFO-ready 3-scenario economic estimate (Conservative / Recommended / Aggressive)
  - Licensing optimization: prefer modular add-ons over suite upgrades; evaluate F1/F3 for frontline; flag orphaned licenses as quick wins.
- Reference `url.txt` for official Microsoft workshop resource URLs.

## Git & CI

- Single branch (`master`). PR workflow — commits require PR + 1 approval (GitHub branch protection).
- Git LFS configured for Office binaries (.docx, .pptx, .vsdx, .xlsx, .doc, .xls, .ppt).
- Pre-commit hook (`core.hooksPath .githooks`) — detects PII (emails, DNI, credit cards, IPs, credentials) before commit. Bypass with `git commit --no-verify` for false positives.
- CI (`.github/workflows/validate.yml`) on push/PR: verifies SYSTEM_PROMPT.md checksum, required directories, AGENTS.md references, entregables naming convention, cleanup of `docs/raw/`, and LFS config.
- `.gitignore` ignores `*.tmp`, `*.log`, `__pycache__/`, `generar_docx.py`, and Office temp files.

## Disclaimer for generated deliverables

All AI-generated session outputs (`Entregables_SesionN/`) must include a clear notice at the top of each file:

> *"Este documento contiene datos simulados para fines de demostración y formación. No incluye información real de clientes, datos personales ni información sensible. Cualquier similitud con empresas o personas reales es mera coincidencia."*
