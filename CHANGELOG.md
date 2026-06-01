# Changelog — Microsoft Security Envisioning Workshops

## [1.0.0] — 2026-06-01 — Fase 1 + Fase 2

### Fase 1: Estabilización y consistencia documental

- Renombrado `Threat Protection/Entregables_Sesion1_Kickoff/` → `Entregables_Sesion1/`
- Movido `Talleres_Ciberseguridad_DataSecurity_ThreatProtection.docx` de raíz a `docs/`
- Saneado `url.txt`: 4 URLs directas de Partner Center reemplazadas por aka.ms
- Creado `docs/implementation/progress.md` con estado inicial del repo
- Verificadas referencias en `AGENTS.md`
- Auditoría cruzada de `docs/` — corregidas contradicciones en 8 archivos
- Nuevo `docs/implementation/phase-1.md` con el plan aprobado

### Fase 2: Seguridad del system prompt + estructura del repo

- `.gitignore` exhaustivo: `.venv/`, `.env`, `.vscode/`, `.idea/`, patrones Office adicionales
- Separado system prompt: `README.md` → `SYSTEM_PROMPT.md` + nuevo `README.md` humano
- `AGENTS.md` actualizado para referenciar `SYSTEM_PROMPT.md`
- `checksums.sig` con hash SHA-256 de `SYSTEM_PROMPT.md`
- `CHANGELOG.md` creado (este archivo)
- Disclaimer legal para entregables en `AGENTS.md`
- Fusionados y eliminados `docs/raw/` (contenido TXT integrado en .md)
- Git LFS configurado para Office binarios (50 archivos migrados, ~558 MB)
- Historia reescrita: los commits ahora contienen punteros LFS en lugar de binarios
