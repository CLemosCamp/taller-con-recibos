# Prompts para desarrolladores

**Cristopher Lemos · ENERO 2025**

> Versión markdown (julio 2026) del deck original de enero de 2025. Material preparado originalmente en Iguana Digital, el estudio digital de mi familia, donde soy socio y asesor.
>
> Canónico textual: [ver el .md en GitHub](https://github.com/CLemosCamp/taller-con-recibos/blob/main/prompts-para-desarrolladores.md).

---

## Contenido

Técnicas de prompting:

1. Zero-Shot Prompting
2. Few-Shot Prompting
3. Chain-of-Thought Prompting
4. Meta Prompting

Además:

- Plus: solicitar que el modelo refine tu prompt (Self-Reflective / Iterative Refinement Prompting)
- Framework de prompts: CO-STAR
- Notebooks: Google Colab

---

## Técnicas de prompting

Existen varias técnicas de prompting útiles. En esta sesión vamos a explorar 4 de ellas:

- Zero-Shot Prompting
- Few-Shot Prompting
- Chain-of-Thought Prompting
- Meta Prompting

En el siguiente link podemos encontrar una guía con más técnicas de prompting:

- <https://www.promptingguide.ai/techniques>
- <https://www.techtarget.com/searchenterpriseai/definition/chain-of-thought-prompting>

---

## Zero-shot prompting

El entrenamiento a gran escala hace que estos modelos sean capaces de realizar algunas tareas de manera "zero-shot" (sin ejemplos previos). El enfoque zero-shot significa que el prompt utilizado para interactuar con el modelo no contiene ejemplos ni demostraciones. El prompt zero-shot instruye directamente al modelo para realizar una tarea sin incluir ejemplos adicionales que lo guíen.

**Input:**

```
Clasifica el texto como neutral, negativo o positivo.
Texto: Creo que las vacaciones están bien.
Sentimiento:
```

**Output esperado:** Neutral

---

## Few-shot prompting

Aunque los modelos de lenguaje a gran escala demuestran capacidades notables en configuraciones zero-shot, todavía presentan limitaciones en tareas más complejas al usar este enfoque. La técnica de few-shot prompting se puede utilizar para habilitar el aprendizaje en contexto, proporcionando demostraciones en el prompt que guíen al modelo hacia un mejor rendimiento. Las demostraciones sirven como condicionamiento para ejemplos posteriores en los que se espera que el modelo genere una respuesta.

**Input:**

```
¡Esto es increíble! // Positivo
¡Esto es malo! // Negativo
¡Guau, esa película estuvo genial! // Positivo
¡Qué espectáculo tan horrible! //
```

**Output esperado:** Negativo

---

## Chain-of-thought prompting

El chain of thought prompting es una técnica que permite a los modelos de lenguaje generar respuestas más precisas y coherentes para tareas complejas al incentivar un razonamiento paso a paso. En lugar de proporcionar solo una instrucción o ejemplos aislados, el prompt guía al modelo para desglosar el problema en una secuencia lógica de pasos intermedios antes de llegar a la respuesta final. Este enfoque mejora el rendimiento en tareas que requieren razonamiento matemático, deducción lógica o análisis más profundo.

Ejemplo de uso con un modelo de lenguaje:

**Entrada:**

```
Un granjero tiene 15 manzanas. Decide dar 3 manzanas a cada uno de sus 4 hijos. ¿Cuántas manzanas le quedan?
```

**Salida esperada:**

```
Primero, calculamos cuántas manzanas da el granjero en total. Si cada hijo recibe 3 manzanas y hay 4 hijos:
3 x 4 = 12 manzanas.
Luego, restamos las manzanas que dio del total que tenía:
15 - 12 = 3 manzanas.

Respuesta final: El granjero se queda con 3 manzanas.
```

Este enfoque enseña al modelo a razonar progresivamente, facilitando una respuesta más precisa incluso en tareas complejas.

### Ejemplo de prompt

**Instrucción general:** Responde las siguientes preguntas y explica tu razonamiento paso a paso antes de dar una respuesta final.

**Ejemplos en el prompt:**

```
Pregunta: Un tren viaja a 60 km/h y tarda 2 horas en llegar a su destino. ¿Qué distancia recorre el tren?
Razonamiento: La velocidad del tren es de 60 km/h. Esto significa que en una hora recorre 60 km. Como tarda 2 horas, multiplicamos la velocidad por el tiempo:
60 km/h × 2 h = 120 km.
Respuesta: El tren recorre 120 km.

Pregunta: Si tienes 20 caramelos y das 4 caramelos a cada uno de tus 5 amigos, ¿cuántos caramelos te quedan?
Razonamiento: Primero, calculamos cuántos caramelos repartiste en total. Multiplicamos la cantidad de caramelos por amigo (4) por el número de amigos (5):
4 × 5 = 20 caramelos.
Luego, restamos los caramelos que repartiste del total que tenías:
20 - 20 = 0 caramelos.
Respuesta: Te quedan 0 caramelos.
```

**Nueva entrada (para que el modelo aplique el patrón):**

```
Pregunta: Un grupo de 8 personas comparte una cuenta de restaurante de $240 de manera equitativa. ¿Cuánto debe pagar cada persona?
```

**Resultado esperado:**

```
Razonamiento: El total de la cuenta es $240, y se divide equitativamente entre 8 personas. Para calcular cuánto paga cada persona, dividimos el total entre el número de personas:
240 ÷ 8 = 30.
Respuesta: Cada persona debe pagar $30.
```

---

## Meta prompting

El meta prompting es una técnica avanzada que guía a un modelo de lenguaje a adoptar un comportamiento específico o un enfoque en sus respuestas al incluir instrucciones sobre cómo razonar o estructurar su salida dentro del propio prompt. Este método utiliza "metacognición" (pensamiento sobre el pensamiento) para instruir al modelo sobre cómo abordar una tarea, asegurando que siga un proceso más reflexivo y estructurado.

En esencia, el modelo no solo responde a la pregunta principal, sino que primero define su enfoque para resolver el problema, lo que permite un razonamiento más claro y deliberado.

### Ejemplo de meta prompting

**Instrucción general:** Antes de responder a cualquier pregunta, reflexiona sobre la tarea, identifica los pasos necesarios para resolverla y luego proporciona tu respuesta final basada en ese razonamiento.

**Ejemplos en el prompt:**

```
Pregunta: ¿Cuántos días hay en 3 semanas?
Reflexión: Primero, necesito recordar que una semana tiene 7 días. Luego, debo multiplicar el número de semanas (3) por la cantidad de días en una semana (7).
Cálculo: 3 × 7 = 21 días.
Respuesta: Hay 21 días en 3 semanas.

Pregunta: Si un coche consume 5 litros de gasolina por cada 100 kilómetros y el tanque tiene 40 litros, ¿qué distancia puede recorrer con un tanque lleno?
Reflexión: Primero, necesito determinar cuántos kilómetros puede recorrer con 1 litro de gasolina. Luego, multiplicaré esa distancia por la capacidad del tanque.
Cálculo: Con 1 litro, el coche recorre 100 ÷ 5 = 20 kilómetros. Con 40 litros, recorrerá 40 × 20 = 800 kilómetros.
Respuesta: El coche puede recorrer 800 kilómetros con un tanque lleno.
```

**Nueva entrada (para que el modelo aplique el patrón):**

```
Pregunta: Una panadería produce 150 panes al día. Si trabaja 6 días a la semana, ¿cuántos panes produce en una semana?
```

**Resultado esperado:**

```
Reflexión: Primero, necesito calcular cuántos panes produce la panadería en un día y luego multiplicar esa cantidad por los días que trabaja en una semana.
Cálculo: 150 × 6 = 900 panes.
Respuesta: La panadería produce 900 panes en una semana.
```

---

## Plus: solicitar que el modelo refine tu prompt

Esta técnica se llama "Self-Reflective Prompting" o "Iterative Refinement Prompting", y consiste en usar el modelo de lenguaje para colaborar en la mejora de un prompt inicial. En este enfoque, el modelo actúa como un asistente crítico que plantea preguntas, sugiere ajustes o identifica lagunas en el prompt inicial, ayudándote a definir el mejor prompt para tu caso específico.

**¿Cómo funciona?**

1. **Inicia con un prompt básico:** proporcionas al modelo un primer borrador del prompt que tienes en mente.
2. **Solicita retroalimentación:** pides al modelo que formule preguntas o sugiera mejoras para aclarar, especificar o ampliar el alcance del prompt.
3. **Itera sobre el diseño:** basándote en las preguntas y sugerencias del modelo, ajustas el prompt y repites el proceso hasta que estés satisfecho con el resultado.

### Ejemplo de uso

**Entrada inicial:**

```
Estoy intentando diseñar un prompt que haga que el modelo resuma artículos largos en un lenguaje simple y apto para niños. Por favor, hazme preguntas o proporciona sugerencias para refinar este prompt y hacerlo más efectivo.
```

**Respuesta del modelo:**

```
¿Qué nivel de comprensión de los niños esperas? (por ejemplo, edad o grado escolar).
¿Prefieres un resumen muy breve o un resumen que incluya ciertos detalles clave?
¿Hay palabras o temas específicos que debería evitar para mantener el lenguaje apropiado para niños?
¿Cuánto énfasis debería dar el modelo a la claridad frente a la precisión del contenido original?
¿Debería seguir algún formato especial, como párrafos o listas con viñetas?
```

**Ajuste del prompt:**

```
Por favor, resume el siguiente artículo en lenguaje simple para niños de entre 8 y 10 años. Mantén las oraciones cortas y usa palabras fáciles de entender. Evita temas complejos o inadecuados para esta edad. Proporciona el resumen como una lista de 3 a 5 viñetas para facilitar su lectura.
```

### Caso práctico con un modelo de lenguaje

**Primera entrada:**

```
Estoy diseñando un prompt para generar ideas creativas para campañas publicitarias en redes sociales. Ayúdame a refinarlo formulando preguntas o sugiriendo mejoras.
```

**Posible respuesta del modelo:**

```
¿Qué tipo de producto o servicio estás promocionando?
¿Cuál es tu público objetivo? (edad, intereses, etc.)
¿Prefieres ideas para campañas específicas de una plataforma o multiplataforma?
¿Qué tono o estilo debe tener la campaña (divertido, serio, educativo, etc.)?
¿Hay algo que definitivamente debería incluirse o evitarse?
```

---

## Framework de prompts: CO-STAR

**Autor del framework: Sheila Teo.** Marco creado por el equipo de Ciencia de Datos e IA de GovTech Singapur.

La estructura efectiva de prompts es clave para obtener respuestas óptimas de un modelo de lenguaje grande (LLM). El marco CO-STAR es una plantilla útil que abarca los aspectos clave para mejorar la efectividad y relevancia de las respuestas del LLM. Sus componentes son:

- **Contexto (C):** proporcionar información de fondo sobre la tarea para que el LLM comprenda el escenario específico y dé respuestas relevantes.
- **Objetivo (O):** definir claramente la tarea que quieres que el LLM realice para enfocar su respuesta en cumplir ese objetivo.
- **Estilo (S):** especificar el estilo de escritura deseado, como el de un analista de negocios, un CEO, o un personaje famoso, para guiar la forma en que el modelo responde.
- **Tono (T):** determinar la actitud o el sentimiento de la respuesta, como formal, humorístico o empático, para alinear el mensaje con el contexto emocional requerido.
- **Audiencia (A):** identificar quién recibirá la respuesta (expertos, principiantes, niños, etc.) para asegurar que sea apropiada y comprensible.
- **Formato de respuesta (R):** especificar el formato deseado (lista, JSON, informe profesional, etc.) para cumplir con las necesidades posteriores.

### Ejemplo de prompt

> **Nota:** el framework CO-STAR es de Sheila Teo y el equipo de GovTech Singapur. El ejemplo original de Sheila Teo (empresa "Alpha", secador "Beta", estilo Dyson) se adaptó aquí a un caso equivalente del universo del taller —una distribuidora que surte tienditas— manteniendo idéntica la estructura CO-STAR.

```
# CONTEXTO #
Quiero promocionar una nueva promoción de mi distribuidora entre las tienditas que surto. El nombre de mi distribuidora es Surtimás y la promoción se llama Combo Abarrote, un paquete de productos de alta rotación con precio preferente y entrega al día siguiente.

# OBJETIVO #
Crear una publicación para redes sociales que motive a los tenderos a pedir el Combo Abarrote a través de la app de pedidos.

# ESTILO #
Sigue el estilo de comunicación de distribuidoras exitosas que hablan directo al comerciante de barrio, con mensajes claros y prácticos.

# TONO #
Cercano y persuasivo.

# AUDIENCIA #
El público son dueños de tienditas de barrio que buscan surtir rápido, cuidar su margen y no quedarse sin producto. Adapta la publicación para enfocarte en lo que este público suele buscar: ahorro, rapidez y productos que se venden solos.

# RESPUESTA #
La publicación para redes sociales debe ser concisa pero impactante.
```

---

## Notebooks: Google Colab

El taller se acompaña de notebooks en Google Colab para practicar las técnicas anteriores de forma interactiva.

## Referencias

- Técnicas de prompting (zero-shot, few-shot, meta) y ejemplos — <https://www.promptingguide.ai/techniques>
- Chain-of-thought prompting (definición) — <https://www.techtarget.com/searchenterpriseai/definition/chain-of-thought-prompting>
- Framework CO-STAR — Sheila Teo · equipo de Ciencia de Datos e IA de GovTech Singapur

---

*Prompts para desarrolladores · Cristopher Lemos · enero 2025 · versión markdown julio 2026*
