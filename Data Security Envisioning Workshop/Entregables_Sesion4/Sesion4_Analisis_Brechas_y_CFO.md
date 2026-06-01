# SESIÓN 4 — Análisis Analítico de Brechas
## Data Security Envisioning Workshop — Close-out

**Cliente:** Empresa industrial con 250 usuarios M365 E3 (CSP)
**Contexto:** Taller Data Security Envisioning v8.0 | Hallazgos de Sesión 3

---

# PARTE 1 — ANÁLISIS DE BRECHAS (STORYTELLING)

---

## HALLAZGO 1: Fuga de Propiedad Intelectual por Teams

### Contexto

El departamento de I+D de esta empresa es su motor de crecimiento. 40 personas trabajando en planos de patentes industriales — la propiedad intelectual más valiosa que tienen. Estos planos representan meses —a veces años— de inversión en investigación, y son lo que los diferencia de la competencia.

**Lo que descubrimos:** Estos 40 usuarios comparten los planos de patentes a través de chats de Microsoft Teams. Sin cifrado. Sin etiquetas de confidencialidad. Sin controles de acceso. Sin registro de auditoría.

### La Brecha (Problema)

| Dimensión | Situación actual | Riesgo |
|-----------|-----------------|--------|
| **Visibilidad** | Nadie sabe qué archivos se comparten, con quién, ni cuándo | Ciego total ante la fuga de IP |
| **Control** | Cualquier archivo puede reenviarse, descargarse o compartirse externamente sin restricción | Dependencia exclusiva de la buena fe del empleado |
| **Protección** | Los planos viajan en claro dentro y fuera de la organización | Exposición a interceptación |
| **Auditoría** | No hay registro de quién compartió qué ni con quién | Imposible investigar incidentes |

**En lenguaje de negocio:** Hoy, un ingeniero de I+D puede tomar el plano de una patente, pegarlo en un chat de Teams con un amigo que trabaja en la competencia, y nadie lo sabría hasta que el producto clonado aparezca en el mercado.

**El costo de no hacer nada:** Una fuga de propiedad intelectual en el sector industrial cuesta, en promedio, **$5.4 millones por incidente** (Ponemon 2025). Sin contar el daño competitivo irreversible.

### La Solución

Microsoft Purview tiene tres capas que cierran esta brecha SIN necesidad de cambiar el plan base:

| Capa | Herramienta | ¿Qué hace? | ¿Incluido en E3? |
|------|------------|-----------|:---:|
| **Clasificar** | Sensitivity Labels | Etiqueta automática "Confidencial-Patentes" cuando un documento contiene términos técnicos de I+D | P1 ✅ |
| **Proteger** | Encryption + Rights Management | Cifra el archivo y restringe: solo lectura, sin reenvío, sin descarga | P1 ✅ |
| **Detectar y controlar** | DLP for Teams | Bloquea automáticamente el envío de archivos con contenido sensible por chat de Teams | ✅ |
| **Investigar** | Insider Risk Management | Alerta si un usuario descarga 50+ planos seguidos antes de renunciar | Requiere P2 |

**Recomendación principal:** Implementar Sensitivity Labels + DLP for Teams. Ambas están incluidas en las licencias E3 actuales. Cero costo adicional de licencias.

**Para el futuro cercano:** Si el riesgo de fuga interna es una preocupación creciente, añadir **Insider Risk Management** (requiere E5 Compliance o Purview P2).

### El Valor para el Negocio

- **Protección de la propiedad intelectual** — Activo intangible más valioso de la empresa
- **Cumplimiento regulatorio** — Trazabilidad y control auditables
- **Ventaja competitiva preservada** — Las patentes no se filtran antes de registrarse
- **Confianza del consejo/accionistas** — Gobierno demostrable sobre IP sensible
- **Costo: $0 en licencias** si se usa solo Sensitivity Labels + DLP
- **ROI inmediato:** Una fuga evitada paga la solución de por vida multiplicada por 10

---

## HALLAZGO 2: Cuentas Huérfanas — Ex-empleados y Consultores Siguen Activos

### Contexto

