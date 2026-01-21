---
title: Información general y guía del usuario de Journey Agent
description: Guía completa de Journey Agent, que permite a los usuarios crear, analizar y optimizar recorridos de marketing mediante una interfaz de lenguaje natural en Journey Optimizer.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer,Leader
source-git-commit: 0e3839f829efc5670c235435d49ed5e49da2ed13
workflow-type: tm+mt
source-wordcount: '2147'
ht-degree: 18%

---


# Journey Agent: Información general y guía del usuario

## Introducción a Journey Agent en Adobe Journey Optimizer

Journey Agent permite a los usuarios de Journey Optimizer crear, analizar y optimizar recorridos de marketing mediante una interfaz de lenguaje natural. Con Journey Agent, los profesionales pueden crear recorridos rápidamente, detectar y resolver conflictos de programación o público, analizar el rendimiento y los puntos de abandono, e identificar los recorridos de mayor rendimiento para replicarlos en futuras campañas. Permite a los profesionales tomar decisiones basadas en datos, mejorar la participación de los clientes y optimizar la organización de recorridos.

Journey Agent consta de dos habilidades principales:
- **Agente de creación de Recorrido**: cree y configure recorridos de marketing mediante mensajes en lenguaje natural
- **Agente de análisis de Recorrido**: Analice recorridos, detecte problemas, descubra información y optimice la participación del cliente

&#x200B;---

&#x200B;# Recorrido Crear agente: descripción general de aptitudes y guía del usuario

## Información general

Recorrido Crear agente permite a los usuarios de Journey Optimizer crear y configurar recorridos de marketing mediante una interfaz de lenguaje natural. Con Recorrido Crear agente, los profesionales pueden crear recorridos rápidamente al describir sus necesidades en mensajes de conversación. El agente optimiza la creación de recorridos, lo que permite a los especialistas en marketing centrarse en la estrategia en lugar de en la configuración técnica.

>[!AVAILABILITY]
>
>El agente de creación de Recorrido está disponible para todos los clientes que tienen acceso al asistente de IA. Sin embargo, necesitará los siguientes permisos para utilizar completamente las funciones de Recorrido de Crear agente:
>
>**Administrar Recorridos**: este permiso le permite crear nuevos recorridos directamente en el Asistente para IA.
>
>**Ver eventos de Recorrido, fuentes de datos y acciones**: este permiso garantiza que el Ayudante de IA pueda buscar mediante eventos de Recorrido y acciones personalizadas.
>
>**Ver segmentos**: Este permiso garantiza que el Asistente de IA pueda buscar segmentos de audiencia al crear un Recorrido.
>
>**Administrar segmentos**: Este permiso le permite crear nuevas audiencias directamente en el Asistente de IA.

## Casos de uso

### Casos de uso clave para el Recorrido Crear agente

La aptitud del Recorrido Crear agente ofrece funcionalidades que se pueden aprovechar para acelerar la ejecución del marketing:

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

El Recorrido Crear agente admite las siguientes funciones:

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
- **Creación de mensaje de contenido**

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

Para maximizar la eficacia de Crear agente de Recorrido, siga estas prácticas recomendadas:

1. **Sea específico**: Proporcione detalles claros sobre sus objetivos de recorrido, audiencia de destinatario y acciones deseadas. Incluya información sobre canales, temporización y condiciones.
1. **Especificar tiempo**: indique claramente los períodos de espera entre las acciones y cuándo debe iniciarse el recorrido.
1. **Definir condiciones**: cuando use la lógica condicional, explique los criterios para cada ruta de bifurcación.
1. **Incluir canales**: especifique qué canales de comunicación desea utilizar (push, correo electrónico, SMS).
1. **Programación de menciones**: para los recorridos programados, proporcione la fecha y la hora de inicio que desee.
1. **Acciones personalizadas**: si usa acciones personalizadas en el flujo de trabajo, debe especificar que usa una acción personalizada junto con el nombre exacto de la acción personalizada. Ejemplo:
Cuando un usuario entre en mi ubicación de tienda, enviar un mensaje de bienvenida mediante la acción personalizada ExternalPush. Espere 2 días y, a continuación, envíe un mensaje de seguimiento mediante una acción personalizada por correo electrónico externo con una encuesta sobre su visita.
1. **Validar expresiones**: asegúrese de comprobar y validar cualquier expresión que cree Journey Agent para asegurarse de que se utilizan los campos y valores correctos.

### Prácticas recomendadas de configuración

