---
title: Información general y guía del usuario de Journey Agent
description: Guía completa de Journey Agent, que permite a los usuarios crear, analizar y optimizar recorridos de marketing mediante una interfaz de lenguaje natural en Journey Optimizer.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer,Leader
TQID: https://experienceleague.adobe.com/7Bamc-q4rDOB9i0oxwixdmtdU8lrx3btpvMfAsjGnig
product_v2:
  - id: cb954087-f4fc-4456-afb9-e939cabcdc79
feature_v2:
  - id: baecb07f-ce89-4ebb-9cd9-0f7c053f944f
  - id: d0a62d3c-b79e-47e4-929e-40ef3cffa037
  - id: d556b755-390a-43f0-be32-a08cf6236126
  - id: d998adac-2f81-400b-a669-d07bb196e4eb
  - id: df64005d-8f9a-422e-ba4d-c6f6dc3454b4
  - id: fe338112-e2ce-4876-8989-fc4d497613f1
subfeature_v2:
  - id: b15c7c2e-788c-4eb7-86a8-390565b0d2c9
  - id: b32bb433-f8c6-4931-8e52-e657230a3bf2
  - id: b3a93754-a8b8-46eb-9421-7eccaeeb3dff
  - id: fa683eda-48de-4558-af32-2673edcd44fe
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5520579-b31f-4df7-9281-f0d9f91e2edc
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: ff2b9b37-92e0-45fc-b853-379d44c08c89
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 2655
ht-degree: 14%

---

# Journey Agent: Información general y guía del usuario

## Introducción a Journey Agent en Adobe Journey Optimizer

Journey Agent permite a los usuarios de Journey Optimizer crear, analizar y optimizar recorridos de marketing mediante una interfaz de lenguaje natural. Con Journey Agent, los profesionales pueden crear recorridos rápidamente, detectar y resolver conflictos de programación o público, analizar el rendimiento y los puntos de abandono, e identificar los recorridos de mayor rendimiento para replicarlos en futuras campañas. Permite a los profesionales tomar decisiones basadas en datos, mejorar la participación de los clientes y optimizar la organización de recorridos.

Journey Agent consta de tres tareas principales que se deben realizar:

- **Creación de Recorrido**: cree y configure recorridos de marketing mediante mensajes en lenguaje natural
- **Creación de contenido de canal**: genera, edita y administra contenido específico del canal (correo electrónico, push, SMS) para recorridos mediante la generación de contenido con tecnología de IA
- **Análisis de Recorrido**: Analice recorridos, detecte problemas, descubra información y optimice la participación de los clientes

## Recorrido Crear: Casos de uso, Aptitudes de agente y Guía del usuario

## Información general

Recorrido Crear permite a los usuarios de Journey Optimizer crear y configurar recorridos de marketing mediante una interfaz de lenguaje natural. Con Recorrido Crear, los profesionales pueden crear recorridos rápidamente al describir sus necesidades en mensajes de conversación. El agente optimiza la creación de recorridos, lo que permite a los especialistas en marketing centrarse en la estrategia en lugar de en la configuración técnica.

>[!AVAILABILITY]
>
>La opción Crear recorrido está disponible para todos los clientes que tienen acceso al asistente de IA. Sin embargo, necesitará los siguientes permisos para utilizar completamente las funciones de creación de Recorridos:
>
>**Administrar Recorridos**: este permiso le permite crear nuevos recorridos directamente en el Asistente para IA.
>
>**Ver eventos de Recorrido, fuentes de datos y acciones**: este permiso garantiza que el Ayudante de IA pueda buscar mediante eventos de Recorrido y acciones personalizadas.
>
>**Ver segmentos**: Este permiso garantiza que el Asistente de IA pueda buscar segmentos de audiencia al crear un Recorrido.
>
>**Administrar segmentos**: Este permiso le permite crear nuevas audiencias directamente en el Asistente de IA.