En la revisión de identidades del tenant, encontramos **20 cuentas activas** que ya no deberían existir. Corresponde a:
- Ex-empleados que salieron de la empresa hace meses
- Consultores externos cuyos proyectos terminaron

**No son cuentas «olvidadas»** — todas tienen licencia E3 asignada y activa. Pueden acceder a correo, SharePoint, Teams y todo el entorno.

### La Brecha (Problema)

| Dimensión | Impacto |
|-----------|---------|
| **Seguridad** | 20 puertas abiertas sin dueño legítimo. Un atacante que comprometa UNA de estas credenciales tiene acceso completo al tenant sin levantar sospechas |
| **Económico** | 20 licencias E3 × ~$36/mes × 12 meses = **$8,640/año en desperdicio puro** |
| **Cumplimiento** | En una auditoría ISO 27001, SOC 2, o regulatoria, esto es un hallazgo crítico. "No cuentan con un proceso de desaprovisionamiento de accesos." |
| **Continuidad** | Consultores dados de baja hace meses siguen teniendo acceso a documentos activos de la empresa |

**Esto no es un error técnico — es un riesgo operativo con consecuencias financieras directas.**

### La Solución

| Acción | ¿Qué implica? | Costo |
|--------|--------------|:-----:|
| **Inmediata** | Desactivar las 20 cuentas hoy. Revisar si alguna ha tenido actividad reciente. | $0 |
| **A corto plazo** | Implementar un proceso de offboarding: RRHH notifica → IT desactiva en <24hs | $0 |
| **A medio plazo** | Implementar Access Reviews trimestrales en Entra ID | Requiere Entra ID P2 |
| **Ideal** | Automatizar el ciclo de vida con Entra ID Governance: cuando RRHH marca "fecha de salida", la cuenta se desactiva sola | Requiere Entra ID Governance |

**Recomendación mínima viable:** Las 3 primeras acciones son de proceso, no de tecnología. Configurar un script de PowerShell que recorra cuentas inactivas, desactivarlas y liberar licencias. Cero inversión.

**Para automatizar:** Entra ID Access Reviews (P2 o Governance) programa revisiones periódicas donde el manager certifica (o revoca) el acceso de su equipo.

### El Valor para el Negocio

- **$8,640/año** de ahorro directo en licencias recuperadas
- **Reducción de superficie de ataque** en 20 vectores
- **Auditoría limpia** — proceso demostrable de gobierno de identidades
- **Liberación de licencias** que pueden reasignarse a nuevos empleados sin costo extra
- **Tranquilidad del CISO** sabiendo que no hay puertas abiertas sin dueño

---

## HALLAZGO 3: Solución MDM Duplicada (MobileIron)

### Contexto

El departamento de IT paga una suscripción activa de **MobileIron** para la gestión de políticas de seguridad en los teléfonos móviles de los empleados.

**Lo que descubrimos:** Microsoft Intune está incluido en las licencias M365 E3. Con capacidades equivalentes o superiores: MDM, MAM, Conditional Access, Compliance Policies, configuración de perfiles, y gestión de aplicaciones.

**La empresa está pagando dos veces por la misma funcionalidad.**

### La Brecha (Problema)

| Aspecto | MobileIron | Intune (ya incluido) |
|---------|-----------|---------------------|
| **Costo** | $$$ suscripción activa mensual | $0 (incluido en E3) |
| **MDM** | Sí | Sí |
| **MAM** | Sí | Sí ++ |
| **Conditional Access** | Limitado | Nativo + integración con Entra ID |
| **Consola** | Separada | Unificada con M365 |
| **Integración** | Punto a punto | Nativa con todo el ecosistema |
| **Actualizaciones** | Versiones programadas | Rolling, siempre actualizado |

**El riesgo real:** No es solo que paguen por duplicado. Es que tener dos consolas distintas para gestionar dispositivos aumenta la complejidad operativa, la probabilidad de configuraciones contradictorias, y la carga del equipo de IT.

### La Solución

