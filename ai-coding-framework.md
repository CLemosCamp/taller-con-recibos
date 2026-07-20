> Versión de lectura del documento original de marzo de 2025 — [PDF original](ai-coding-framework.pdf). Transcripción fiel, sin actualizaciones.

**CHVR Labs** — **23/Marzo/2025** — **Cristopher Lemos**

# Ai Coding Framework

Este framework está diseñado para construir software documentado y testeado para usuarios poco técnicos o para usuarios técnicos que se quieran ahorrar unas horas.

# Fase de diseño de producto

En esta fase debes de poner los puntos sobre las íes de tu solución. Al finalizar esta fase debes de tener el documento de Definición de producto detallada.
Para lograr esto debes de entender muy bien tu problema. Preguntas como las siguientes tienes que tenerlas muy claras, si no, te va a tocar pensar mucho en ellas:

1. ¿Quién es tu público objetivo?
2. ¿Qué es lo que les duele?
3. ¿Por qué cambiarían lo que están haciendo ahora por tu solución?
4. ¿Les vas a ahorrar dinero?
   a. ¿Es fácilmente cuantificable cuánto les vas a ahorrar?
   b. ¿Tiene que haber labor de convencimiento para que crean que les vas a ahorrar dinero?
5. ¿Qué problema les vas a solucionar?
6. ¿Cómo lo vas a solucionar?
   a. ¿Hay otros componentes de tecnología involucrados?
   b. ¿Tus usuarios son adeptos a la tecnología?
   c. ¿Tu mercado tiene el digital literacy para usar tu producto?
7. ¿Cuáles son los elementos de tu solución?
8. ¿Cómo se comunican entre sí los elementos de tu solución?
9. ¿Quién le escribe/pregunta/escucha qué a quién?
10. ¿Qué tiene que hacer cada elemento?

Una vez teniendo estas preguntas claras debes de proceder a escribir tu definición del producto:

1. Las preguntas del punto 1 te pueden ayudar a definir tu solución.
2. Si eres un usuario poco técnico te recomiendo completar en la rango i - vi
3. Si eres un usuario técnico, las preguntas del vii - x te pueden ayudar a estructurar tu documento de definición.

Una vez habiendo escrito tus definiciones iniciales el siguiente paso es rebotarla con un modelo de razonamiento (yo uso O1, pero claude sonnet 3.7 thinking tiene buen rendimiento también).

1. Recomendaciones de peticiones a O1:
   a. Solicítale que te ayude a profundizar sobre tus definiciones de negocio.
   b. Solicítale que te haga preguntas acerca de tu producto para mejorar tus definiciones de negocio
   c. Explícale que este documento luego será usado por desarrolladores para construir la solución.

Finalmente debes de guardar tu definición en un documento en forma ".md" dentro del repositorio (carpeta) para luego poder rebotar con cursor o windsurf.

# Fase de diseño técnico

En esta fase debes aterrizar la definición técnica. Al finalizar esta fase debes de tener los siguientes documentos:

1. Arquitectura de la solución
2. Plan de implementación
3. Documento detallando estructura de documentación
4. Documento detallando estructura de pruebas

## Arquitectura de la solución

Con ayuda de cursor o windsurf debes de construir la arquitectura de tu producto. Debes solicitarle que:

1. Basado en tu definición de producto te ayude a construir la arquitectura de tu solución.
2. Solicítale que te haga preguntas acerca de tu producto y tus necesidades.
3. Recuerda que tu arquitectura debe considerar:
   a. Elementos de la solución
   b. Cómo se comunican entre ellos
   c. Inputs del sistema
   d. Operaciones intermedias
   e. Outputs del sistema

## Plan de implementación

En este plan de implementación debes pedir que considere lo siguiente:

1. En este plan de implementación debes de dividir (con ayuda de cursor o windsurf) tu solución en fases. Dependiendo de la complejidad de tu solución puedes pedir lo siguiente:
   a. **Solución sencilla** con pocos detalles técnicos, sin necesidades especiales de seguridad, concurrencia, escalabilidad: **5 - 6 fases** de desarrollo.
   b. Solución intermedia con varios puntos de integración, con varios modulos, que involucren varios clientes: **10 - 12 fases**
   c. Soluciones complejas: en este caso recomiendo subdividir tu solución en elementos más pequeños. **(Otro artículo en cómo lograr esto)**
2. Para la división en fases debes de indicar que como te gusta construir productos es:
   a. Construir pruebas
   b. Construir funcionalidad
   c. Construir documentación