## Casos de uso

### Casos de uso clave para la creación de Recorridos

Recorrido Cree ofertas que se puedan aprovechar para acelerar la ejecución del marketing:

1. **Creación de recorrido desencadenada por eventos**

   - Cree recorridos que se activen en función de eventos de clientes específicos.
   - Diseñar respuestas automatizadas a acciones de clientes en tiempo real.
   - Cree flujos de comunicación personalizados basados en el comportamiento de los clientes.

1. **Creación de recorrido con destino de audiencia**

   - Genere recorridos dirigidos a segmentos de audiencia específicos.
   - Diseñe secuencias de comunicación de varios pasos con sincronización estratégica.

1. **Creación de recorrido desencadenada por evento empresarial**

   - Cree recorridos que se activen en función de un evento empresarial determinado y se dirijan a una audiencia específica (por ejemplo, producto disponible o cambio de puntuación de juego)
   - Cree flujos de comunicación personalizados basados en el comportamiento de los clientes.

1. **Creación del recorrido de calificación de audiencia**

   - Cree recorridos que se activen cuando los perfiles entran o salen de una definición de segmento de audiencia.
   - Cree flujos de comunicación personalizados basados en el comportamiento de los clientes.

1. **Flujos de recorrido condicionales**

   - Cree ramas de decisión basadas en atributos del cliente.
   - Diseñe rutas divididas que se adapten a las preferencias de los clientes.

Para cada uno de estos casos de uso, el agente traduce los requisitos del lenguaje natural en configuraciones de recorrido estructuradas.

## Aptitudes dentro y fuera del ámbito

### **En ámbito**

Recorrido Crear admite las siguientes funciones:

- **Creación de recorridos en lenguaje natural**: permite a los usuarios describir el flujo de recorrido en lenguaje conversacional.
- **recorridos basados en eventos y en audiencias**: admite tipos de recorridos programados y basados en déclencheur, así como eventos comerciales y calificación de audiencias.
- **Lógica condicional**: administra las divisiones y ramas de decisión en función de los atributos del cliente.
- **Mensajería multicanal**: Admite notificaciones push, correo electrónico y canales SMS.
- **Programación de Recorridos**: Configura las fechas de inicio y el horario de los recorridos programados.

### **Fuera de ámbito**

Actualmente no se admiten las siguientes funcionalidades:

- **Análisis de recorrido avanzado**
- **Modificaciones de recorrido en tiempo real**
- **Organización entre recorridos**
- **Configuración de prueba A/B**
- **Transformaciones de datos complejas**

## Ejemplos de peticiones de datos

### Solicitudes comunes para la creación de recorridos

Estos son ejemplos de sugerencias útiles que los usuarios pueden aprovechar para crear recorridos.

### Mensajes de recorrido activados por eventos

**recorrido de visitas a la tienda:**

&quot;Crear un recorrido que se inicie cuando un usuario entre en mi ubicación de tienda. Envíe una notificación push para dar la bienvenida a los usuarios a la tienda. Espere 2 días y compruebe si el usuario tiene una dirección de correo electrónico válida. Si el usuario tiene una dirección de correo electrónico válida, envíe un sondeo por correo electrónico para preguntar por su experiencia en la tienda. Si el usuario no tiene una dirección de correo electrónico válida, envíe una notificación push para solicitar el registro&quot;.

**recorridos posteriores a la compra:**

&quot;Cree un recorrido que se inicie cuando un cliente realice una compra en línea. Envíe una notificación push para agradecerles su compra. A continuación, compruebe si son miembros socio. Si el usuario es un abonado de las recompensas por fidelidad, envíe una segunda notificación push con un código de descuento del 10 %. Si el usuario no es un miembro de las recompensas por fidelidad, envía una notificación push invitándolo a registrarse en el programa de fidelidad. Espere 2 días y envíe una notificación push de seguimiento con una encuesta sobre su experiencia de compra&quot;.