| Fase | Acción | Plazo |
|------|--------|:-----:|
| 1 | Evaluar políticas actuales de MobileIron y mapearlas a Intune | 1 semana |
| 2 | Configurar perfiles equivalentes en Intune (Compliance + Config) | 1 semana |
| 3 | Migrar dispositivos en lotes (pilot → grupos → todos) | 2-4 semanas |
| 4 | Dar de baja la suscripción de MobileIron | Inmediato después |

**Recomendación:** Migración gradual. No hay pérdida de funcionalidad, y la experiencia del usuario final no se ve afectada.

### El Valor para el Negocio

- **Ahorro directo:** 100% del costo de MobileIron se elimina
- **Simplificación operativa:** Una consola de gestión de dispositivos, no dos
- **Consistencia de políticas:** Las políticas de acceso condicional se definen una vez y se aplican a todos los recursos
- **Seguridad mejorada:** Conditional Access nativo + integración con Defender for Endpoint
- **Sin riesgo de migración:** Coexistencia posible durante la transición

---

# PARTE 2 — NOTAS DEL ORADOR (SPEAKER NOTES)
## Guion natural para diapositivas de hallazgos

---

### Diapositiva 1: Portada — Resultados del Data Security Check

**Notas:**

"Muy buenos días. Hoy tenemos los resultados de las 3 semanas de análisis que hicimos en su entorno. Y spoiler: encontramos cosas que merecen atención."

"Pero antes de entrar en los hallazgos, quiero que quede claro algo: esto no es una auditoría. No vinimos a señalar errores. Vinimos a encontrar oportunidades — y créanme, hay varias."

"Hoy vamos a hablar de tres brechas que descubrimos. Cada una con su historia, su impacto, y — lo más importante — su solución. Al final, su equipo se va con un plan concreto. No con una lista de problemas sin salida."

---

### Diapositiva 2: Resumen Ejecutivo — Los 3 Hallazgos

**Notas:**

"Tres hallazgos. Muy distintos entre sí, pero con algo en común: todos son solucionables CON las herramientas que ya tienen o con inversiones mínimas."

"Primero: su propiedad intelectual —los planos de patentes de I+D— está viajando por Teams sin ningún tipo de control."

"Segundo: tenemos 20 cuentas activas de personas que ya no trabajan acá."

"Tercero: están pagando por una solución de MDM que ya tienen incluida en su licencia."

"Más allá del titular, lo interesante es lo que estos hallazgos revelan sobre procesos, no sobre tecnología. Y las soluciones, en muchos casos, son de proceso —no requieren un presupuesto nuevo."

---

### Diapositiva 3: Hallazgo 1 — La Fuga Silenciosa de I+D (Contexto)

**Notas:**

"Empecemos con I+D. 40 personas. Planos de patentes. El activo más valioso que tiene esta empresa después de su gente."

"¿Por qué es tan crítico? Porque una patente no registrada que se filtra pierde todo su valor. Literalmente. Una vez que el diseño está en dominio público, no hay protección legal que valga."

"Lo que encontramos: estos planos se comparten por chat de Teams como quien comparte una foto de las vacaciones. Sin etiquetar, sin cifrar, sin restricciones. Y no, no es culpa del equipo de I+D — ellos no saben que hay herramientas para protegerlo. Ese es nuestro trabajo."

---

### Diapositiva 4: Hallazgo 1 — El Riesgo (Problema)

**Notas:**

"Pongámoslo en números: según Ponemon, el costo promedio de una fuga de propiedad intelectual industrial es de 5.4 millones de dólares. Por incidente."

"Pero el número frío no cuenta la historia completa."

"Imaginen esto: un competidor —local o internacional— quiere sus planos. Envía un LinkedIn a uno de sus ingenieros. Conversan. El ingeniero, sin mala intención, comparte una captura de un plano por Teams para 'mostrar en qué está trabajando'. Esa captura se reenvía. Termina en el teléfono del competidor."

"¿Cómo se enteran ustedes? No se enteran. Porque hoy no hay forma de detectarlo. No hay alerta, no hay registro, no hay bloqueo."

---

### Diapositiva 5: Hallazgo 1 — La Solución (Solución + Valor)

**Notas:**

"Ahora la buena noticia. Esto se resuelve en tres pasos, y ninguno requiere una licencia nueva."

