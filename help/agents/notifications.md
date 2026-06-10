---
title: Agente de notificaciones
description: Aprenda a utilizar el agente de notificaciones en el asistente de IA para resumir, interpretar y actuar en las notificaciones de Adobe CX Enterprise utilizando un lenguaje natural.
source-git-commit: d4254ada196055b869e6392b6d8cc2d4a037c4ad
workflow-type: tm+mt
source-wordcount: '405'
ht-degree: 1%

---

# Agente de notificaciones

El agente de notificaciones agrega una capa de IA conversacional dentro de [Asistente de IA](../ai-assistant/ai-assistant-ui.md) que puede usar para resumir, interpretar y actuar en las notificaciones mediante lenguaje natural, convirtiendo así una fuente pasiva en un asistente activo. En lugar de escanear una lista larga, puede pasar de &quot;Tengo 47 notificaciones&quot; a &quot;2 necesito mi aprobación para el viernes, 3 conjuntos de datos tienen conflictos, el resto es para su información&quot; en un solo intercambio.

## Qué puede hacer el agente de notificaciones

El agente de notificaciones admite las siguientes funciones:

| Competencias | Descripción |
| --- | --- |
| **Resúmenes de notificaciones y datos** | Obtenga información general concisa de sus notificaciones, distinga claramente entre las que requieren acción y las que solo son informativas, y comprenda tanto el propósito de una notificación como el motivo por el que la recibió. |
| **Acciones operativas** | Realizar acciones en las notificaciones directamente a través de la conversación: marcarlas como leídas, posponerlas o configurar recordatorios para notificaciones individuales o agrupadas. |
| **Preferencias y configuración** | Habilite o deshabilite los canales de notificación (correo electrónico, Slack, en la aplicación) por solución y categoría, sin navegar por la Configuración. |
| **Navegación y vinculación profunda** | Saltar de una notificación directamente al área de producto correspondiente mediante vínculos profundos. |
| **Collaboration y uso compartido** | Comparta notificaciones o envíe anuncios a destinatarios de la misma organización. |

## Agente de notificaciones de acceso

Puede acceder al Agente de notificaciones de las siguientes maneras:

- **Desde el Asistente de IA**: Abra el Asistente de IA e introduzca cualquier mensaje relacionado con las notificaciones.
- **En la biblioteca de mensajes**: seleccione un mensaje sugerido que se ajuste a sus necesidades.

## Ejemplos de peticiones de datos

Lea las siguientes secciones para ver ejemplos de mensajes que puede utilizar con el Agente de notificaciones.

### Resúmenes e información

- &quot;Resumir mis notificaciones recientes&quot;.
- &quot;¿Cuál de mis notificaciones necesita mi acción o qué es solo para mi información?&quot;

### Acciones

- &quot;Marcar todas las notificaciones no procesables como leídas&quot;.
- &quot;Recordatorio de la notificación {NOTIFICATION_OF_INTEREST} en una hora&quot;.

### Preferencias

- &quot;Habilitar las notificaciones de Slack para Journey Optimizer&quot;.
- &quot;Cambiar mi resumen diario a semanal&quot;.

### Colaboración

- &quot;Compartir esta notificación con {EMAIL_ADDRESS_OF_USER_IN_YOUR_ORG}.&quot;

## Prácticas recomendadas

Tenga en cuenta las siguientes sugerencias al utilizar el Agente de notificaciones:

- **Sea específico**: Asigne claramente un nombre a la aplicación, la notificación, la categoría de notificación y el canal para que el agente pueda actuar en el destino deseado.
- **Mensajes en cadena**: puede solicitar un resumen, realizar un seguimiento centrándose en una notificación específica y, a continuación, realizar una acción, todo ello dentro de una sola conversación.
- **Responder preguntas para aclarar**: cuando el agente pida confirmación sobre la aplicación, el canal o la notificación, asegúrese de responder para que los cambios se apliquen correctamente.