**Promoción basada en eventos:**

&quot;Crea un recorrido cuando la puntuación del juego alcance 50. Envíe un mensaje SMS a los miembros de la recompensa de fidelidad diciendo que cumplen los requisitos para una porción gratuita de pizza del patrocinador del socio&quot;.

### Mensajes de recorrido dirigidos a audiencia

**Campaña estacional:**

&quot;Quiero crear un recorrido dirigido a una audiencia de excursionistas. Quiero enviar un correo electrónico alertando a esta audiencia sobre mi próxima venta de vacaciones que incluye una variedad de elementos esenciales para el senderismo. Espere 3 días después de enviar el primer correo electrónico y envíe un segundo correo electrónico que tenga un cupón del 15% con envío gratuito. Espere 1 semana y luego envíe un tercer mensaje de correo electrónico para mostrar nuestro nuevo saco de dormir y la colección de la tienda. Programe el recorrido para que comience el 20/12&quot;.

**Reconocimiento de fidelidad:**

&quot;Cree un recorrido de apreciación de la lealtad para los propietarios de SUV, que incluya una notificación push de agradecimiento con una oferta de lavado de coches gratis y un recordatorio de notificación push de seguimiento si no se interactúa con la primera notificación en el plazo de 1 día&quot;.

### Mensajes abiertos

Para usuarios que empiecen sin tener en cuenta un recorrido específico:

- &quot;Me gustaría crear un recorrido&quot;
- &quot;Ayúdame a crear un recorrido&quot;
- &quot;Crea un recorrido&quot;

El agente le proporcionará instrucciones y ejemplos para ayudarle a definir los requisitos de recorrido.

## Prácticas recomendadas

### Impulso de las prácticas recomendadas

Para maximizar la eficacia de Creación de Recorridos, siga estas prácticas recomendadas:

1. **Sea específico**: Proporcione detalles claros sobre sus objetivos de recorrido, audiencia de destinatario y acciones deseadas. Incluya información sobre canales, temporización y condiciones.
1. **Especificar tiempo**: indique claramente los períodos de espera entre las acciones y cuándo debe iniciarse el recorrido.
1. **Definir condiciones**: cuando use la lógica condicional, explique los criterios para cada ruta de bifurcación.
1. **Incluir canales**: especifique qué canales de comunicación desea utilizar (push, correo electrónico, SMS).
1. **Programación de menciones**: para los recorridos programados, proporcione la fecha y la hora de inicio que desee.
1. **Acciones personalizadas**: si usa acciones personalizadas en el flujo de trabajo, debe especificar que usa una acción personalizada junto con el nombre exacto de la acción personalizada. Por ejemplo:
Cuando un usuario entre en mi ubicación de tienda, enviar un mensaje de bienvenida mediante la acción personalizada ExternalPush. Espere 2 días y, a continuación, envíe un mensaje de seguimiento mediante una acción personalizada por correo electrónico externo con una encuesta sobre su visita.
1. **Validar expresiones**: asegúrese de comprobar y validar cualquier expresión que cree Journey Agent para asegurarse de que se utilizan los campos y valores correctos.

### Setup best practices

- **Define Clear Objectives**: Before creating journeys, establish clear goals (improving retention, driving conversions, increasing engagement).
- **Prepare Audiences**: Ensure your target audiences are already created and properly segmented.
- **Plan Message Content**: Have your messaging strategy defined before journey creation.
- **Consider Customer Experience**: Design journey flows that respect customer preferences and avoid over-communication.

## Channel Content Create: Use Cases, Agentic Skills and User Guide

>[!AVAILABILITY]
>
>This feature is available for all customers in Limited Availability. Póngase en contacto con su representante de Adobe para obtener acceso.

## Información general

Channel Content Create enables Journey Optimizer users to generate, edit, and manage channel-specific content for journeys using AI-powered content generation.

