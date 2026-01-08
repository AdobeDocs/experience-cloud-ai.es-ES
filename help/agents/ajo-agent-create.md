---
title: Recorrido Crear resumen de aptitudes del agente
description: Aprenda a utilizar la habilidad Crear de Journey Agent para crear recorridos de marketing a través de mensajes en lenguaje natural en Journey Optimizer.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer
feature: AI Assistant
topic: Administration
level: Beginner
source-git-commit: 864002185f3745ca76180af192f616d1e5da0791
workflow-type: tm+mt
source-wordcount: '1068'
ht-degree: 1%

---


# Recorrido Crear agente: descripción general de aptitudes y guía del usuario

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

