# Instrucciones para crear un prototipo funcional con Cursor

> Escrito en marzo de 2025. Se publica con las herramientas y modelos de su época (ChatGPT O1, Cursor, Replit) — el flujo sigue siendo válido con las herramientas de hoy: sustituye los nombres. Único cambio para publicación: el PRD de ejemplo original era de un producto real y se sustituyó por un caso ficticio equivalente (jul-2026).

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

---

> **Ejemplo ilustrativo** — producto ficticio para mostrar el formato.
> Nota de publicación: el ejemplo original del instructivo usaba un producto real; se sustituyó por este caso ficticio equivalente (jul-2026), manteniendo formato y nivel de detalle.

# Ejemplo formato Product Requirements Document (PRD) - Bot de Pedidos IA

## **1. Visión del Producto**

El **Bot de Pedidos IA** busca revolucionar la forma en que las distribuidoras (particularmente las que surten a tienditas y abarrotes) levantan y procesan pedidos de sus clientes. Se trata de un **producto B2B** capaz de:

* Guiar a la distribuidora en la **definición y configuración** de su catálogo y su flujo de toma de pedidos.
* Coordinar el **levantamiento de pedidos** por voz o texto (WhatsApp, llamadas telefónicas) directamente con el tendero.
* Entregar visibilidad de alto valor a través de un **dashboard dinámico** y un agente conversacional que ayuda a **consultar y analizar** los pedidos de manera automática.

### **Objetivos Principales**

1. **Agilidad en la Configuración del Catálogo y Flujo de Pedido**
   Un agente que interactúe con el usuario (distribuidora) en lenguaje natural para definir de forma semiestructurada el catálogo de productos, precios, reglas de pedido mínimo y el flujo que debe seguir la toma de pedido.
2. **Automatización del Levantamiento de Pedidos**
   Un sistema capaz de **levantar los pedidos** mediante llamada o mensajes de texto/WhatsApp con el tendero, extrayendo cantidades y productos de manera natural y almacenándolos en una base de datos interna.
3. **Análisis y Visualización de Pedidos**
   Un tercer agente que permita **consultar, graficar y extraer** los datos de pedidos (CSV, reportes básicos) y responder dudas sobre volumen, productos más pedidos y comportamiento de tienditas.
4. **Escalabilidad y Facilidad de Integración**
   Diseñar la arquitectura para que sea posible cambiar el proveedor de IA (inicialmente OpenAI) y escalar el número de tienditas y distribuidoras atendidas.

---

## **2. Casos de Uso**

### **2.1 Distribuidora (Primer Cliente Objetivo)**

* **Definición del Catálogo y Flujo**: El equipo de la distribuidora sube un listado de productos y precios (ej. en CSV) y, mediante un chat con el "agente de diseño", define:
  * Catálogo de productos vigente (SKUs, precios, presentaciones).
  * Reglas de pedido (pedido mínimo, días de entrega, zonas cubiertas).
  * Tipo de información a confirmar con el tendero (cantidad, sustitutos si falta stock, etc.).
* **Levantamiento del Pedido**: El "agente de pedidos" procede a contactar a la base de tienditas asignadas a cada ruta a través de:
  * **Llamada telefónica** automatizada (voz).
  * **WhatsApp** (texto).
* **Análisis de la Información**: El "agente analítico" ofrece:
  * Estadísticas básicas (número de pedidos levantados, tasa de respuesta por ruta).
  * Visualizaciones dinámicas (gráficas generadas en tiempo real de productos más pedidos).
  * Exportación de datos en CSV para conciliar con el sistema de facturación de la distribuidora.

### **2.2 Empresa Final (Futuro)**

* Una marca de consumo masivo con ruta directa a tiendita podría usar el sistema directamente para levantar pedidos de reposición sin pasar por una distribuidora intermedia.
* Sin embargo, en el MVP, se prioriza a la **distribuidora** como cliente principal.

---

## **3. Funcionalidades Clave**

1. **Agente de Diseño de Catálogo y Flujo (Chat Interactivo)**
   * Flujo de **conversación semiestructurada** que guía al usuario a definir:
     * Catálogo de productos y precios vigentes.
     * Reglas del pedido (mínimos, sustitutos, días y horarios de corte).
     * Tipo de confirmaciones esperadas (cantidad exacta, unidades vs. cajas, etc.) aunque la interacción con el tendero sea natural.
   * Posibilidad de **personalizar el flujo de pedido** completamente (no solo plantillas).
