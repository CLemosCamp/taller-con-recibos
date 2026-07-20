# Creación de prototipos

**Cristopher Lemos** · Julio 2025

> Versión markdown (julio 2026) del deck original de julio de 2025.

## El proceso de un vistazo — Agenda

| Paso | |
|---|---|
| 1 | Alinear la hipótesis y el problema |
| 2 | Journey |
| 3 | Storyboard |
| 4 | Construir el prototipo |
| 5 | Validación |

## 1. Alinear la hipótesis y el problema

**Objetivo:** asegurar que todo el equipo comparta la misma pregunta a responder.

### Técnicas clave

- **Problem Statement** (formato "Para ___ que tienen ___, nuestra solución ___").
- **Lean Hypothesis** (si [x] entonces [y] medido por [z]). [Referencia](https://www.optimizely.com/optimization-glossary/lean-hypothesis-testing/).
- **Jobs-to-Be-Done interview snippets** para descubrir motivaciones. [Referencia](https://www.productplan.com/glossary/jobs-to-be-done-framework/).

### Artefactos

- One-pager con hipótesis, público objetivo y métrica de éxito (North Star).
- Lista priorizada de supuestos críticos (Assumption Backlog).

### Ejemplos de problem statement

#### 1. Problem Statement

> "En una app de pedidos para distribuidoras, el 38 % de los tenderos abandona el proceso de pedido antes de completar el segundo paso. Esto genera una pérdida estimada de 2000 pedidos semanales y reduce la satisfacción del cliente (NPS −12 puntos) frente al promedio de la industria."

Estructura cubierta:

- **Qué ocurre:** alto abandono en pedidos.
- **Quién se ve afectado:** tenderos que usan la app de pedidos.
- **Impacto medible:** 2000 pedidos perdidos y NPS bajo.
- **Por qué importa:** afecta ingresos y fidelidad.

#### 2. Lean Hypothesis

> Si simplificamos el flujo de pedido a un solo paso (X), entonces la tasa de finalización aumentará un 15 % (Y) medida por la métrica "order_completion_rate" durante 4 semanas (Z).

Fórmula:

- **Si [X]** → acción o cambio.
- **Entonces [Y]** → resultado esperado.
- **Medido por [Z]** → métrica y periodo.

#### 3. Jobs-to-Be-Done — Entrevista (snippet)

> **Contexto reciente**
> "Cuéntame sobre la última vez que necesitaste surtir tu tiendita con urgencia. ¿Qué sucedía ese día?"
>
> **Motivaciones y obstáculos**
> "¿Qué estabas pensando cuando elegiste la app para hacer el pedido? ¿Qué te frustró en el camino?"
>
> **Resultados deseados**
> "¿Cómo sabías que el pedido había sido un éxito? ¿Qué habría hecho la experiencia 'perfecta' para ti?"

Por qué funciona:

- Se ancla en un evento específico ("última vez").
- Explora emociones, no solo pasos.
- Destapa criterios de éxito y fallas percibidas.

## 2. Journey

**Objetivo:** visualizar el flujo completo y qué aprender en cada punto.

### Técnicas clave

- **Customer Journey Map** rápido enfocando "momentos de verdad".
- **Story Mapping** de Jeff Patton: pasos horizontales + profundidad vertical.
- **Experiment Canvas** para cada parte del flujo (prototipo ≠ producto final).

### Artefactos

- Storyboard de 6-8 viñetas.
- Matriz "Parte del prototipo ↔ supuesto ↔ métrica de validación".

### Customer Journey Map: el tendero surte su tienda

| | 1. Necesidad | 2. Contacto | 3. Armado del pedido | 4. Confirmación | 5. Entrega |
|---|---|---|---|---|---|
| **Acciones** | Detecta faltantes en el anaquel | Abre la app y consulta el catálogo | Agrega productos al carrito | Revisa el total y confirma el pedido | Recibe y verifica la mercancía |
| **Emoción** | Urgencia por no perder ventas | Expectativa: ¿habrá stock? | Duda con precios y presentaciones | Alivio si el resumen es claro | Satisfacción si llega completo |
| **Oportunidades** | Alertas de re-surtido | Búsqueda rápida y favoritos | Sugerencias y combos | Confirmación en un solo paso | Seguimiento de la entrega |

## 3. Storyboard

**Objetivo:** bajar el riesgo técnico y de usabilidad al mínimo coste.

### Técnicas clave

- **Crazy-8s** o **Design Studio** para generar variantes rápidas. [Referencia](https://www.uifrommars.com/guia-completa-crazy-8s/).
- **Service Blueprint** sencillo (frontstage / backstage) si hay servicio humano.
- "Riesgo primero": ordenar qué se prototipa según impacto × incertidumbre.

### Artefactos

- Wireframes de baja fidelidad (papel o FigJam).
- Criterios de test cut-off (qué invalida la hipótesis).

### Storyboard en 6 viñetas: un pedido en la app

1. **La necesidad** — El tendero nota que se acaban varios productos
2. **El acceso** — Abre la app de pedidos de su distribuidora
3. **El armado** — Busca productos y los agrega al carrito
4. **La confirmación** — Revisa el resumen y confirma en un paso
5. **La espera** — Recibe confirmación con fecha de entrega
6. **El cierre** — Recibe el pedido y verifica que esté completo

## 4. Construcción del prototipo

**Objetivo:** crear algo lo bastante real para gatillar la reacción deseada.

### Técnicas clave

- **Fidelity ladder:** empieza en papel → clickeable (Figma/InVision) → Wizard-of-Oz/Concierge.
- Reutilizar **Design System** o UI kits para acelerar.
- Definir **"Golden Path"** (flujo feliz) y fakear el resto.

### Artefactos

- Prototipo interactivo + guía de navegación.
- Registro de cambios con fecha e hipótesis asociada ("Build-Measure" log).

## 5. Validación

### Entrevistas y pruebas de validación

**Objetivo:** medir si el prototipo resuelve el problema y aprender por qué/por qué no.

#### Técnicas clave

- **Customer Discovery Interview** (problema antes que solución; 5 por ronda).
- **Think-Aloud Usability Test** (3-5 usuarios revelan 80 % de issues).
- **5-Second Test** para primera impresión y mensaje.
- **RICE** o **Confidence Meter** post-test para decidir siguiente paso.

#### Artefactos

- Guía de entrevista + script de tareas.
- Tablero de capturas (quotes, pain points, delight).
- Learning Card:

> ✓ **Learning Card**
> "Esperábamos ___, observamos ___, aprendimos ___, decidimos ___"

### Cierre del experimento y decisión

**Objetivo:** transformar los hallazgos en acción clara.

#### Técnicas clave

- Taller **"Stop / Start / Continue"**.
- **Pivot-or-Persevere meeting** (máx. 30 min; votación basada en evidencia).

#### Artefactos

- Resumen de insights ↔ hipótesis (1 diapositiva por hipótesis).
- Roadmap de siguiente sprint de descubrimiento o construcción.

---

creación de prototipos · jul 2025 · versión markdown jul 2026
