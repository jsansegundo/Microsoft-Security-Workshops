# Cloud Security Envisioning Workshop — SESIÓN 1: KICKOFF

## Guion Detallado del Formador

**Duración estimada:** 2 horas (reunión de kickoff)
**Formato:** Presencial / Virtual
**Audiencia:** Sponsor ejecutivo, Arquitectos de seguridad/nube, Administradores de infraestructura, Equipo de SOC

---

## ÍNDICE DE LA SESIÓN

| # | Bloque | Diapositivas | Duración |
|---|--------|:------------:|:--------:|
| 1 | Bienvenida y apertura | 1-3 | 5 min |
| 2 | Rompehielos: la historia de "La caja fuerte en el garaje" | — | 5 min |
| 3 | ¿Qué es este taller y para qué sirve? | 5-7 | 10 min |
| 4 | El desafío de la seguridad en la nube | 8-10 | 10 min |
| 5 | Qué vamos a hacer — Módulos del taller | 11-15 | 15 min |
| 6 | Fases y actividades del engagement | 16-17 | 10 min |
| 7 | Cómo funciona: diseño sin impacto | — | 5 min |
| 8 | Gobierno del proyecto | 18-19 | 10 min |
| 9 | Próximos pasos y logística | 20-22 | 5 min |
| 10 | Q&A y cierre | — | 5 min |

---

## BLOQUE 1 — BIENVENIDA Y APERTURA (5 min)

*(Diapositiva 1 — Portada: "Cloud Security Envisioning Workshop — Kickoff" con logos)*

**Formador:** "Muy buenos días a todos. Gracias por estar acá. Y cuando digo 'gracias' lo digo en serio — porque sé que en cualquier organización tener a un grupo así reunido, con gente de seguridad, de infraestructura, de nube y de negocio, es más difícil de coordinar que un operativo de fin de año."

*(Sonrisa. Pausa breve.)*

**Formador:** "Mi nombre es [Nombre] y vengo de [Empresa/Partner]. Hoy empezamos algo que me entusiasma mucho: el Cloud Security Envisioning Workshop."

*(Clic a Diapositiva 2 — "Siempre revisa que tengas la versión más reciente")*

**Formador (comentario rápido):** "Esa diapositiva es para mí — no para ustedes. Significa que antes de venir revisé que esta sea la versión más actualizada del taller. Ustedes no tienen que preocuparse por eso."

*(Clic a Diapositiva 3 — Feedback)*

**Formador (comentario rápido):** "Y esta es otra para nosotros. Si algo no funciona, si algo no se entiende, si algo se siente como pérdida de tiempo — queremos saberlo. Acé hay un enlace directo al equipo que construye este taller. Úsenlo sin miedo."

*(Clic a Diapositiva 4 — Version History, comentario rápido)*

**Formador:** "Este taller ha evolucionado. Arrancó en septiembre de 2025 y ya vamos por la versión 1.1 con nuevos módulos. Es un taller vivo, que se actualiza con las capacidades que Microsoft lanza."

*(Transición al rompehielos)*

---

## BLOQUE 2 — ROMPEHIELOS: "LA CAJA FUERTE EN EL GARAJE" (5 min)

*(Sin diapositiva — o una imagen simple de un edificio de oficinas vs. una nube. El formador se acerca, baja el ritmo.)*

**Formador:** "Antes de meternos en la agenda y los módulos, quiero contarles una historia que les va a sonar familiar."

*(Pausa. Tono conversacional.)*

**Formador:** "Imaginen que su empresa tiene un edificio. Dentro del edificio hay una caja fuerte con todos los documentos importantes: contratos, propiedad intelectual, datos financieros. Para llegar a la caja fuerte hay que pasar por: un guardia en la entrada, una puerta con tarjeta, un pasillo con cámaras, y la puerta de la caja fuerte con combinación."

*(Pausa. Gestos con las manos.)*

