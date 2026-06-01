# Notas del Orador — Sesión 1: Kickoff
## Cloud Security Envisioning Workshop

---

### Diapositiva 1 — Portada: Cloud Security Envisioning Workshop

**Notas del orador:**

Bienvenida. Sonrisa natural. Contacto visual.

"Gracias por estar acá. Reunir a seguridad, infraestructura, nube y negocio en una misma sala no es fácil — así que valoramos el esfuerzo."

"Me llamo [Nombre]. Hoy arrancamos el Cloud Security Envisioning Workshop. No es una presentación comercial. Es un diagnóstico práctico de 3 semanas."

**Tono:** Cálido, agradecido, enérgico pero sin apuro.

---

### Diapositiva 2 — Latest Version

**Notas del orador:**

Comentario rápido, casi para sí mismo.

"Esta es para mí — significa que revisé que estoy usando la versión más reciente del taller. No se preocupen por esto."

---

### Diapositiva 3 — Feedback

**Notas del orador:**

"Y esta es para ustedes. Si algo no funciona, si algo no se entiende, si algo se siente como pérdida de tiempo — hay un enlace directo al equipo que construye este taller. Úsenlo sin miedo. El feedback mejora el taller para todos."

---

### Diapositiva 4 — Version History

**Notas del orador:**

"Este taller arrancó en septiembre 2025. Ya vamos por la versión 1.1. Es un taller vivo — evoluciona con los productos."

"Pero basta de slides administrativas. Vamos al contenido."

---

### Diapositiva 5 — Engagement Overview (section header)

**Notas del orador:**

"Tres semanas. Un objetivo: darles visibilidad real de su seguridad en la nube y un plan de acción."

---

### Diapositiva 6 — Introducing the Workshop

**Notas del orador:**

"Esto es un taller práctico. Configuramos herramientas de seguridad de Microsoft directamente en su tenant de PRODUCCIÓN — no en un laboratorio."

"Recolectamos datos reales de su entorno durante 2-3 semanas."

"Al final: esto vimos, esto significa, esto recomendamos."

"Sin compromiso de compra. Sin presión comercial."

---

### Diapositiva 7 — Overview Diagram

**Notas del orador:**

"Tres momentos:"
1. "**Descubrimiento** — evaluamos postura y amenazas actuales."
2. "**Visión** — conectamos hallazgos con capacidades de Defender for Cloud."
3. "**Plan** — hoja de ruta con responsables y plazos."

"Como una resonancia magnética: la máquina escanea, genera datos, luego los médicos —ustedes— interpretan."

---

### Diapositiva 8 — What We'll Do

**Notas del orador:**

"**Analizar:** sus requisitos, su entorno, sus prioridades."
"**Definir y configurar:** seleccionamos módulos, habilitamos herramientas."
"**Descubrir amenazas:** qué está atacando sus cargas de trabajo hoy."
"**Evaluar postura:** configuraciones, cumplimiento, vulnerabilidades."
"**Planificar:** siguientes pasos concretos."

---

### Diapositiva 9 — After the Workshop

**Notas del orador:**

"Al terminar, ustedes van a:"
- "Saber priorizar y responder a las amenazas que realmente los afectan."
- "Tener visibilidad de su postura en Azure (y multicloud si aplica)."
- "Llevarse recomendaciones PERSONALIZADAS — no genéricas."
- "Tener un plan de acción con fechas y dueños."

---

### Diapositiva 10 — Objectives

**Notas del orador:**

"Tres objetivos, muy claros:"
1. "Descubrir amenazas a través de la telemetría unificada de Defender XDR."
2. "Entender la postura de seguridad en Azure, AWS y/o GCP."
3. "Definir los siguientes pasos — juntos — sin dejar un informe muerto en una carpeta."

---

### Diapositiva 11 — Modular Design

**Notas del orador:**

"Dos módulos OBLIGATORIOS + mínimo 2 SELECCIONABLES."

"**Obligatorios:**"
- "Microsoft Defender Portal — el cerebro donde converge todo."
- "CSPM — análisis de configuración, cumplimiento, rutas de ataque."

"**Seleccionables (9 opciones, eligen mínimo 2):**"
- "Servers, Databases, Storage, Containers, App Service, AI, Key Vault, APIs, Security Exposure Management."

"Vamos a ver cada uno en detalle para que tomen una decisión informada."

---

### Diapositiva 12 — Phases and Activities: Setup

**Notas del orador:**

"Semana 1: Pre-engagement (llamada inicial + cuestionario)."
"Semana 2: Setup — kickoff, definición de alcance, configuración de módulos."

"Son ~22 horas de trabajo del equipo de entrega repartidas en 5 semanas."

"La mayor parte del tiempo las herramientas trabajan solas."

---

### Diapositiva 13 — Phases: Data Collection onwards

**Notas del orador:**