"**Paso 1:** Creamos una Sensitivity Label que se llama 'Confidencial-Patentes'. Se aplica automáticamente cuando un documento contiene términos relacionados con sus diseños industriales."

"**Paso 2:** Esa label cifra el archivo automáticamente y restringe permisos: solo lectura, sin reenvío, sin descarga."

"**Paso 3:** Configuramos una política DLP para Teams que detecta cuando alguien intenta compartir un archivo etiquetado como 'Confidencial-Patentes' por chat, y lo bloquea o alerta."

"El resultado: su ingeniero de I+D puede compartir lo que necesite, con quien necesite, dentro de la empresa — pero el archivo viaja cifrado y controlado. Y si alguien intenta enviarlo afuera, el sistema lo detiene y alerta al equipo de seguridad."

"**Valor para el negocio:** Protección de su activo más valioso. Sin costo adicional de licencias. Configurable en días."

---

### Diapositiva 6: Hallazgo 2 — Las Puertas Abiertas (Contexto + Problema)

**Notas:**

"Hallazgo número 2. Este es más sencillo de explicar, pero igual de grave."

"Encontramos 20 cuentas activas de personas que ya no trabajan en la empresa."

"No somos jueces — estas cosas pasan en todas las organizaciones. Cuando alguien se va, hay 40 cosas que hacer y dar de baja la cuenta es una más. Pero el riesgo es real."

"Cada una de esas cuentas puede: leer correo, acceder a SharePoint, iniciar Teams, descargar archivos. Y nadie las está vigilando porque... ¿quién vigilaría una cuenta de alguien que ya no trabaja acá?"

"Además, están pagando por esas cuentas. 20 licencias E3 activas sin uso. Son aproximadamente 8,640 dólares al año en desperdicio."

---

### Diapositiva 7: Hallazgo 2 — La Solución (Solución + Valor)

**Notas:**

"La solución inmediata es sencilla: desactivar esas cuentas hoy. Lo hacemos antes de que termine esta reunión si quieren."

"Pero la solución de fondo no es técnica — es de proceso. Necesitan un mecanismo simple: cuando RRHH registra una salida, IT recibe una notificación automática y desactiva en menos de 24 horas."

"Si quieren automatizar más, Entra ID Access Reviews permite que cada manager revise trimestralmente: '¿Estas personas siguen necesitando acceso?' Las cuentas que no se certifican se desactivan solas."

"**Valor para el negocio:** $8,640/año de ahorro directo. Superficie de ataque reducida en 20 vectores. Proceso auditable para compliance."

---

### Diapositiva 8: Hallazgo 3 — Pagar Dos Veces por lo Mismo (Contexto + Problema)

**Notas:**

"Hallazgo 3. Este es el que más le va a gustar al CFO."

"IT tiene MobileIron para gestionar los teléfonos. Y está bien — MobileIron es un producto sólido. Pero Microsoft Intune, que hace lo mismo —y en varios aspectos mejor— ya está incluido en sus licencias E3."

"Están pagando dos veces por la misma funcionalidad. Es como tener Netflix y también pagar Blockbuster por si acaso."

"El problema no es solo el costo duplicado. Es que tener dos consolas de MDM significa: más complejidad para IT, más probabilidad de configuraciones inconsistentes, más tiempo perdido en gestión."

---

### Diapositiva 9: Hallazgo 3 — La Solución (Solución + Valor)

**Notas:**

"La migración es directa y bajo riesgo."

"Mapeamos las políticas actuales de MobileIron a Intune —coinciden en más del 90%—. Migramos los dispositivos en lotes: primero un grupo piloto, luego por departamentos. Coexistencia durante la transición. Cero impacto para el usuario final."

"Cuando termina la migración, dan de baja la suscripción de MobileIron."

"**Valor para el negocio:** Ahorro del 100% del costo de MobileIron. Una consola, no dos. Políticas consistentes. Y acceso condicional nativo con el resto del ecosistema Microsoft."

---

### Diapositiva 10: Tablero de Impacto Económico

**Notas:**

"Miremos el resumen económico de los tres hallazgos."