**Formador:** "Todo bien, ¿verdad? Esa es seguridad en capas. Funciona."

*(Clic a imagen — la caja fuerte ahora está en el garaje de una casa)*

**Formador:** "Ahora imaginen que la empresa decide mudar sus operaciones. Pero en vez de alquilar un edificio nuevo, cada empleado empieza a trabajar desde su casa. Los servidores se van a AWS, las apps a Azure, los datos a SaaS. La caja fuerte… ahora está en el garaje de una casa en las afueras."

*(Pausa. Mirada al público.)*

**Formador:** "Sigue siendo la misma caja fuerte. Con las mismas cerraduras. Pero ahora el 'edificio' no es suyo. No controlan quién entra al garaje. No controlan si el vecino tiene acceso. No controlan si hay una puerta trasera que alguien más abrió sin decirles."

*(Eleva ligeramente la mano)*

**Formador:** "Eso es la seguridad en la nube. Los mismos datos, los mismos riesgos… pero un modelo de responsabilidad completamente distinto. Ya no basta con poner un candado bueno — hay que saber qué está pasando en un entorno que no controlamos al 100%."

*(Tono normal, cálido)*

**Formador:** "Este taller existe exactamente para eso: para ayudarles a entender dónde está su caja fuerte hoy, quién más tiene acceso al garaje, y cómo asegurarse de que las cerraduras realmente funcionan en este nuevo mundo."

*(Transición)*

---

## BLOQUE 3 — ¿QUÉ ES ESTE TALLER Y PARA QUÉ SIRVE? (10 min)

*(Diapositiva 5 — Section Header: "Engagement Overview")*

**Formador:** "Bien. Hablemos de qué es esto exactamente."

*(Clic a Diapositiva 6 — "Introducing the Cloud Security Envisioning Workshop")*

**Formador:** "Esto es un taller de tres semanas diseñado para hacer una cosa: ayudarles a fortalecer su postura de seguridad en Azure — y también en AWS y GCP si los usan — a través de un diagnóstico práctico, no de una presentación."

*(Pausa)*

**Formador:** "No vamos a venderles nada durante el taller. Vamos a CONFIGURAR herramientas de seguridad de Microsoft directamente en su tenant de producción, durante 2 o 3 semanas. Vamos a recolectar datos reales de su entorno. Y al final, nos sentamos y les mostramos: esto es lo que vimos, esto es lo que significa, y esto es lo que recomendamos."

*(Clic a Diapositiva 7 — Overview diagram)*

**Formador:** "El taller tiene tres grandes momentos:"

*(Señala con la mano)*

**Formador:** "**Primero: Descubrimiento.** Evaluamos su postura actual — qué recursos tienen en la nube, cómo están configurados, qué amenazas los están atacando."

"**Segundo: Visión.** Les mostramos lo que Microsoft Defender for Cloud puede hacer por ustedes, conectando los hallazgos con las capacidades del producto."

"**Tercero: Plan.** Construimos juntos una hoja de ruta con pasos concretos, responsables y plazos."

*(Clic a Diapositiva 8 — "What we'll do")*

**Formador:** "En concreto:"
- "**Analizamos** sus requisitos y prioridades."
- "**Definimos el alcance** y configuramos las herramientas en su entorno."
- "**Descubrimos amenazas** activas que están atacando sus cargas de trabajo."
- "**Evaluamos su postura de seguridad** — configuración, cumplimiento, vulnerabilidades."
- "Y **planificamos** los siguientes pasos."

*(Clic a Diapositiva 9 — "After the workshop")*

**Formador:** "Cuando terminemos, ustedes van a:"
- "Saber priorizar y responder a las amenazas que realmente los afectan."
- "Tener visibilidad de su postura de seguridad en Azure (y multicloud si aplica)."
- "Recibir recomendaciones personalizadas — no genéricas, sino basadas en los datos de su entorno."
- "Y tener un plan de acción claro, con dueños y fechas."

