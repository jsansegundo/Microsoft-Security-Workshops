# Plan Fase 1 — Estabilización y Consistencia Documental

**Fecha:** 2026-06-01
**Basado en:** architecture.md, security-review.md, roadmap.md, backlog.md, executive-summary.md, session-architecture.txt, session-security.txt, AGENTS.md

---

## 1. Objetivos

- Unificar convenciones de nomenclatura según AGENTS.md (`Entregables_SesionN/`)
- Reubicar documentos Office huérfanos de la raíz a `docs/`
- Sanear `url.txt` eliminando URLs directas de descarga de Partner Center
- Materializar archivos referenciados pero inexistentes (`progress.md`)
- Sincronizar AGENTS.md con el estado real del repositorio
- Verificar y corregir consistencia cruzada entre los 8 documentos de `docs/`
- Sin modificar README.md, sin crear código, sin configurar GitHub

## 2. Tareas concretas

| # | Tarea | Origen | Esfuerzo |
|---|-------|--------|:--------:|
| **A** | Renombrar `Threat Protection/Entregables_Sesion1_Kickoff/` → `Entregables_Sesion1/` | architecture.md §6, backlog#2.1, roadmap#2.1 | 2 min |
| **B** | Mover `Talleres_Ciberseguridad_DataSecurity_ThreatProtection.docx` de raíz a `docs/` | architecture.md §4, backlog#2.3, roadmap#2.2 | 1 min |
| **C** | Sanear `url.txt`: sustituir 4 URLs directas de Partner Center Downloads por aka.ms | security-review.md #4, backlog#3.4, roadmap#3.2 | 5 min |
| **D** | Crear `docs/implementation/progress.md` con estado inicial verificable del repo | roadmap#1.1, AGENTS.md (ref huérfana) | 10 min |
| **E** | Actualizar `AGENTS.md` — sección "Persistent Project Knowledge": verificar que las 6 referencias existen | roadmap#1.1 | 2 min |
| **F** | Auditoría cruzada de `docs/`: corregir discrepancias entre el contenido real y lo que cada análisis documenta | transversal | 10 min |

## 3. Archivos a modificar

| Archivo | Acción |
|---------|--------|
| `Threat Protection Envisioning Workshop/Entregables_Sesion1_Kickoff/` → `Entregables_Sesion1/` | Renombrar (mv) |
| `Talleres_Ciberseguridad_DataSecurity_ThreatProtection.docx` | Mover a `docs/` |
| `url.txt` | Editar líneas 4–7 (reemplazar 4 URLs directas) |
| `docs/implementation/progress.md` | **Crear** (nuevo) |
| `AGENTS.md` | Editar sección "Persistent Project Knowledge" si procede |
| Cualquier archivo `docs/*.md` | Editar si la auditoría F encuentra contradicción |

## 4. Orden exacto de ejecución

```
A → B → C → D → E → F
```

1. **A** — rename; antes `grep -r "Entregables_Sesion1_Kickoff"` para verificar que nada referencia la ruta vieja
2. **B** — mover DOCX a `docs/`; antes `grep -ri "Talleres_Ciberseguridad"` para detectar referencias
3. **C** — editar `url.txt`; verificar aka.ms con `curl -sI` antes de commit
4. **D** — crear `progress.md` con estado inicial alineado con executive-summary.md
5. **E** — editar AGENTS.md solo si alguna referencia no existe tras paso D
6. **F** — leer cada archivo de `docs/` y verificar que su contenido describe el estado actual del repo; corregir si hay contradicciones

Un solo commit atómico al final.

## 5. Riesgos a evitar

| Riesgo | Mitigación |
|--------|------------|
| Renombrar `_Kickoff` rompe referencias internas | `grep -r` previo a la ruta vieja |
| Mover DOCX rompe ruta referenciada | `grep -ri` previo al nombre del archivo |
| `progress.md` con datos inconsistentes | Basar contenido en executive-summary.md + architecture.md verificables |
| `url.txt` con enlaces rotos | `curl -sI` a cada aka.ms antes de commit |
| Editar AGENTS.md incorrectamente | Editar solo la línea necesaria; mantener el resto intacto |
| Documentos `docs/` se contradicen | Auditoría F los detecta y corrige |

## 6. Criterios de validación

- [ ] `grep -r "Entregables_Sesion1_Kickoff"` no devuelve resultados
- [ ] `ls -la Talleres_Ciberseguridad_DataSecurity_ThreatProtection.docx` falla (no está en raíz); `ls -la docs/Taller*` funciona
- [ ] `url.txt` no contiene URLs con patrón `microsoftpartners.microsoft.com/Downloads/`
- [ ] `docs/implementation/progress.md` existe con contenido coherente con el estado real
- [ ] AGENTS.md lista 6 referencias en "Persistent Project Knowledge" y todas apuntan a archivos que existen
- [ ] `git status` = 1 rename + 1 move + 1 new + ≤3 edits
- [ ] `git diff --cached` no toca README.md ni archivos fuera de alcance
- [ ] Tras F, todos los archivos `docs/*.md` describen el estado actual sin contradicciones
