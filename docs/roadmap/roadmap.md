# Plan de Mejoras — Microsoft Security Envisioning Workshops

> Generado el 2026-06-01
> Estado: propuesto (pendiente de aprobación)

---

## Diagnóstico breve

Repositorio 100 % contenido estático (Office + Markdown), 759 MB, 70 archivos, 1 solo commit en `master`. `README.md` es un system prompt para IA, no documentación humana. Sin build, tests, scripts ni automatización. Ambos archivos referenciados en `AGENTS.md` ya existen (`docs/roadmap/roadmap.md` y `docs/implementation/progress.md`). Todos los subdirectorios de `docs/` están poblados. Nomenclatura de entregables unificada a `Entregables_SesionN/` (Fase 1).

---

## Bloque 1 — Estabilidad (prioridad máxima)

| # | Mejora | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|---|--------|----------|---------|----------|-------------------|
| 1.1 | **Materializar archivos huérfanos** | Crear `docs/roadmap/roadmap.md` (este) y `docs/implementation/progress.md`; eliminar referencias rotas en AGENTS.md | Evita errores del agente por referencias inexistentes | Bajo (15 min) | AGENTS.md, nuevos archivos |
| 1.2 | ~~Vaciar o poblar directorios `docs/` vacíos~~ | **Ya no aplica** — todos los subdirectorios de `docs/` están poblados con contenido propio | — | — | — |
| 1.3 | **Git LFS para archivos Office pesados** | Migrar .docx/.pptx/.vsdx/.xlsx a Git LFS | Reduce drásticamente el tamaño del clon (759 MB → ~50 KB de punteros) | Medio (config + migración) | .gitattributes, todos los binarios |
| 1.4 | **.gitignore exhaustivo** | Añadir reglas para `.DS_Store`, `.venv/`, patrones Office adicionales | Evita commits accidentales | Bajo (5 min) | .gitignore |

**Orden de ejecución:** 1.2 → 1.1 → 1.4 → 1.3

---

## Bloque 2 — Estructura

| # | Mejora | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|---|--------|----------|---------|----------|-------------------|
| 2.1 | ✅ **EJECUTADO** — Unificar nomenclatura entregables | Renombrado `Entregables_Sesion1_Kickoff/` → `Entregables_Sesion1/` (Fase 1) | Elimina ambigüedad | Bajo | Threat Protection dir |
| 2.2 | ✅ **EJECUTADO** — Mover DOCX huérfano de raíz | `Talleres_Ciberseguridad_DataSecurity_ThreatProtection.docx` → `docs/` (Fase 1) | Orden en raíz | Bajo | Raíz → docs/ |
| 2.3 | **Estandarizar `docs/raw/`** | Unificar los TXT con sus versiones MD (fusionar o marcar obsoletos) | Evita duplicación | Bajo (10 min) | docs/raw/*, docs/architecture/*, docs/security/* |
| 2.4 | **README.md dual** | Añadir cabecera de readme humano antes del system prompt, separado por `---` | Un humano puede entender el repo sin leer el prompt de IA | Medio (15 min) | README.md |
| 2.5 | **CHANGELOG.md** | Arrancar registro de cambios a partir del estado actual | Trazabilidad | Bajo (5 min) | CHANGELOG.md (nuevo) |

**Orden de ejecución:** 2.1 → 2.2 → 2.3 → 2.4 → 2.5

---

## Bloque 3 — Seguridad

| # | Mejora | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|---|--------|----------|---------|----------|-------------------|
| 3.1 | **Protección README.md contra prompt injection** | Envolver el system prompt en bloque condicional `<!-- -->` o moverlo a `.opencode/prompt.md` | Elimina vector de ataque por ingeniería social | Bajo (10 min) | README.md |
| 3.2 | ✅ **EJECUTADO** — Sanear `url.txt` | URLs directas de Partner Center Downloads reemplazadas por aka.ms (Fase 1) | Evita exposición de rutas internas | Bajo | url.txt |
| 3.3 | **Disclaimer para entregables** | Añadir aviso legal estándar a los markdown generados (datos simulados, no PII real) | Mitiga riesgo de exposición de datos de cliente | Bajo (10 min) | AGENTS.md (norma), entregables |
| 3.4 | **Pre-commit hook (client-side)** | Hook que verifique patrones de PII (email, DNI, tarjetas) antes de commit | Capa de prevención | Medio (1-2 h) | .githooks/ |
| 3.5 | **Revisión de seguridad recurrente** | Agenda revisión tras cada batch de nuevas sesiones | Mantenimiento | Bajo (15 min/ciclo) | docs/security/security-review.md |

**Orden de ejecución:** 3.1 → 3.2 → 3.3 → 3.4 → 3.5

---

## Bloque 4 — Evolución funcional

| # | Mejora | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|---|--------|----------|---------|----------|-------------------|
| 4.1 | **Script `generar_docx.py`** | Materializar el script referenciado en `.gitignore` para exportar entregables MD → DOCX | Automatiza entrega al cliente | Alto (4-8 h) | nuevo + .gitignore |
| 4.2 | **Makefile / Taskfile** | Automatizar tareas comunes: lint markdown, exportación, validación de estructura | Estandariza comandos del equipo | Medio (2-3 h) | Makefile o Taskfile.yml |
| 4.3 | **Entregables de Modern SecOps** | Sesión 1 (y opcional Sesión 4) para el taller sin outputs | Cobertura completa de talleres | Medio (1-2 h IA) | Modern SecOps/Entregables_Sesion1/ |
| 4.4 | **GitHub Actions: validador de estructura** | Workflow que verifique nomenclatura, referencias y consistencia tras cada push | CI básico para contenido | Medio (2-3 h) | .github/workflows/validate.yml |
| 4.5 | **Dashboard de cobertura** | Tabla en README.md (sección humana) con estado de cada taller | Visibilidad para el equipo | Bajo (15 min) | README.md |

**Orden de ejecución:** 4.3 → 4.1 → 4.2 → 4.5 → 4.4

---

## Quick wins (impacto ÷ esfuerzo alto)

| # | Tarea | Tiempo |
|---|-------|--------|
| 1.2 | ~~Seedear o limpiar directorios vacíos~~ | ✅ Hecho (no requería acción) |
| 2.1 | ~~Unificar nombres entregables~~ | ✅ Ejecutado |
| 2.2 | ~~Mover DOCX huérfano~~ | ✅ Ejecutado |
| 3.1 | Proteger README.md | 10 min (pendiente Fase 2) |
| 3.2 | ~~Sanear url.txt~~ | ✅ Ejecutado |
| 4.3 | Generar entregables Modern SecOps | 1-2 h IA (pendiente Fase 2) |