*(Clic a Diapositiva 10 — Objectives)*

**Formador:** "Los objetivos son simples:"
1. "Descubrir amenazas usando la telemetría de Microsoft Defender XDR unificada."
2. "Entender su postura de seguridad — no solo en Azure, también en AWS y GCP si aplica."
3. "Y definir los siguientes pasos entre todos — no los vamos a dejar colgados con un informe de 200 páginas."

*(Transición)*

---

## BLOQUE 4 — EL DESAFÍO DE LA SEGURIDAD EN LA NUBE (10 min)

*(Diapositiva nueva — o apoyarse en diapositiva 8. Imagen conceptual: servidores tradicionales vs. nube con múltiples conexiones)*

**Formador:** "Quiero detenerme un momento en esto, porque es importante."

*(Pausa)*

**Formador:** "La mayoría de las empresas con las que trabajamos nos dicen lo mismo: 'Pasamos a la nube por agilidad, por escalabilidad, por costo. Pero la seguridad… la seguridad la estamos armando sobre la marcha.'"

*(Camina lentamente)*

**Formador:** "Y no es su culpa. La nube cambió las reglas del juego de formas que todavía estamos asimilando."

*(Señala conceptos con la mano)*

**Formador:** "Antes: tenías un data center, ponías un firewall en el perímetro, y listo."

**Formador:** "Ahora: tus recursos están distribuidos en Azure, tal vez en AWS, en SaaS, en APIs públicas. No hay un perímetro. Hay decenas de 'micro-perímetros' que tienes que configurar y vigilar por separado."

*(Pausa)*

**Formador:** "Y el problema más grande no es la tecnología — es la visibilidad. Porque cuando algo está mal configurado en la nube —una base de datos expuesta, un contenedor con vulnerabilidades, una clave de API en un repositorio público— el tiempo de exposición se mide en minutos, no en días."

*(Tonos más enfático)*

**Formador:** "Aquí es donde entra Microsoft Defender for Cloud. No es solo un producto más. Es una plataforma que les da visibilidad unificada de su postura de seguridad (CSPM) y detección de amenazas en tiempo real para sus cargas de trabajo, sin importar si están en Azure, en AWS, en GCP o en on-premise."

*(Mira al público)*

**Formador:** "Lo que vamos a hacer en estas semanas es exactamente eso: conectar Defender for Cloud a su entorno y ver qué encontramos."

*(Transición)*

---

## BLOQUE 5 — QUÉ VAMOS A HACER: MÓDULOS DEL TALLER (15 min)

*(Diapositiva 11 — Modular Design)*

**Formador:** "Ahora sí, hablemos de la estructura concreta."

*(Pausa)*

**Formador:** "El taller tiene dos tipos de módulos. Los obligatorios, que hacemos siempre, y los seleccionables, donde ustedes eligen según sus prioridades."

**Formador:** "**Módulos obligatorios (los hacemos siempre):**"
- "**Microsoft Defender Portal** — la plataforma unificada donde convergen todas las alertas, incidentes y capacidades de búsqueda de amenazas."
- "**Cloud Security Posture Management (CSPM)** — el análisis de configuración, cumplimiento normativo, recomendaciones de seguridad y caminos de ataque."

*(Pausa)*

**Formador:** "**Módulos seleccionables (eligen mínimo 2):**"

*(El formador los enumera señalando la diapositiva)*

**Formador:** "Tenemos 9 módulos para elegir. Van a ver las fichas de cada uno en la presentación, pero déjenme darles un resumen ejecutivo:"