"Semanas 2-4: Data Collection. Las herramientas recolectan datos. Ustedes no hacen nada — siguen con su día a día."

"Semana 5: Exploración + Resultados. Analizamos juntos los hallazgos."

"Incluye:"
- "CSPM (Secure Score, attack paths, recomendaciones)"
- "Threat Protection (incidentes, hunting, alertas)"
- "Security Exposure Management (superficie de ataque, métricas)"

"Cerramos con resultados y siguientes pasos."

---

### Diapositiva 14 — Outcomes

**Notas del orador:**

"Lo que se llevan:"
- "Resultados de exploración de amenazas."
- "Resultados de CSPM."
- "Recomendaciones priorizadas."
- "Y una hoja de ruta."

---

### Diapositiva 15 — Out of Scope

**Notas del orador:**

"Importante: lo que NO hacemos."
- "No hacemos configuraciones más allá de lo guiado."
- "No hacemos investigación profunda de amenazas."
- "Ni respuesta a incidentes."
- "Ni forense."
- "Ni implementaciones en producción."

"Esto es un diagnóstico, no una implementación completa."

---

### Diapositiva 16 — Customer Responsibilities

**Notas del orador:**

"¿Qué necesitamos de ustedes?"
- "Acceso a las personas clave — sponsor, arquitectos, admins."
- "Un sponsor ejecutivo que destrabe si hace falta."
- "Acceso al tenant de Azure."

"Sin acceso, no podemos configurar. Sin personas clave, los hallazgos no se traducen en acción."

---

### Diapositiva 17 — Pre-engagement

**Notas del orador:**

"Lo que ya hicimos: la llamada inicial y el cuestionario."

"Con base en eso, hoy estamos acá alineando expectativas."

---

### Diapositiva 18 — Project Governance

**Notas del orador:**

"¿Cómo nos organizamos?"

"**Necesitamos:**"
- "Sponsor ejecutivo: abre puertas, destraba."
- "Arquitectos: seguridad, nube, infraestructura, identidad."
- "Admins con acceso al tenant."

"**Nosotros traemos:**"
- "Arquitecto de seguridad."
- "Consultor de seguridad."
- "Project Manager (opcional)."

"Canales de comunicación: Teams, correo — lo que prefieran."

---

### Diapositiva 19 — Next Steps / Actions

**Notas del orador:**

"Vamos a dejar compromisos escritos: quién hace qué, para cuándo."

"Esto no es optional — es la única forma de que el taller no se quede en intenciones."

**Dejar tiempo para llenar la tabla con el cliente.**

---

### Diapositiva 20 — Q&A

**Notas del orador:**

"Abro la palabra. Preguntas, dudas, preocupaciones."

"Prefiero que se vayan con todo claro a que tengan que escribirme después."

**Prepárate para:**
| Pregunta | Respuesta |
|----------|-----------|
| ¿Genera costos en Azure? | Trial 30 días. Si ya se usó, evaluamos opciones antes de activar. |
| ¿Y si encontramos una amenaza activa? | Mostramos, recomendamos, pero NO actuamos sin autorización. |
| ¿Podemos quedarnos con las herramientas? | Sí. Decommissioning opcional. Solo tengan en cuenta que después del trial se factura. |
| ¿Sirve si solo tenemos Azure? | Sí. El taller es Azure-native. Multicloud es adicional. |
| Somos equipo pequeño | Justamente para eso está diseñado. Automatiza el trabajo pesado. |

---

### Diapositiva 21 — Thank You

**Notas del orador:**

**Cierre emocional, pausado:**

"La nube no es más insegura que on-premise. Pero es DISTINTA."

"Lo que funcionaba antes —firewalls perimetrales, revisiones anuales— no alcanza."

"Este taller es una oportunidad para encontrar las brechas reales, no las que imaginan."

"Porque lo peor no es descubrir que algo está mal. Es no descubrirlo."

"Gracias. Vamos a hacer un gran trabajo."

---

## MAPA MENTAL DEL FORMADOR

```
BIENVENIDA (5 min) → HISTORIA CAJA FUERTE (5 min) → QUÉ ES EL TALLER (10 min)
  → DESAFÍO NUBE (10 min) → MÓDULOS (15 min) → FASES (10 min)
  → SIN IMPACTO (5 min) → GOBIERNO (10 min) → LOGÍSTICA (5 min) → Q&A (5 min)

FRASE CLAVE: "La caja fuerte ahora está en el garaje de una casa en las afueras."
FRASE DE CIERRE: "Lo peor no es descubrir que algo está mal. Es no descubrirlo."

ANALOGÍA CENTRAL: Resonancia magnética → la máquina escanea, genera datos,
                  los médicos (cliente) interpretan y deciden tratamiento.
```

---

*Fin de las Notas del Orador — Sesión 1: Kickoff | Cloud Security Envisioning Workshop*