"Hallazgo 1: Cero dólares en licencias adicionales para la solución básica. La protección de patentes se hace con lo que ya tienen."

"Hallazgo 2: Recuperación de $8,640/año en licencias desperdiciadas — inmediato."

"Hallazgo 3: Eliminación del gasto de MobileIron — ahorro recurrente."

"En conjunto, la recomendación de mínimos no solo no cuesta — genera ahorro. Las inversiones adicionales (como automatizar gobierno de identidades) son optativas y se justifican por sí mismas."

---

### Diapositiva 11: Recomendaciones y Roadmap

**Notas:**

"Esto es lo que recomendamos hacer, en orden de prioridad:"

"**Inmediato (esta semana):**"
"- Desactivar las 20 cuentas huérfanas"
"- Iniciar el mapeo de políticas MobileIron → Intune"

"**Corto plazo (próximas 2 semanas):**"
"- Configurar Sensitivity Labels + DLP para I+D"
"- Definir el proceso de offboarding con RRHH"

"**Medio plazo (próximo mes):**"
"- Migrar dispositivos de MobileIron a Intune"
"- Evaluar Entra ID Access Reviews para automatizar gobierno de identidades"

"**Próximo trimestre:**"
"- Evaluar Insider Risk Management si la preocupación por fuga interna crece"
"- Considerar E5 Compliance para auto-clasificación avanzada"

"En la siguiente sección, su CFO va a querer ver los números. Vamos allá."

---

### Diapositiva 12: Siguientes Pasos

**Notas:**

"¿Qué sigue?"

"Primero: definimos juntos quién lidera cada acción y en qué plazo."

"Segundo: agendamos una sesión de seguimiento en 2 semanas para ver avances."

"Tercero: si algún hallazgo requiere una compra de licencias o servicios adicionales, trabajamos el business case con el equipo financiero."

"Preguntas, dudas, preocupaciones — este es el momento. Prefiero que se vayan con todo claro a que tengan que llamarme después."

---

# PARTE 3 — OPTIMIZACIÓN DE COSTES PARA EL CFO
## Add-ons Estratégicos vs. Salto a M365 E5

---

## Situación Actual

| Concepto | Valor |
|----------|-------|
| Licencias activas | 250 M365 E3 (CSP) |
| Precio estimado E3 (CSP) | ~$34.40/user/mes |
| Gasto mensual actual | ~$8,600/mes |
| Gasto anual actual | ~$103,200/año |
| Orphan accounts (pérdida) | 20 licencias = ~$8,640/año desperdiciado |
| MobileIron (gasto duplicado) | ~$5/device/mes × 250 = ~$15,000/año aprox. |

---

## Escenario A: Add-ons Estratégicos (Mínima Inversión)

Se mantienen las 250 licencias E3. Se añaden capacidades específicas solo donde se necesitan.

### Costos adicionales

| Concepto | Quién | Costo mensual | Costo anual |
|----------|-------|:------------:|:-----------:|
| E5 Compliance add-on (para auto-clasificación avanzada + Insider Risk) | 40 usuarios I+D | +$400 | +$4,800 |
| Entra ID P2 (Access Reviews + Identity Governance básico) | Toda la org (250) | +$1,750 | +$21,000 |
| **Subtotal add-ons** | | **+$2,150** | **+$25,800** |

### Ahorros y recuperación

| Concepto | Ahorro mensual | Ahorro anual |
|----------|:------------:|:-----------:|
| Desactivación 20 orphan accounts | -$688 | -$8,256 |
| Eliminación MobileIron | -$1,250 | -$15,000 |
| **Subtotal ahorros** | **-$1,938** | **-$23,256** |

### Resultado neto Escenario A

| Métrica | Valor |
|---------|-------|
| **Inversión neta mensual** | **+$212/mes** (adicional) |
| **Inversión neta anual** | **+$2,544/año** (adicional) |
| **Protección obtenida** | IP + identidades + dispositivos |
| **ROI en caso de 1 fuga evitada** | 212x (inversión de $2,544 vs. riesgo de $5.4M) |

### Si se opta por la ruta de solo proceso (sin add-ons)