3. Es importante que construyamos una funcionalidad a la vez. Debes de mencionar esto en el plan de implementación.
4. Debes de solicitarle que dentro del plan de implementación te muestre el avance de las fases del proyecto:
   a. Debes pedirte que sea conciso y te muestre solo el nivel de granularidad necesario y el número de avance
   b. Las reglas para considerar una fase completada son:
      i. Funcionalidad 100% implementada
      ii. Funcionalidad 100% documentada
      iii. Funcionalidad 95% testeada
5. Debes pedirle que guarde este documento en formato .md dentro de la carpeta de documentación del proyecto. Tu documento debe de contener lo siguiente:
   a. Resumen ejecutivo
   b. Estado de fases del proyecto
   c. Próximos pasos
   d. Historial de actualizaciones
6. Debes solicitarle que actualice el documento después de finalizar cada fase. Cuando actualice el plan debes pedirle que mantenga el mismo formato que ya tiene la documentación. Debemos evitar hacer cambios a la documentación y la arquitectura a menos que sean estrictamente necesarios.

## Estructura de documentación

Debes solicitar que te ayude a construir una estructura de documentación que considere:

1. Documentación detallada para **todos** los componentes de tu solución. Cada archivo nuevo que se cree, cada servicio, cada parte de tu documentación debe estar documentada.
2. Yo utilizo una estrategia de documentación donde guardo toda mi documentación en una carpeta `/docs/` y luego una estructura de carpetas "espejo".
3. Debes pedir que actualice la documentación cada que hagas un cambio en tu código. (Es más caro en tokens, pero es más barato en bugs).
4. Cuando actualice la documentación debes pedirle que mantenga el mismo formato que ya tiene la documentación. Debemos evitar hacer cambios a esta documentación y la arquitectura a menos que sean estrictamente necesarios.
5. Tu estructura de documentación debe considerar lo siguiente:
   a. Estructura de carpetas
   b. Tipos de documentación
   c. Templates de documentación
   d. Herramientas de automatización
6. Al final tu documento de estrategia de documentación debes de guardarlo en formato md dentro de tu carpeta de documentación.

## Estructura de pruebas

Debes solicitar que te ayude a construir una estructura de pruebas que considere:

1. Todos los componentes de tu solución deben de ser testeado y debemos llegar a un coverage de +95%
2. Tu documento de pruebas debe de contener lo siguiente:
   a. Estructura de carpetas
   b. Tipos de pruebas
   c. Coverage
   d. Convenios de nomenclatura
   e. Fixtures y mocks
   f. Herramientas de automatización
   g. Guías para pruebas
3. Al final tu documento de estrategia de documentación debes de guardarlo en formato md dentro de tu carpeta de documentación.

# Fase de construcción

La arquitectura, estructura de documentación, estructura de pruebas y documento de seguimiento que hemos creado en la fase de diseño técnico, nos ayudarán a que la construcción sea más fluida, rápida y fácil de debuggear.
Para empezar a construir tu solución debes de solicitarle al modo agente de cursor o de windsurf que empiece a construir tu solución con la fase 1. En este chat debes de darle toda la documentación que hemos creado hasta este punto para que tenga el contexto adecuado y construir tu solución. Adicional debes de decirle que te haga todas las preguntas necesarias para puntualizar este componente o fase.
Usualmente la fase 1 que te va a sugerir cursor o windsurf van a ser la creación de la estructura de carpetas del repo:

- Es fundamental que la estructura que se cree considere la estructura de la documentación y pruebas que hemos definido en el punto anterior.

A partir de la siguiente fase debes de considerar que la forma de construir tu solución debe ser por fases o funcionalidades. Vamos a inspirarnos en una estrategia llamada extreme programming y seguir los siguientes pasos para construir:

1. Construir pruebas
2. Construir funcionalidad
3. Correr las pruebas
4. Construir documentación

Es muy importante que construyamos una funcionalidad a la vez. Debes mencionar esto en el chat con el agente.
Una vez que el agente haya construido tanto las pruebas como la funcionalidad, debes solicitarle que corra las pruebas. Aquí te van a empezar a salir bugs y simplemente le dejas a cursor o windsurf que las resuelva.
Es muy importante que todas las pruebas pasen antes de construir la documentación, para que nuestra documentación sea lo más alineada posible.
Si en el proceso de construcción, se cambian otras partes de tu producto, debes solicitar que se actualice esa documentación también.
Al finalizar cada funcionalidad debes pedir que actualice el documento de plan de implementación, para siempre tener una vista actual de donde estamos parados.

# Tips adicionales

- Si no sabes en qué fase estás puedes pedirle a tu IDE que haga un assesment del avance en cualquier momento.
- Usa chats separados para cada funcionalidad, porque puede perderse entre tanto contexto.
- El "ask" te puede servir para alinear dudas. El "agente" hará todo el trabajo automáticamente por tí.
