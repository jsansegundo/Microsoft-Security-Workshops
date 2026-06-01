# Backlog de Mejoras — Microsoft Security Envisioning Workshops

**Fecha:** 2026-06-01
**Tipo:** Plan priorizado en 4 bloques (estabilidad, estructura, seguridad, evolución funcional)
**Basado en:** Análisis real del repositorio (estático, sin build, 69 archivos, 4 talleres, 5 entregables generados)

---

## 🔒 1. Estabilidad

| # | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|:-:|:---------|:--------|:---------|:-------------------|
| 1.1 | **Proteger integridad del system prompt** — Añadir checksum/hash de `README.md` al repo y verificar que no ha sido modificado antes de cada sesión | Alto — el system prompt es el núcleo del comportamiento del agente; cualquier corrupción silenciosa cambia las respuestas | Bajo (~30 min) | `README.md`, nuevo `checksums.sig` o `.github/workflows/verify-prompt.yml` |
| 1.2 | ✅ **EJECUTADO** — Eliminar duplicación de AGENTS.md | `docs/AGENTS.md` no existía en el working tree; se verificó que no hay duplicación | Medio | Verificado en Fase 1 |
| 1.3 | ✅ **EJECUTADO** — Limpiar directorios `docs/` inertes | Todos los subdirectorios de `docs/` están poblados con contenido. No requiere acción | Bajo | Verificado en Fase 1 |

**Orden de ejecución recomendado:** 1.2 → 1.3 → 1.1

---

## 🏗️ 2. Estructura

| # | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|:-:|:---------|:--------|:---------|:-------------------|
| 2.1 | ✅ **EJECUTADO** — Unificar nomenclatura `Entregables_Sesion1_Kickoff/` → `Entregables_Sesion1/` | Renombrado en Fase 1 | Medio | Threat Protection dir |
| 2.2 | **Separar system prompt de README visible** — Renombrar `README.md` a `SYSTEM_PROMPT.md` y crear un `README.md` humano con descripción del repo | Medio — clarifica propósito; evita que humanos confundan el archivo | Bajo (~30 min) | `README.md` → `SYSTEM_PROMPT.md`, nuevo `README.md` |
| 2.3 | ✅ **EJECUTADO** — Mover `Talleres_Ciberseguridad_DataSecurity_ThreatProtection.docx` | Movido a `docs/` en Fase 1 | Bajo | `docs/Talleres_Ciberseguridad_DataSecurity_ThreatProtection.docx` |
| 2.4 | **Materializar `generar_docx.py` o limpiar `.gitignore`** — Archivo referenciado en `.gitignore` que no existe; decidir si se crea o se elimina la referencia | Medio — desbloquearía automatización DOCX; limpiaría incoherencia | Medio-Alto si se crea; Bajo si solo se limpia `.gitignore` | `.gitignore`, nuevo `generar_docx.py` (opcional) |

**Orden de ejecución recomendado:** 2.1 → 2.3 → 2.2 → 2.4

---

## 🛡️ 3. Seguridad

| # | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|:-:|:---------|:--------|:---------|:-------------------|
| 3.1 | **Proteger contra prompt injection** — `README.md` es modificable por cualquiera con write access; implementar branch protection + PR obligatorio sobre este archivo | Alto — vector de supply chain sobre el agente AI | Medio (config GitHub + CI) | `README.md`, branch protection rules (GitHub), `.github/workflows/verify-prompt.yml` |
| 3.2 | **Prevenir exposición de PII** — Añadir pre-commit hook o linter que detecte patrones de datos de cliente (nombres de empresa, dominios de tenant) antes del commit | Alto — riesgo legal si datos reales se versionan en repo | Medio (pre-commit hook + `.gitleaks.toml`) | `.gitleaks.toml` o `.pre-commit-config.yaml` |
| 3.3 | **Establecer flujo de revisión mínimo** — Branch protection en `master` que exija PR + al menos 1 approval | Medio — evita cambios no revisados en system prompt y entregables | Bajo (settings GitHub) | GitHub branch protection (no archivos) |
| 3.4 | ✅ **EJECUTADO** — Reemplazar URLs directas de Partner Center en `url.txt` por aka.ms links | Ejecutado en Fase 1 | Bajo | `url.txt` |

**Orden de ejecución recomendado:** 3.1 → 3.2 → 3.3 → 3.4

---

## 🚀 4. Evolución funcional

| # | Objetivo | Impacto | Esfuerzo | Archivos afectados |
|:-:|:---------|:--------|:---------|:-------------------|
| 4.1 | **Generar entregables de Modern SecOps** — Único taller sin contenido generado; sesiones 1-4 completas | Alto — cubre el gap del portfolio completo | Medio (~4-8h de contenido) | `Modern SecOps Envisioning Workshop/Entregables_Sesion{1..4}/` |
| 4.2 | **Crear `generar_docx.py`** — Script Python que convierta markdowns de entregables a DOCX/PPTX usando `python-docx` y `python-pptx`, cumpliendo el requisito de README.md (línea 65: entregables en .pptx) | Alto — README.md exige formato .pptx para Sesión 4; hoy se genera solo markdown | Alto (estimación 16-24h dev) | nuevo `generar_docx.py`, `requirements.txt` |
| 4.3 | **Sistema de templates** — Crear directorio `templates/` con plantillas markdown para cada tipo de sesión (guion, speaker notes, checklist, FAQ, análisis CFO) | Medio — estandariza calidad y estructura de outputs | Bajo-Medio (~2h) | `templates/` (nuevo) |
| 4.4 | **Index de contenidos cruzado** — Script que genere un `INDEX.md` con búsqueda por tema/herramienta a través de los 4 talleres | Medio — formador encuentra contenido relevante rápido sin abrir cada DOCX | Medio (~3-4h) | nuevo `INDEX.md` o script generador |

**Orden de ejecución recomendado:** 4.1 → 4.3 → 4.2 → 4.4

---

## Resumen ejecutivo

| Bloque | Items | Esfuerzo total | Prioridad |
|--------|:-----:|:---------------|:----------|
| Estabilidad | 3 | ~40 min | **Inmediata** — riesgos de integridad del agente |
| Estructura | 4 | ~1-8 h | **Corto plazo** — orden y claridad del repo |
| Seguridad | 4 | ~2-4 h | **Corto plazo** — proteger contra vectores reales |
| Evolución funcional | 4 | ~10-36 h | **Medio/largo plazo** — automatización y cobertura |

**Quick wins para esta semana (ejecución <30 min cada uno):** 1.2, 1.3, 2.1, 2.3, 3.3, 3.4

---

*Documento generado a partir del análisis exhaustivo del repositorio en master @ 4b9a42e.*