| Concepto | Impacto anual |
|----------|:-----------:|
| Orphan cleanup + proceso manual | -$8,256 (ahorro) |
| Eliminación MobileIron | -$15,000 (ahorro) |
| DLP + Sensitivity Labels (incluido en E3) | $0 |
| **Resultado neto (ruta proceso)** | **-$23,256/año (ahorro neto)** |

✅ **Esta es la ruta de menor impacto económico posible.** La empresa AHORRA $23,256 al año solo con proceso + configuraciones incluidas.

---

## Escenario B: Salto a Microsoft 365 E5 (Full Upgrade)

Se migran las 250 licencias de E3 a E5.

### Costos del upgrade

| Concepto | Cálculo | Valor |
|----------|---------|:-----:|
| Delta E3 → E5 por usuario/mes | ~$55.40 - $34.40 | ~$21.00/user/mes |
| **Costo incremental total mensual** | 250 × $21.00 | **+$5,250/mes** |
| **Costo incremental total anual** | $5,250 × 12 | **+$63,000/año** |

### ¿Qué incluye E5 que E3 no tiene?

| Capacidad | Relevancia para los hallazgos |
|-----------|------------------------------|
| Microsoft Defender for Office 365 P2 | + Seguridad en correo (no es el foco principal) |
| Defender for Identity | + Protección de identidades (complementario) |
| Microsoft Purview Information Protection P2 | 🔑 **Auto-clasificación + Insider Risk Management** |
| Communication Compliance | 🔑 **Monitoreo de comunicaciones sospechosas** |
| Entra ID P2 | 🔑 **Access Reviews + Identity Governance** |
| Advanced eDiscovery | + Investigaciones avanzadas |
| Customer Lockbox | + Control de acceso de soporte técnico |

### Ahorros aplicables (igual que Escenario A)

| Concepto | Ahorro anual |
|----------|:-----------:|
| Desactivación 20 orphan accounts | -$8,256 |
| Eliminación MobileIron | -$15,000 |
| **Subtotal ahorros** | **-$23,256** |

### Resultado neto Escenario B

| Métrica | Valor |
|---------|-------|
| **Inversión neta mensual** | **+$5,250 - $1,938 = +$3,312/mes** |
| **Inversión neta anual** | **+$63,000 - $23,256 = +$39,744/año** |
| **Cobertura** | Completa (todos los productos Microsoft) |

---

## Comparativa: Escenario A vs. Escenario B

| Dimensión | 🟢 Escenario A (Add-ons) | 🔵 Escenario B (E5 Completo) |
|-----------|:----------------------:|:--------------------------:|
| **Costo neto anual** | **+$2,544** (o -$23,256 con ruta proceso) | **+$39,744** |
| **Brechas cubiertas** | ✅ Las 3 brechas | ✅ Las 3 brechas + más |
| **Protección IP (I+D)** | ✅ DLP + Labels (incluido) | ✅ DLP + Labels + Auto-clasificación P2 |
| **Orphan accounts** | ✅ Proceso manual o Entra ID P2 | ✅ Entra ID P2 incluido |
| **MobileIron** | ✅ Migración a Intune (incluido) | ✅ Migración a Intune (incluido) |
| **Insider Risk Management** | ❌ No incluido (add-on aparte) | ✅ Incluido |
| **Communication Compliance** | ❌ No incluido | ✅ Incluido |
| **Defender for Office 365** | ❌ No incluido | ✅ P2 incluido |
| **Defender for Identity** | ❌ No incluido | ✅ Incluido |
| **Complejidad de licencias** | Media (varios add-ons) | Baja (un solo SKU) |
| **Escalabilidad futura** | Pagas solo lo que usas | Todo incluido, crece solo |
| **ROI si hay 1 fuga de IP** | 212x (inversión $2,544 vs. riesgo $5.4M) | 136x (inversión $39,744 vs. $5.4M) |

---

## Recomendación al CFO

### Ruta 1: La de menor impacto económico posible ✅ RECOMENDADA

