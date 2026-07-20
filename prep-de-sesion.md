# Plantilla · Prep de sesión de descubrimiento

Una sesión se diseña alrededor de las **salidas** (con qué te vas), no de los temas que se conversan. Cada salida es un entregable verificable; al cierre, el resultado se puntúa contra la lista.

Dos piezas hacen el trabajo pesado:

- **Regla de oro** — la única cosa irremplazable de la sesión. Se nombra antes de entrar y se custodia en vivo, no sólo en el plan.
- **Orden de sacrificio** — qué se recorta primero cuando el tiempo aprieta, para que el recorte no lo decida el reloj.

Copia lo de abajo y sustituye.

```markdown
# Prep · <sesión> · <fecha> · <cliente>
> Interno. Encuadre en una línea: qué es esta sesión y qué NO se reabre.

## Regla de oro
La única cosa irremplazable de estos N minutos: __________.
Orden de sacrificio si aprieta el tiempo: A → B → C → [la regla de oro no se sacrifica].

## Salidas (con qué nos vamos)
1. ________  · vive en → doc #
2. ________  · vive en → doc #
… (si falta alguna al cierre, se agenda follow-up ANTES de salir)

## Preguntas por bloque
- <bloque>: pregunta, pregunta…

## Run-of-show (min)
| Tiempo | Bloque | Qué pasa |

## Reparto
| Quién | Lleva |  (uno es DUEÑO de que las salidas se cumplan)

## Datos a pedir/recibir hoy
## Riesgos y manejo
```

Notas de uso:

- Si una salida falta al cierre, el follow-up se agenda **antes de salir de la sala**, no después.
- Pide consentimiento para grabar. Un segundo dispositivo grabando es seguro barato.

---

## Ejemplo: la plantilla llenada

Caso ficticio, para ilustrar el formato: una sesión de descubrimiento previa a construir el **Bot de Pedidos** (un bot B2B de levantamiento de pedidos por WhatsApp/voz), con "la Distribuidora", una distribuidora regional de abarrotes que surte a tienditas. Ningún dato corresponde a una empresa real.