1. "**Defender for Servers** — protección para sus máquinas virtuales, parches, vulnerabilidades, EDR."
2. "**Defender for Databases** — detección de amenazas para SQL y bases de datos open-source."
3. "**Defender for Storage** — detección de malware en uploads, anomalías de acceso, datos sensibles."
4. "**Defender for Containers** — seguridad en AKS, imágenes, runtime."
5. "**Defender for App Service** — protección para aplicaciones web, SQL injection, XSS."
6. "**Defender for AI Services** — esto es nuevo. Protección para Azure OpenAI, detección de prompt injection, uso indebido."
7. "**Defender for Key Vault** — monitoreo de accesos anómalos a sus secretos y certificados."
8. "**Defender for APIs** — seguridad para APIs, OWASP Top 10, exposición de datos."
9. "**Security Exposure Management** — visión consolidada de exposición, caminos de ataque, iniciativas de seguridad."

*(Pausa para preguntas)*

**Formador:** "La elección es de ustedes. Según lo que vimos en el cuestionario y lo que conversamos hoy, vamos a seleccionar los 2 o más módulos que mejor se alineen con sus prioridades. No se preocupen si no están seguros ahora — en la siguiente sesión definimos el alcance exacto."

*(Transición)*

---

## BLOQUE 6 — FASES Y ACTIVIDADES DEL ENGAGEMENT (10 min)

*(Diapositiva 12 — Phases and Activities: Setup)*

**Formador:** "Veamos cómo se organiza esto en el tiempo. Son aproximadamente 5 semanas, pero no se asusten — la mayor parte del tiempo las herramientas están trabajando solas."

*(Señala las fases)*

**Formador:** "**Semana 1 — Pre-engagement:**"
- "La llamada inicial que ya tuvimos."
- "El cuestionario que ya completaron."
- "Y opcionalmente, una sesión de readiness para que el equipo conozca las herramientas."

**Formador:** "**Semana 2 — Setup:**"
- "La reunión de hoy (kickoff)."
- "La definición del alcance — elegimos los módulos."
- "La configuración de los módulos obligatorios y seleccionables."

*(Clic a Diapositiva 13 — Phases: Data Collection onwards)*

**Formador:** "**Semanas 2 a 4 — Data Collection:**"
- "Las herramientas empiezan a recolectar datos de su entorno."
- "No hay interrupción para sus operaciones."
- "Hacemos un check-in para verificar que los datos están fluyendo."

**Formador:** "**Semana 5 — Exploración y Resultados:**"
- "Analizamos juntos los hallazgos: CSPM, Threat Protection, y Security Exposure Management."
- "Presentamos los resultados."
- "Definimos los siguientes pasos."
- "Y opcionalmente, hacemos la desinstalación (decommissioning)."

*(Pausa)*

**Formador:** "En total, son aproximadamente 22 horas de trabajo del equipo de entrega, repartidas en 5 semanas. La mayoría del trabajo pesado lo hacen las herramientas — ustedes solo necesitan estar disponibles para las sesiones clave."

---

## BLOQUE 7 — CÓMO FUNCIONA: DISEÑO SIN IMPACTO (5 min)

*(Sin diapositiva dedicada, o incluirlo en la 12/13)*

**Formador:** "Quiero ser muy claro en algo, porque siempre surge la pregunta."

*(Pausa. Tono sereno pero firme.)*

**Formador:** "Todo lo que configuramos está diseñado para **no tener impacto en sus operaciones**."

*(Enumera con los dedos)*

**Formador:** "Uno: No vamos a bloquear nada — operamos en modo monitoreo. Las políticas de seguridad que configuramos detectan y alertan, pero no bloquean."

"Dos: No instalamos nada en dispositivos de usuarios finales. Esto es seguridad de nube e infraestructura."

"Tres: No activamos respuestas automáticas durante el taller. Nada de 'bloquear IPs automáticamente' o 'poner cuarentenas sin preguntar'. Todo es visible, todo es revisable, y al final ustedes deciden qué hacer con la información."

*(Mira al público)*

**Formador:** "Este taller es como hacerse una resonancia magnética. La máquina hace su trabajo, genera imágenes, y luego los médicos —ustedes— interpretan los resultados y deciden el tratamiento. Nosotros somos el técnico que opera la máquina y ayuda a leer los resultados."

