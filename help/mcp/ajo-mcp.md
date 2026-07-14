---
title: Herramientas Adobe Journey Optimizer en CX Coworker Gateway
description: Descubra qué herramientas de Adobe Journey Optimizer están disponibles a través de CX Coworker Gateway.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '534'
ht-degree: 3%

---

# Herramientas Adobe Journey Optimizer en CX Coworker Gateway {#ajo-mcp}

Utilice las herramientas de producto de Adobe Journey Optimizer para inspeccionar campañas y configuraciones de canal desde un cliente compatible con MCP. Estas herramientas están disponibles a través de [CX Coworker Gateway](overview.md) cuando su organización está habilitada y su cuenta de usuario tiene los permisos de Journey Optimizer requeridos.

>[!AVAILABILITY]
>
>Las herramientas de producto de Journey Optimizer se encuentran en Beta. El acceso se realiza únicamente por invitación y requiere la habilitación de la organización de Adobe. Consulte [Herramientas de Access CX Coworker Gateway](access.md).

## Funcionalidades clave {#mcp-capabilities}

Las herramientas de Journey Optimizer proporcionan una superficie de solo lectura para la revisión de la configuración de campañas y canales. Se puede:

- Enumere las campañas de Journey Optimizer y filtre por estado.
- Recupere detalles de la campaña, incluidos los metadatos de segmentación, programación, canal y configuración de contenido.
- Enumere las configuraciones de canal para los canales de correo electrónico, SMS, push y WhatsApp.
- Revise la configuración de campaña y canal en lenguaje natural sin navegar por las pantallas de producto.

>[!IMPORTANT]
>
>Todas las herramientas de Journey Optimizer de la Beta actual son de solo lectura. No se puede crear, actualizar, eliminar, iniciar, detener o publicar campañas.

## Herramientas disponibles {#mcp-tools}

| Herramienta | Descripción |
| --- | --- |
| `ajo_campaign_list` | Examine las campañas de marketing de Journey Optimizer. Admite el filtrado por estado, como `DRAFT`, `LIVE`, `STOPPED` y `COMPLETED`. |
| `ajo_campaign_get` | Obtenga detalles y configuración de una campaña específica por ID, incluidos metadatos de segmentación de audiencia, programación, canal y configuración de contenido. |
| `ajo_channel_configuration_list`, `ajo_channel_configuration_get` | Vea los ajustes preestablecidos de superficie y la configuración de marca para los canales de correo electrónico, SMS, push o [!DNL WhatsApp]. |

## Ejemplos de peticiones {#mcp-use-cases}

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| Información general de Campaign | &quot;Mostrarme todas mis campañas de Journey Optimizer&quot;. |
| Auditoría de estado | &quot;¿Qué campañas están activas actualmente?&quot; |
| Detalles de la campaña | &quot;Obtener todos los detalles de la campaña `[campaign ID]`&quot;. |
| Audiencia y segmentación | &quot;¿A qué audiencia se dirige la campaña `[campaign ID]`?&quot; |
| Programación y calendario | &quot;¿Cuándo está programado que se ejecute la campaña `[campaign ID]`?&quot; |
| Resolución de problemas | &quot;Revise la configuración de la campaña `[campaign ID]` y marque los posibles problemas&quot;. |
| Configuración de canal | &quot;¿Qué configuraciones de canal de correo electrónico están disponibles?&quot; |
| Auditoría de canales | &quot;¿Qué configuraciones de canal faltan o están incompletas?&quot; |

## Contexto y permisos del producto {#mcp-context}

La cuenta de usuario debe tener permiso para ver las campañas de Journey Optimizer y las configuraciones de canal que consulte. El MCP no omite los permisos del producto.

Si su organización utiliza varios entornos limitados, especifique el contexto del entorno o la zona protegida en el mensaje cuando necesite resultados de un entorno limitado específico.

## Limitaciones conocidas {#mcp-limitations}

| Limitación | Descripción | Solución alternativa |
| --- | --- | --- |
| Superficie de solo lectura | Las herramientas de Journey Optimizer solo exponen las operaciones de recuperación. No puede crear, actualizar, eliminar, iniciar, detener ni publicar campañas. | Utilice la interfaz de usuario o las API de Journey Optimizer para realizar operaciones de escritura. |
| Sin métricas de participación ni de rendimiento | Las herramientas no devuelven datos de informes como impresiones, tasas de pulsaciones, conversiones o estadísticas de envío. | Utilice los informes de Journey Optimizer, las herramientas de Customer Journey Analytics o las herramientas de Adobe Analytics para las métricas de rendimiento. |
| La paginación de la lista de campañas es limitada | La lista de campañas devuelve la primera página de resultados, con un máximo de 50 campañas ordenadas alfabéticamente. Los valores de desplazamiento y límite no se aplican. | Use `Get Campaign` directamente si se conoce el ID de campaña. Utilice la interfaz de usuario de Journey Optimizer para realizar exploraciones y filtros completos. |
| Sin filtrado del lado del servidor por fecha, canal o programación | La lista de campañas admite el filtrado de estado, pero no el filtrado de fecha de publicación, fecha de programación, canal o tipo de campaña. | Utilice la lista de campañas de la IU de Journey Optimizer para el filtrado nativo de fechas y canales. |
| Recuperación de contenido de mensaje no disponible | Message HTML, las líneas de asunto, los tokens de personalización y el contenido de las ofertas no están disponibles a través de las herramientas actuales. | Vea el contenido y la personalización del mensaje directamente en la interfaz de usuario de Journey Optimizer. |