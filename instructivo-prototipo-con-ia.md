# Instrucciones para crear un prototipo funcional con Cursor

> Escrito en marzo de 2025. Se publica tal cual, con las herramientas y modelos de su época (ChatGPT O1, Cursor, Replit). El flujo sigue siendo válido con las herramientas de hoy: sustituye los nombres.

Para un usuario **no técnico** que necesita un mock front-end navegable para una presentación comercial.

1. Redactar una breve descripción de necesidades del producto.
2. Pedir a ChatGPT (modelo O1) que te ayude a completar un documento tipo PRD.
3. **Nota:** en caso de ya tener un documento de negocio, unos requerimientos o detalles del producto, se pueden saltar los pasos 1 y 2.
4. Rebotar la definición de ese documento con Cursor y ayuda del prompt.
5. Cursor te va a generar preguntas y debes contestarlas.
6. Cursor te va a generar un documento adicional, y ése debes solicitar a un nuevo chat de Cursor que te haga el mock.

## Prompt para el mock

```text
Estoy trabajando en un proyecto llamado <nombre del proyecto>, está descrito en el documento adjunto
Mi objetivo es poder construir un mock para una presentación comercial.
Quiero que me hagas las preguntas adecuadas para lograr aterrizar mejor mi idea del mock.
Soy un usuario poco técnico por lo que las dudas técnicas no son mi fuerte
Quiero lograr construir una versión aunque no funcional, pudiera ser puro front end básico con movimiento entre pantallas.
Esto para una presentación comercial
```

## Prompt para rebotar definición de negocio con O1

```text
Quiero afinar mis definiciones de negocio para un producto que estoy pensando
Quiero que me hagas las preguntas adecuadas para poder afinar mis definiciones de negocio
Te comparto mi descripción inicial del producto:
<descripción del producto>
Te comparto un formato de PRD que puedes usar de ejemplo para que entiendas lo que estoy buscando
<ejemplo prd>
```