---

## BLOQUE 8 — GOBIERNO DEL PROYECTO (10 min)

*(Diapositiva 18 — Project Governance)*

**Formador:** "Hablemos del cómo nos organizamos para que esto funcione."

*(Pausa)*

**Formador:** "Para que el taller sea exitoso, necesitamos tres cosas de su lado:"

1. "**Un sponsor ejecutivo** — la persona que abre puertas, que destraba recursos si algo se complica."
2. "**Los arquitectos y administradores correctos** — seguridad, nube, infraestructura, identidad. La gente que conoce su entorno."
3. "**Acceso al tenant** — con los permisos necesarios para configurar las herramientas."

*(Clic a la tabla de roles)*

**Formador:** "Del lado de nosotros —el equipo de entrega— vamos a tener:"
- "Un arquitecto de seguridad que lidera la parte técnica."
- "Un consultor de seguridad que ejecuta las configuraciones y el análisis."
- "Y opcionalmente, un project manager si el engagement lo requiere."

*(Pausa)*

**Formador:** "¿Cómo nos comunicamos? Vamos a acordar canales — Teams, correo, lo que prefieran. Check-ins regulares. Y toda la documentación la compartimos en un repositorio común."

*(Diapositiva 19 — Next Steps/Actions)*

**Formador:** "Vamos a dejar esta tabla con compromisos concretos: quién hace qué, para cuándo. Nada queda en el aire."

*(Transición)*

---

## BLOQUE 9 — PRÓXIMOS PASOS Y LOGÍSTICA (5 min)

*(Diapositiva 20 — Q&A)*

**Formador:** "Antes de cerrar, cosas prácticas:"

*(Tono directo, práctico)*

**Formador:** "**Sesión de definición de alcance:** En los próximos días vamos a tener una sesión de 2 horas para elegir los módulos definitivos. Usaremos una herramienta —el Design Decision Points— que nos ayuda a documentar las decisiones."

"**Configuración:** Después de definir el alcance, arrancamos con la configuración de los módulos. Necesitaremos acceso al tenant —idealmente un administrador de seguridad o de nube— durante las sesiones de configuración."

"**Duración:** Todo el proceso dura aproximadamente 5 semanas. La fase de recolección de datos es automática — ustedes no tienen que hacer nada durante ese tiempo."

"**Recursos:** Si quieren prepararse, pueden revisar los módulos de readiness en Microsoft Learn. Los enlaces están en la documentación que compartimos."

*(Pausa)*

**Formador:** "Y lo más importante: esto es de ustedes. Si en cualquier momento sienten que el taller no está alineado con sus prioridades, díganlo. No tenemos problema en ajustar el rumbo."

---

## BLOQUE 10 — Q&A Y CIERRE (5 min)

*(Diapositiva 20 — Q&A / Diapositiva 21 — Thank you)*

**Formador:** "Hasta acé mi parte. Ahora quiero escucharlos."

*(Abre la ronda de preguntas. Deja espacio. No apresurar.)*

**Formador:** "¿Preguntas? ¿Dudas? ¿Algo que no haya quedado claro?"

*(Después de las preguntas — o si no hay, pasar al cierre)*

**Formador:** "Para cerrar, quiero dejarles una reflexión breve."

*(Pausa. Tonos pausado.)*

**Formador:** "La nube no es más insegura que on-premise. Pero es DISTINTA. Y lo que funcionaba antes —firewalls perimetrales, controles manuales, revisiones anuales— no alcanza."

"Este taller es una oportunidad para entender dónde están sus brechas reales, no las que imaginan. Porque lo peor que puede pasar no es descubrir que algo está mal. Es no descubrirlo."

*(Sonrisa. Tonos cálido.)*

**Formador:** "Gracias por su tiempo y su atención. Vamos a hacer un gran trabajo juntos."

*(Fin de la sesión)*