| Paso | Acción | Impacto |
|:----:|--------|:-------:|
| 1 | Desactivar 20 cuentas huérfanas HOY | -$8,256/año |
| 2 | Cancelar/iniciar migración de MobileIron | -$15,000/año |
| 3 | Implementar DLP for Teams + Sensitivity Labels (incluido) | $0 |
| 4 | Definir proceso de offboarding con RRHH | $0 |
| **Total neto** | | **-$23,256/año (AHORRO)** |

**Sin invertir un dólar adicional en licencias, la empresa ahorra $23,256 al año y cierra las 3 brechas identificadas.**

### Ruta 2: Si se quiere automatizar gobierno de identidades

Añadir **Entra ID P2** para toda la organización:

| Costo adicional | $21,000/año |
|----------------|:-----------:|
| Neto con ahorros | **$21,000 - $23,256 = -$2,256/año (sigue siendo ahorro neto)** |

✅ **Incluso comprando Entra ID P2, el neto sigue siendo positivo.**

### Ruta 3: Upgrade completo a E5 (solo si hay otros drivers)

Recomendado si además de estas brechas, la organización necesita:
- Defender for Office 365 para seguridad de correo avanzada
- Communication Compliance para monitoreo regulatorio
- Defender for Identity para protección de Active Directory
- Advanced eDiscovery para litigios
- Y se prefiere simplificar la gestión de licencias con un solo SKU

| Costo incremental neto | **+$39,744/año** |
|------------------------|:----------------:|

---

## Resumen Ejecutivo para el CFO

```
┌─────────────────────────────────────────────────────────────┐
│       RESUMEN — OPTIMIZACIÓN DE COSTES DE SEGURIDAD         │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  SITUACIÓN ACTUAL:                                          │
│  • 250 licencias M365 E3             ~$103,200/año          │
│  • 20 licencias E3 desperdiciadas    ~$8,256/año            │
│  • MobileIron (redundante)            ~$15,000/año           │
│  • Gasto real útil                   ~$79,944/año            │
│                                                             │
│  RECOMENDACIÓN (MÍNIMA INVERSIÓN):                          │
│  • Desactivar cuentas huérfanas       -$8,256/año           │
│  • Migrar MobileIron → Intune        -$15,000/año           │
│  • DLP + Labels (incluido en E3)      $0                    │
│  ─────────────────────────────────────                       │
│  • AHORRO NETO ANUAL                  $23,256                │
│  • Brechas cerradas:                  3 de 3                 │
│                                                             │
│  INVERSIÓN OPCIONAL (AUTOMATIZACIÓN):                       │
│  • Entra ID P2 (250 users)           +$21,000/año            │
│  • Neto con ahorros:                  -$2,256/año (ahorro)   │
│                                                             │
│  UPGRADE COMPLETO A E5 (SCOPE MÁXIMO):                      │
│  • Costo incremental neto             +$39,744/año            │
│  • Incluye: Defender, Compliance P2,  │
│    Communication Compliance, Identity  │
│    Governance, Advanced eDiscovery    │
│                                                             │
│  CONCLUSIÓN:                                                │
│  Las 3 brechas identificadas se resuelven sin inversión      │
│  adicional en licencias. La empresa PUEDE AHORRAR            │
│  $23,256/año mientras fortalece su postura de seguridad.     │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Nota metodológica

Los precios utilizados son estimaciones basadas en precios de lista comercial CSP para la región correspondiente. Los precios reales pueden variar según el acuerdo comercial, el volumen, y el partner CSP. Se recomienda validar los precios exactos con el partner CSP o el account team de Microsoft antes de tomar decisiones de compra.

| SKU de referencia | Precio estimado (CSP, lista) |
|-------------------|:---------------------------:|
| Microsoft 365 E3 | ~$34.40/user/mes |
| Microsoft 365 E5 | ~$55.40/user/mes |
| Microsoft 365 E5 Compliance | ~$10.00/user/mes (add-on) |
| Microsoft 365 E5 Security | ~$12.00/user/mes (add-on) |
| Entra ID P2 | ~$8.00/user/mes (standalone) |

---

*Fin del documento — Sesión 4: Análisis de Brechas y Optimización de Costes*