## Casos de uso

### Key use cases for Channel Content Create

1. **Channel-specific content generation**: Generate content for email, push notifications, SMS, and other channels using natural language prompts.

1. **Template-based content creation**: Browse and select from available templates with preview capabilities.

1. **Multi-channel content management**: Generate and manage content for multiple channels within the same journey workflow.

1. **In-context content editing**: Open generated content in Content Designer for editing and refinement.

1. **Content refinement and iteration**: Regenerate content with different tones or styles using the Regenerate action.

1. **Journey canvas integration**: Select journeys from inventory and view associated channels.

## In scope and out of scope skills

### **In scope**

The following capabilities are supported by Channel Content Create:

- **AI-powered content generation**: Generate content for email, push, SMS, and other channels using natural language prompts.
- **Template management**: Browse and select from available templates with preview capabilities.
- **In-context editing**: Open generated content in Content Designer for editing and refinement.
- **Content regeneration**: Regenerate content with different tones, styles, or messaging using the Regenerate action.
- **Multi-channel support**: Generate and manage content for multiple channels within the same journey workflow.
- **Journey inventory access**: Select journeys from inventory and view associated channels.

### **Out of scope**

Actualmente no se admiten las siguientes funcionalidades:

- **Alineación de marca y comprobaciones de calidad del contenido**
- **Insertar nodos de contenido directamente en el lienzo de recorrido**
- **Importación de plantilla**

## Ejemplos de peticiones de datos

### Generación de contenido

&quot;Generar contenido de correo electrónico para mi recorrido de bienvenida. Cree un correo electrónico de bienvenida para nuevos clientes con un tono cordial e incluya una oferta de descuento del 10 %&quot;.

&quot;Agregar contenido para el correo electrónico del canal para mi recorrido de bienvenida&quot;.

&quot;Generar una notificación push para el recorrido de mi visita a la tienda. Cree un mensaje de bienvenida que anime a los clientes a registrarse y recibir una oferta especial&quot;.

&quot;Generar contenido SMS para mi recorrido activado por eventos. Cree un mensaje corto para notificar a los clientes sobre una venta flash con un call-to-action&quot;.

### Selección de plantilla

&quot;Mostrarme las plantillas de correo electrónico disponibles para mi recorrido de campaña de temporada&quot;.

&quot;Seleccione una plantilla para mi correo electrónico que tenga un diseño moderno y limpio.&quot;

### Edición y refinamiento de contenido

&quot;Abra el contenido del correo electrónico en Content Designer para poder personalizar el diseño&quot;.

&quot;Regenerar el contenido de las notificaciones push con un tono más informal&quot;.

&quot;Actualice el contenido del correo electrónico para incluir un código promocional.&quot;

## Prácticas recomendadas

### Impulso de las prácticas recomendadas

1. **Sea específico**: Proporcione detalles claros sobre el tipo de contenido, el tono, la audiencia de destino y los mensajes clave.
1. **Especificar canal**: indique claramente para qué canal está creando contenido (correo electrónico, push, SMS).
1. **Definir tono**: especifique el tono deseado (cordial, formal, informal, urgente).
1. **Iterar y refinar**: use la acción de regeneración para refinar el contenido hasta que cumpla con sus requisitos.

## Análisis de recorrido: casos de uso, habilidades de agente y guía del usuario

## Información general

Journey Agent will enable Journey Optimizer users to analyze, and optimize journeys using a natural language interface. With Journey Agent, practitioners can quickly identify and resolve schedule and/or audience conflicts, detect points of user abandonment in a journey and provide insights or recommendations. Permite a los profesionales tomar decisiones basadas en datos, mejorar la participación del cliente y agilizar la orquestación del recorrido.