---

## ANEXO A: POSIBLES PREGUNTAS Y RESPUESTAS

**P: "¿Esto va a generar costos en nuestra suscripción de Azure?"**
R: "Buena pregunta. El taller activa planes de Defender for Cloud que tienen un trial gratuito de 30 días por suscripción. Si su suscripción ya usó el trial, evaluamos opciones — o usamos otra suscripción con trial disponible, o cubrimos los costos. No activamos nada sin antes mostrarles el estimado de costos."

**P: "¿Qué pasa si durante el taller descubrimos una amenaza activa crítica?"**
R: "Les mostramos el hallazgo, les explicamos qué significa, y les recomendamos acciones. Pero NO actuamos sin su autorización. Cualquier respuesta —bloquear, aislar, parchear— la decide y ejecuta su equipo."

**P: "¿Podemos quedarnos con las herramientas configuradas después del taller?"**
R: "Sí. El decommissioning es opcional. Muchos clientes eligen quedarse con la configuración. Solo tengan en cuenta que, pasados los 30 días de trial, los planes empiezan a facturar. Si quieren continuar, podemos ayudarlos con el proceso."

**P: "Solo tenemos recursos en Azure, no en AWS o GCP. ¿Sirve igual?"**
R: "Absolutamente. El taller está diseñado para Azure nativo. El soporte multicloud es adicional si tienen recursos ahí."

**P: "Nuestro equipo de seguridad es pequeño. ¿Esto nos va a desbordar?"**
R: "Al revés. El taller automatiza el descubrimiento y priorización de riesgos. No aumenta su carga operativa — la enfoca en lo que realmente importa."

**P: "Usamos otro CNAPP. ¿Tiene sentido hacer este taller?"**
R: "Sí, porque el valor no está solo en las herramientas sino en el diagnóstico. Además, la integración de Defender for Cloud con el ecosistema Microsoft (M365 Defender, Sentinel, Purview) es un diferenciador que ningún CNAPP independiente ofrece. Al final, ustedes comparan y deciden."

---

## ANEXO B: LENGUAJE SENCILLO — CONCEPTOS CLAVE

*(Para usar si el público pide profundizar en términos)*

| Término | Explicación sencilla |
|---------|---------------------|
| **CSPM** | Un scanner que revisa que sus recursos en la nube estén bien configurados y no tengan puertas abiertas |
| **CNAPP** | CSPM + detección de amenazas + protección de cargas de trabajo, todo en una plataforma |
| **Secure Score** | Un número del 0 al 100 que dice qué tan segura está su configuración de nube |
| **Attack Path** | La ruta que un atacante podría seguir para llegar a su recurso más crítico |
| **Workload** | Cualquier cosa que corre en la nube: una VM, una base de datos, un contenedor, una app |
| **Agentless Scanning** | Analizar discos de VMs sin instalar nada dentro de ellas |
| **Caminos de ataque** | Como el recorrido que haría un ladrón: ventana abierta → puerta sin llave → caja fuerte sin candado |

---

## ANEXO C: DATOS DE APOYO

*(Para respaldar argumentos si el público lo pide)*

- **80%** de las brechas de seguridad involucran datos en la nube (Verizon DBIR)
- **99%** de los incidentes de seguridad en la nube son causados por configuraciones incorrectas, no por hackers sofisticados (MITRE)
- Las organizaciones que usan CSPM reducen el tiempo de remediación en un **60%** (Forrester)
- El costo promedio de una brecha en la nube es **$4.8 millones** (IBM)
- **66%** de las organizaciones reportan que la visibilidad multicloud es su mayor desafío de seguridad (McAfee)
- Defender for Cloud cubre **más de 50 regulaciones** de cumplimiento normativo (SOC 2, PCI DSS, ISO 27001, etc.)

---

*Fin del Guion del Formador — Sesión 1: Kickoff | Cloud Security Envisioning Workshop*