2. **Carga de Tienditas**
   * **Importación masiva** de contactos de tienditas vía CSV/Excel, con ruta y vendedor asignado.
   * Almacenamiento en base de datos interna, segmentado por ruta y por distribuidora.
3. **Agente de Levantamiento de Pedido**
   * **Modalidades**:
     * **Llamadas** a teléfonos celulares (interfaz de voz).
     * **Mensajes de WhatsApp** (texto conversacional).
   * **IA semiestructurada** para mantener el objetivo del pedido, aun si la conversación da rodeos (ej. el tendero pregunta por promociones o pide cambiar cantidades a media conversación).
   * Manejo de **Estado**: detecta si el tendero ya confirmó todos los productos del pedido habitual o si hace falta preguntar por algo adicional.
4. **Almacenamiento y Gestión de Pedidos**
   * Base de datos interna (sin integraciones externas en el MVP).
   * Segmentación de resultados por **distribuidora**, por **ruta** y por **tiendita**.
5. **Agente Analítico y Dashboard**
   * Posibilidad de **consultar** los datos por medio de una interfaz conversacional ("Muéstrame cuántas tienditas pidieron X producto esta semana").
   * **Visualizaciones dinámicas** (gráficas de barras, pastel, mapas de calor por ruta, etc.) generadas automáticamente a partir de los datos.
   * **Exportación** de reportes o datos en CSV.
   * Métricas básicas (número de pedidos levantados, tasa de tienditas contactadas que sí pidieron, resúmenes de productos más solicitados).
   * (Futuro) Personalización más avanzada de widgets o dashboards.

---

## **4. Requisitos Técnicos y Alcance**

### **4.1 Arquitectura y Proveedor de IA**

* Uso inicial de **OpenAI** para los modelos de lenguaje (GPT-4o según se decida).
* Diseño modular para **cambiar de proveedor** en el futuro (Azure, Anthropic, etc.).
* Flujo **semiestructurado** en la parte conversacional para evitar que la IA se desvíe del objetivo del pedido.

### **4.2 Modalidades de Interacción (MVP)**

* **Idiomas**: Español (en MVP).
* **Pedidos por Voz**: Llamadas a celular por medio de un servicio de telefonía (API de Twilio).
* **Pedidos por Texto**: Uso de WhatsApp (API oficial).

### **4.3 Seguridad y Privacidad**

* En el MVP **no** se contemplan requisitos especiales de cifrado o cumplimiento normativo avanzado (GDPR, CCPA, etc.).
* Se almacenan datos de contacto de tienditas y detalle de pedidos de manera interna.

### **4.4 Despliegue y Escalabilidad**

* **Cloud first** (AWS).
* En el MVP, se espera un volumen de **cientos de tienditas** y **un solo cliente (la distribuidora)**.
* La arquitectura deberá poder **escalar** con un diseño modular.

---

## **5. MVP: Detalles y Alcance**

El MVP se enfocará en ofrecer las **tres funcionalidades principales** con una primera versión simplificada de cada una:

1. **Agente de Diseño de Catálogo y Flujo**
   * Interfaz conversacional básica para definir catálogo, precios y reglas de pedido.
   * Creación de un flujo de pedido semiestructurado que pueda ajustarse a medida que se conversa con el bot.
2. **Agente de Levantamiento de Pedido**
   * Capacidad de contactar a las tienditas vía llamada telefónica o WhatsApp.
   * Captura del pedido en un formato consistente (texto plano, con algún etiquetado mínimo de producto/cantidad).
   * Manejo simple de reintentos (por si la tiendita no contesta o pide que la vuelvan a llamar más tarde).
3. **Agente Analítico y Dashboard**
   * Almacenamiento de pedidos en la base de datos.
   * Generación de **gráficas automáticas** (por ejemplo, conteo de pedidos por ruta o distribución de productos más pedidos).
   * Exportación a CSV y visualización de métricas iniciales.
   * Consulta conversacional básica: "¿Cuántas tienditas pidieron el producto X esta semana?" y se despliega la métrica.

### **5.1 Out of Scope (Para Futuros Lanzamientos)**

* Cumplimiento con GDPR u otras regulaciones de datos.
* Integraciones con sistemas ERP o de facturación externos (SAP, CONTPAQi, etc.).
* Procesamiento avanzado de audio en múltiples idiomas.
* Personalización exhaustiva del dashboard o creación de plantillas de flujo de pedido predefinidas.
* Modelos de pricing y marketplace de complementos.

---