Learn more and discover the agent at a glance in this [overview](https://experienceleague.adobe.com/es/slides/journey-agent-overview).

>[!AVAILABILITY]
>
>The Journey Agent is available for all customers who have access to AI Assistant. However, you will need the following permissions in order to fully use the Journey Agent features:
>
>**View Journeys**: This permission lets you view insights into the journey directly in AI Assistant.
>
>**Manage Journeys**: To permission lets you create new journeys directly in AI Assistant.
>
>**View Segments**: This permission lets you view insights into the audiences directly in AI Assistant.
>
>**Manage Segments**: To permission lets you create new audiences directly in AI Assistant.

![Sample for AJO Agent](./images/ajo-agent/ajo-agent-sample.png)

## Casos de uso

### Key Use Cases for Journey Analyze

Journey Analyze offers a range of functionalities that can be leveraged to optimize marketing efforts:

1. **Análisis del abandono del recorrido**

   - Identifique dónde y por qué abandonan los clientes durante un recorrido.
   - Detecte patrones de comportamiento del cliente que conducen a la desvinculación.
   - Utilice la información para perfeccionar el diseño del recorrido y mejorar la retención.

1. **Análisis de solapamiento de público en los recorridos**

   - Analice el solapamiento de público en múltiples recorridos.
   - Evite la fatiga del público causada por una segmentación excesiva.
   - Optimice la segmentación para garantizar una participación equilibrada.

1. **Análisis del solapamiento de la programación en los recorridos**

   - Detecte conflictos de horarios entre recorridos programados dirigidos al mismo público.
   - Evite el exceso de comunicación y mejore la eficacia de la programación.
   - Maximice el impacto en el público asegurándose de que los viajes se realizan en los momentos óptimos.

1. **Datos operativos**

   - Prompt-based Journey Insights – Surface operational insights about journeys , i.e. &quot;show me all live journeys.&quot;

For each of these analyses, the agent not only detects issues but also provides **actionable recommendations to resolve them**.

## Competencias incluidas y excluidas del ámbito de aplicación

### **Ámbito de aplicación**

The following capabilities are supported by Journey Analyze:

- **Consultas reactivas**: permite a los usuarios hacer preguntas específicas sobre el rendimiento del recorrido, el uso del público y los conflictos de programación.
- **Integración con otros agentes**: colabora con Audience Agent y Data Insights Agent para un análisis más profundo.
- **Agent response structuration**: reasoning (explain the logic), analysis summary (highlight key points), issue details (describe the problem), and recommendation (propose next steps).

### **Fuera del ámbito de aplicación**

Actualmente no se admiten las siguientes funcionalidades:

- **Creación automática de recorridos**
- **Detección de anomalías en tiempo real**
- **Los canales se solapan**
- **Análisis de entrada del recorrido**
- **Análisis de problemas técnicos**
- **Análisis de fatiga**

## Muestras de solicitudes/Ejemplos de solicitudes

### Solicitudes habituales para el análisis del recorrido

A continuación, presentamos ejemplos de solicitudes valiosas que los usuarios pueden aprovechar para explorar, monitorizar y solucionar problemas en sus recorridos.

### Preguntas sobre el ciclo de vida del recorrido

- &quot;When was [Journey Name] published?&quot;
- &quot;When was [Journey Name] stopped?&quot;
- &quot;List all journeys currently in test mode&quot;

### Preguntas sobre los recursos del recorrido

- &quot;How many live journeys do I have?&quot;
- &quot;Give me a list of all scheduled recurring journeys and their expected run times.&quot;

### Información sobre el público y el recorrido

- &quot;Which audiences are used in more than X journeys?&quot;
- &quot;List all journeys using the [audience name] audience.&quot;

### Fallout analysis

- &quot;I want to analyze the fallout by node for journey Fourth of July Campaign.&quot;
- &quot;Perform a fallout analysis for journey Fourth of July Campaign.&quot;
- &quot;What is profile loss over the course of journey Fourth of July Campaign?&quot;
- &quot;Show where users are dropping off in journey Fourth of July Campaign.&quot;

### Solicitudes de análisis de conflictos

Utilice estas solicitudes para analizar los posibles conflictos entre recorridos, incluidos los solapamientos de horarios y públicos:

- &quot;Can you do a comprehensive analysis of conflicts for our journey [Journey Name] with conflict type (scheduling/audience) information with live/running journeys?&quot;
- &quot;Please do a scheduling conflict analysis for journey [Journey Name] with conflict type information.&quot;
- &quot;Please do an audience overlap analysis for journey [Journey Name] with conflict type information.&quot;
- &quot;Are there any scheduling conflicts for journey [Journey Name]?&quot;
- &quot;Show me audience overlap conflicts for journey [Journey Name].&quot;
- &quot;Analyze all conflicts for journey [Journey Name] with other live journeys.&quot;
- &quot;What are the current conflicts for journey [Journey Name]?&quot;
- &quot;Check if journey [Journey Name] has audience conflicts with other journeys.&quot;
- &quot;Check for scheduling conflicts involving journey [Journey Name].&quot;
- &quot;I want to know about all journey conflicts for [Journey Name].&quot;
- &quot;Do any live journeys conflict with [Journey Name] by schedule or audience?&quot;
- &quot;Identify conflict types for journey [Journey Name] compared to running journeys.&quot;
- &quot;Show overlapping audiences for journey [Journey Name] and other journeys.&quot;
- &quot;Highlight scheduling overlaps between journey [Journey Name] and live journeys.&quot;
- &quot;Is journey [Journey Name] running in conflict with any other journey?&quot;
- &quot;Please detect and list conflicts for [Journey Name].&quot;
- &quot;Report all types of conflicts for journey [Journey Name].&quot;
- &quot;Give me a conflict breakdown (scheduling and audience) for [Journey Name].&quot;
- &quot;Does [Journey Name] have any conflicts that may impact performance?&quot;
- &quot;Are there any active conflicts affecting [Journey Name]?&quot;
- &quot;List journeys in conflict with [Journey Name] by schedule or audience.&quot;
- &quot;Has journey [Journey Name] triggered any conflict alerts?&quot;
- &quot;Buscar posibles conflictos de audiencia para el recorrido [Nombre de Recorrido]&quot;.
- &quot;Analice el riesgo de conflicto para el recorrido [Nombre de Recorrido].&quot;
- &quot;Proporcionar diagnósticos de conflicto para [Nombre de Recorrido].&quot;

## Prácticas recomendadas

### Prácticas recomendadas en materia de solicitudes

Para maximizar la eficacia del análisis de Recorrido, siga estas prácticas recomendadas:

1. **Sea específico**: utilice preguntas claras y concisas para obtener información específica. Por ejemplo, en lugar de preguntar &quot;¿Cuáles son mis recorridos?&quot;, especifique &quot;Enumerar todos los recorridos creados en el último mes&quot;.
1. **Combine información**: integre la información de Audience Agent y Data Insights Agent para obtener una visión integral del rendimiento del recorrido.
1. **Perfeccionamiento iterativo**: utilice el análisis de abandonos y solapamientos para perfeccionar de forma iterativa el diseño y la programación de los recorridos.

### Prácticas recomendadas para la configuración

- **Defina objetivos claros**: antes de analizar los recorridos, establezca objetivos claros (por ejemplo, mejorar la retención, aumentar las conversiones).
- **Monitorice de forma periódica**: programe revisiones periódicas del rendimiento de los recorridos para identificar las tendencias y las anomalías.
- **Optimice la segmentación**: asegúrese de que la segmentación del público está equilibrada para evitar la fatiga y maximizar la participación.

## Diapositivas y presentaciones

>[!NOTE]
>
>Las diapositivas y el material de presentación de Journey Agent estarán disponibles aquí. Vuelva pronto para ver las actualizaciones.