```markdown
# Prep · Descubrimiento de levantamiento de pedidos · 2026-08-03 · La Distribuidora
> Interno. Entender cómo el equipo de ventas levanta hoy un pedido de una tiendita de punta a punta, para diseñar el flujo del Bot de Pedidos. NO se reabre: precio, condiciones comerciales o cobertura de rutas (eso ya está definido con el cliente).

## Regla de oro
La única cosa irremplazable de estos 90 minutos: ver a un capturista levantar un pedido real de una tiendita, de punta a punta, con sus herramientas en pantalla (WhatsApp, catálogo, sistema de captura) — no que nos lo describan de memoria.
Orden de sacrificio si aprieta el tiempo: preguntas sobre reportes y dashboard actuales → detalle de excepciones raras (devoluciones, crédito) → recorrido de la app de catálogo interno → [la regla de oro no se sacrifica: la demostración en vivo del pedido de punta a punta se protege aunque se corte todo lo demás].

## Salidas (con qué nos vamos)
1. Grabación (o notas minuto a minuto) de un pedido real levantado de punta a punta · vive en → doc #1
2. Diagrama de los pasos que sigue el capturista desde que llega el mensaje/llamada de la tiendita hasta que el pedido queda registrado · vive en → doc #2
3. Lista de los canales reales que usan hoy las tienditas para pedir (WhatsApp, llamada, nota de voz, visita del vendedor) con % aproximado de uso por canal · vive en → doc #2
4. Ejemplo real de un pedido "difícil" (producto sin stock, tiendita que regatea cantidad, pedido incompleto) y cómo lo resuelve hoy el capturista · vive en → doc #3
5. Catálogo de productos vigente exportado (CSV o captura de pantalla del sistema actual) · vive en → doc #4
6. Lista de 3-5 tienditas piloto con contacto directo, para pruebas del bot · vive en → doc #5
… (si falta alguna al cierre, se agenda follow-up ANTES de salir)

## Preguntas por bloque
- Apertura y encuadre: ¿quién en la sala levanta pedidos día a día? ¿podemos ver su pantalla mientras trabaja?
- Recorrido en vivo del pedido: ¿por dónde entra el pedido (WhatsApp, llamada, visita)? ¿qué hace primero al recibirlo? ¿dónde lo captura? ¿qué revisa antes de confirmarlo (stock, crédito, mínimo de pedido)?
- Excepciones: ¿qué pasa si el producto no tiene stock? ¿si la tiendita pide fiado o pasa su límite de crédito? ¿si el pedido llega incompleto o con dudas?
- Canales y volumen: ¿qué porcentaje de tienditas pide por WhatsApp vs. llamada vs. visita del vendedor? ¿hay tienditas que prefieren nota de voz?
- Catálogo y datos: ¿el catálogo que usa el capturista está actualizado en algún sistema o es una lista en papel/Excel? ¿podemos quedarnos con una copia?
- Cierre: ¿qué tienditas estarían dispuestas a probar un piloto del bot? ¿quién de su equipo sería el punto de contacto?

## Run-of-show (min)
| Tiempo | Bloque | Qué pasa |
|---|---|---|
| 0-10 | Apertura y encuadre | Confirmamos objetivo de la sesión, pedimos consentimiento para grabar, presentamos al equipo |
| 10-45 | Recorrido en vivo del pedido | El capturista levanta un pedido real de una tiendita frente a nosotros, con su pantalla compartida |
| 45-65 | Excepciones y canales | Preguntas sobre casos difíciles, canales reales de entrada y su distribución aproximada |
| 65-80 | Catálogo y datos | Revisión y exportación del catálogo vigente; confirmación de qué datos nos pueden compartir hoy mismo |
| 80-88 | Cierre y compromisos | Confirmamos tienditas piloto, punto de contacto, y qué salidas quedaron pendientes |
| 88-90 | Buffer | Colchón para preguntas que se hayan quedado fuera |

## Reparto
| Quién | Lleva |
|---|---|
| Cristopher | Conduce la sesión y protege la regla de oro (DUEÑO de que las salidas se cumplan) |
| Analista de producto | Toma notas estructuradas y arma el diagrama de pasos (salida #2) |
| Contacto en La Distribuidora (gerente de ventas) | Facilita al capturista y a las tienditas piloto |

## Datos a pedir/recibir hoy
- Catálogo de productos vigente (CSV o export del sistema actual).
- Contacto de 3-5 tienditas piloto.
- Si existe, algún reporte o Excel donde hoy consoliden pedidos por ruta.

## Riesgos y manejo
- El capturista "actúa" un pedido en vez de mostrar uno real (se limpia y ordena para quedar bien) → pedir explícitamente ver el siguiente pedido que entre de forma natural durante la sesión, no uno preparado de antemano.
- La sesión se llena de quejas sobre el sistema actual y no llegamos al recorrido en vivo → recordar el encuadre al inicio y cortar con "eso lo anotamos, volvamos al pedido en pantalla" si se desvía.
- El gerente de ventas responde por el capturista y no lo deja mostrar cómo trabaja realmente → dirigir las preguntas de recorrido directamente al capturista, no al gerente.
```

### Por qué cada bloque

- **Encuadre**: fija qué no se reabre, para no perder los 90 minutos discutiendo algo ya decidido.
- **Regla de oro**: qué proteger cuando el tiempo apriete — si sólo sale una cosa de la sesión, que sea esa.
- **Orden de sacrificio**: decide el recorte antes de que lo decida el reloj, en caliente.
- **Salidas**: con qué te vas, no de qué hablas — cada una es verificable y vive en un documento concreto.
- **Preguntas por bloque**: el guion mínimo para no improvisar en vivo, organizado por lo que cada bloque necesita producir.
- **Run-of-show**: el presupuesto de tiempo explícito, para notar a mitad de sesión si vas atrasado.
- **Reparto**: quién hace qué y quién responde si al final falta una salida.
- **Datos a pedir/recibir hoy**: lo que se puede llevar en la mano al salir de la sala, sin depender de un follow-up.
- **Riesgos y manejo**: los modos de falla previsibles de esta sesión específica, con la reacción ya decidida de antemano.
