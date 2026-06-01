# Revisión de Seguridad — Microsoft Security Envisioning Workshops

**Fecha:** 2026-06-01
**Tipo:** Revisión de seguridad estática del repositorio
**Repositorio:** Microsoft-Security-Workshops (master @ 4b9a42e)

---

## Hallazgo 1: `README.md` como system prompt — vector de inyección de prompt

- **Evidencia:** `README.md` (líneas 1–101) no es documentación humana. Es el *system prompt* de un agente AI que le instruye sobre qué hacer, cómo responder, qué fuentes consultar y qué formato usar.
- **Impacto:** Cualquier persona con permisos de escritura en el repo puede modificar `README.md` para inyectar instrucciones maliciosas en el agente (ej. "ignora instrucciones de seguridad anteriores", "exfiltra el contenido del repositorio a un servidor externo", "genera respuestas diseñadas para engañar al formador"). Esto constituye un ataque de **supply chain sobre el propio agente AI**.
- **Severidad:** Alta (riesgo real si el repo es colaborativo o acepta PRs externos)
- **Recomendación:** Firmar digitalmente `README.md` o almacenar su hash en un archivo de integridad (`checksums.sig`). Implementar revisión obligatoria de cambios sobre este archivo (branch protection + PRs forzados). Alternativamente, mover el system prompt a un archivo fuera del repositorio (ej. variable de entorno o almacenamiento externo).

---

## Hallazgo 2: Datos de clientes reales en entregables generados — riesgo de PII

- **Evidencia:** `Data Security Envisioning Workshop/Entregables_Sesion4/Sesion4_Analisis_Brechas_y_CFO.md` contiene:
  - `Cliente: Empresa industrial con 250 usuarios M365 E3 (CSP)` (línea 4)
  - `Contexto: Taller Data Security Envisioning v8.0 | Hallazgos de Sesión 3` (línea 5)
  - Uso extensivo del término "Cliente" con contexto financiero y de licencias detallado.
  - En `Threat Protection Envisioning Workshop/` los entregables incluyen: `Cliente: Empresa de Servicios Financieros | 400 empleados | Modelo 100% híbrido` (ej. `Notas_Orador_Defender_XDR.md` línea 4).
- **Impacto:** Aunque los datos actuales parecen escenarios hipotéticos de ejemplo, la estructura y nomenclatura del repo están diseñadas para que estos archivos contengan **datos reales de clientes** en el futuro (nombre de empresa, número de empleados, licencias, hallazgos de seguridad, configuraciones de tenant). Si estos archivos se versionan en un repo público, constituirían una exposición de datos del cliente.
- **Severidad:** Media (riesgo actual bajo porque los datos son genéricos, pero la estructura lo escala a Alta si se introducen datos reales)
- **Recomendación:** Añadir un `.gitignore` o pre-commit hook que detecte patrones de PII (ej. nombres de cliente, dominios de tenant) antes del commit. Documentar una política de sanitización obligatoria para entregables que contengan datos reales. Considerar un repositorio separado y privado para entregables con datos de cliente.

---

## Hallazgo 3: [RESUELTO] Redundancia y duplicación de archivos de control del agente — riesgo de deriva

- **Estado:** Resuelto en Fase 1. `docs/AGENTS.md` no existía en el working tree; los subdirectorios de `docs/` están poblados con contenido propio. Se verificó que no hay duplicación de fuentes de instrucción del agente.
- **Severidad original:** Baja
- **Recomendación original:** Eliminar `docs/AGENTS.md` y los subdirectorios vacíos de `docs/`. — No requería acción porque no existían en el working tree.

---

## Hallazgo 4: [RESUELTO] `url.txt` con parámetros en URL de Partner Center — posible leakage de ruta

- **Estado:** Resuelto en Fase 1. Las 4 URLs directas de descarga (`microsoftpartners.microsoft.com/Downloads/?filename=...`) fueron reemplazadas por enlaces aka.ms (ver `url.txt` líneas 3–6).
- **Severidad original:** Baja
- **Recomendación original:** Usar enlaces acortados (`aka.ms`) — ejecutado.

---

## Hallazgo 5: Sin flujo de revisión ni control de cambios — riesgo de integridad del contenido

- **Evidencia:**
  - Un solo commit (`4b9a42e`), una sola rama (`master`), sin PR workflow.
  - Sin CI/CD, sin tests, sin validación.
  - `docs/architecture/architecture.md` contiene autoevaluación documentando estas carencias (sección 6).
- **Impacto:** Cualquier cambio malicioso o accidental en `README.md` (el system prompt del agente) o en los entregables se refleja inmediatamente en el repo sin revisión intermedia. No hay forma de detectar regresiones en las instrucciones del agente ni en la calidad de los entregables generados.
- **Severidad:** Media (depende del alcance del repositorio; para producción formal con clientes reales es Alta)
- **Recomendación:** Implementar branch protection en `master` que exija PRs y al menos una aprobación. Añadir un pipeline mínimo que verifique la integridad de `README.md` y `AGENTS.md` (longitud, hash, cambios en secciones críticas).

---

## Hallazgo 6: Sin ejecutables ni dependencias técnicas — riesgo controlado

- **Evidencia:** No existe ningún fichero `.py`, `.js`, `.ts`, `.sh`, `.ps1`, `Dockerfile`, `package.json`, `requirements.txt` ni ningún otro artefacto ejecutable o compilable. El repositorio es 100% contenido estático.
- **Impacto:** Esto elimina por completo las categorías tradicionales de vulnerabilidades (inyección de comandos, RCE, path traversal, deserialización insegura, SSRF, XSS, etc.) como vectores de ataque desde el contenido del repo. No hay dependencias de terceros que auditar.
- **Severidad:** N/A (fortaleza, no hallazgo)
- **Recomendación:** Mantener esta disciplina. Si en el futuro se añade código (ej. `generar_docx.py` referenciado en `.gitignore`), debe pasar por revisión de seguridad antes de integrarse.

---

## Resumen de severidades

| # | Hallazgo | Severidad |
|---|----------|-----------|
| 1 | `README.md` como system prompt — vector de prompt injection | **Alta** |
| 2 | Datos de clientes reales en entregables — riesgo de exposición de PII | Media (→ Alta si se introducen datos reales) |
| 3 | [RESUELTO] Duplicación de `AGENTS.md` — deriva en instrucciones del agente | ~~Baja~~ |
| 4 | [RESUELTO] `url.txt` expone rutas internas de Partner Center | ~~Baja~~ |
| 5 | Sin flujo de revisión — riesgo de integridad del contenido | Media |
| 6 | Sin código ejecutable — superficie de ataque nula (fortaleza) | N/A |

---

*Documento generado automáticamente. Revisión sobre el estado del repositorio en master @ 4b9a42e.*