- **Definir objetivos claros**: antes de crear recorridos, establezca objetivos claros (mejorar la retención, impulsar las conversiones y aumentar la participación).
- **Preparar audiencias**: Asegúrese de que las audiencias de destino ya se hayan creado y segmentado correctamente.
- **Planificar contenido del mensaje**: Defina su estrategia de mensajería antes de crear el recorrido.
- **Tenga en cuenta la experiencia del cliente**: Diseñe flujos de recorrido que respeten las preferencias del cliente y eviten la comunicación excesiva.

&#x200B;---

&#x200B;# Agente de análisis de recorrido: información general de aptitudes y guía del usuario

## Información general

Journey Agent permitirá a los usuarios de Journey Optimizer analizar y optimizar los recorridos mediante una interfaz de lenguaje natural. Con Journey Agent, los profesionales pueden identificar y resolver rápidamente conflictos de programación o audiencia, detectar puntos de abandono de usuarios en un recorrido y proporcionar perspectivas o recomendaciones. Permite a los profesionales tomar decisiones basadas en datos, mejorar la participación del cliente y agilizar la orquestación del recorrido.

Obtenga más información y descubra el agente rápidamente en esta [descripción general](https://experienceleague.adobe.com/es/slides/journey-agent-overview).

>[!AVAILABILITY]
>
>Journey Agent está disponible para todos los clientes que tienen acceso a AI Assistant. Sin embargo, necesitará los siguientes permisos para utilizar completamente las funciones de Journey Agent:
>
>**Ver Recorridos**: este permiso le permite ver información sobre el recorrido directamente en el Ayudante de IA.
>
>**Administrar Recorridos**: El permiso Para permite crear nuevos recorridos directamente en el Asistente de IA.
>
>**Ver segmentos**: Este permiso le permite ver información de las audiencias directamente en el Asistente de IA.
>
>**Administrar segmentos**: El permiso Para permite crear nuevas audiencias directamente en el Asistente de IA.

![Muestra para el agente de AJO](./images/ajo-agent/ajo-agent-sample.png)

## Casos de uso

### Principales casos de uso de análisis de Journey Agent

La capacidad de análisis de Journey Agent ofrece una serie de funcionalidades que pueden aprovecharse para optimizar los esfuerzos de marketing:

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

   - Perspectivas de Recorrido basadas en mensajes - Perspectivas operativas de la superficie sobre recorridos , es decir, &quot;muéstreme todos los recorridos en directo&quot;.

Para cada uno de estos análisis, el agente no solo detecta problemas, sino que también proporciona **recomendaciones procesables para resolverlos**.

## Competencias incluidas y excluidas del ámbito de aplicación

### **Ámbito de aplicación**

Las siguientes funcionalidades son compatibles con el análisis de Journey Agent:

- **Consultas reactivas**: permite a los usuarios hacer preguntas específicas sobre el rendimiento del recorrido, el uso del público y los conflictos de programación.
- **Integración con otros agentes**: colabora con Audience Agent y Data Insights Agent para un análisis más profundo.
- **Estructura de la respuesta del agente**: razonamiento (explicar la lógica), resumen del análisis (resaltar puntos clave), detalles del problema (describir el problema) y recomendación (proponer pasos siguientes).

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

- &quot;¿Cuándo se publicó [Nombre de Recorrido]?&quot;
- &quot;¿Cuándo se detuvo [Nombre de Recorrido]?&quot;
- &quot;Enumerar todos los recorridos que están actualmente en modo de prueba&quot;

### Preguntas sobre los recursos del recorrido

- &quot;¿Cuántos recorridos de vida tengo?&quot;
- &quot;Dame una lista de todos los recorridos recurrentes programados y sus tiempos de ejecución esperados&quot;.

### Información sobre el público y el recorrido

- &quot;¿Qué audiencias se utilizan en más de X recorridos?&quot;
- &quot;Enumerar todos los recorridos con la audiencia [audience name]&quot;.

### Análisis de abandonos

- &quot;Quiero analizar las visitas en el orden previsto por nodo para la campaña del 4 de julio de recorrido&quot;.
- &quot;Realizar un análisis de abandonos para la campaña del 4 de julio de recorrido&quot;.
- &quot;¿Qué es la pérdida de perfil en el transcurso de la campaña del 4 de julio de recorrido?&quot;
- &quot;Mostrar dónde caen los usuarios en la campaña del 4 de julio de recorrido&quot;.

### Solicitudes de análisis de conflictos

Utilice estas solicitudes para analizar los posibles conflictos entre recorridos, incluidos los solapamientos de horarios y públicos:

- &quot;¿Puede hacer un análisis completo de los conflictos de nuestro recorrido [Nombre del Recorrido] con información de tipo de conflicto (programación/audiencia) con recorridos en vivo/en ejecución?&quot;
- &quot;Realice un análisis de conflictos de programación para el recorrido [Nombre del Recorrido] con información de tipo de conflicto.&quot;
- &quot;Realice un análisis de superposición de audiencias para el recorrido [Nombre del Recorrido] con información del tipo de conflicto.&quot;
- &quot;¿Hay algún conflicto de programación para el recorrido [Nombre de Recorrido]?&quot;
- &quot;Mostrarme conflictos de superposición de audiencias para el recorrido [Nombre del Recorrido]&quot;.
- &quot;Analice todos los conflictos del recorrido [Nombre de Recorrido] con otros recorridos activos.&quot;
- &quot;¿Cuáles son los conflictos actuales para el recorrido [Nombre de Recorrido]?&quot;
- &quot;Compruebe si el recorrido [Nombre de Recorrido] tiene conflictos de audiencia con otros recorridos&quot;.
- &quot;Compruebe si hay conflictos de programación que impliquen el recorrido [Nombre de Recorrido].&quot;
- &quot;Deseo obtener información sobre todos los conflictos de recorrido de [Nombre de Recorrido]&quot;.
- &quot;¿Hay algún recorrido activo que entre en conflicto con [Nombre de Recorrido] por programación o audiencia?&quot;
- &quot;Identifique los tipos de recorrido [Nombre de Recorrido] en comparación con los recorridos en ejecución.&quot;
- &quot;Mostrar audiencias superpuestas para el recorrido [Nombre del Recorrido] y otros recorridos&quot;.
- &quot;Resaltar las superposiciones de programación entre el recorrido [Nombre del Recorrido] y los recorridos activos.&quot;
- &quot;¿El recorrido [Nombre de Recorrido] está en conflicto con algún otro recorrido?&quot;
- &quot;Detecte y enumere los conflictos de [nombre de Recorrido].&quot;
- &quot;Notificar todos los tipos de conflictos para el recorrido [Nombre del Recorrido].&quot;
- &quot;Proporcionarme un desglose de conflictos (programación y audiencia) para [Nombre de Recorrido]&quot;.
- &quot;¿Tiene [Nombre de Recorrido] algún conflicto que pueda afectar al rendimiento?&quot;
- &quot;¿Hay algún conflicto activo que afecte a [Nombre de Recorrido]?&quot;
- &quot;Enumerar recorridos que entran en conflicto con [Nombre de Recorrido] por programación o audiencia&quot;.
- &quot;¿Ha activado el recorrido [Nombre de Recorrido] alguna alerta de conflicto?&quot;
- &quot;Buscar posibles conflictos de audiencia para el recorrido [Nombre de Recorrido]&quot;.
- &quot;Analice el riesgo de conflicto para el recorrido [Nombre de Recorrido].&quot;
- &quot;Proporcionar diagnósticos de conflicto para [Nombre de Recorrido].&quot;

## Prácticas recomendadas

### Prácticas recomendadas en materia de solicitudes

Para maximizar la eficacia de análisis de Journey Agent, siga estas prácticas recomendadas:

1. **Sea específico**: utilice preguntas claras y concisas para obtener información específica. Por ejemplo, en lugar de preguntar &quot;¿Cuáles son mis recorridos?&quot;, especifique &quot;Enumerar todos los recorridos creados en el último mes&quot;.
1. **Combine información**: integre la información de Audience Agent y Data Insights Agent para obtener una visión integral del rendimiento del recorrido.
1. **Perfeccionamiento iterativo**: utilice el análisis de abandonos y solapamientos para perfeccionar de forma iterativa el diseño y la programación de los recorridos.

### Prácticas recomendadas para la configuración

- **Defina objetivos claros**: antes de analizar los recorridos, establezca objetivos claros (por ejemplo, mejorar la retención, aumentar las conversiones).
- **Monitorice de forma periódica**: programe revisiones periódicas del rendimiento de los recorridos para identificar las tendencias y las anomalías.
- **Optimice la segmentación**: asegúrese de que la segmentación del público está equilibrada para evitar la fatiga y maximizar la participación.

&#x200B;---

## Diapositivas y presentaciones

>[!NOTE]
>
>Las diapositivas y el material de presentación de Journey Agent estarán disponibles aquí. Vuelva pronto para ver las actualizaciones.
