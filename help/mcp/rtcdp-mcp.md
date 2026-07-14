---
title: Real-Time CDP MCP (Beta)
description: Obtenga información sobre cómo conectar Adobe Real-Time CDP a clientes MCP mediante el servidor MCP.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '786'
ht-degree: 3%

---

# Herramientas Real-Time CDP en CX Coworker Gateway {#rtcdp-mcp}

Puede utilizar las herramientas de producto de Real-Time CDP MCP para inspeccionar audiencias, destinos, fuentes, áreas de nombres de identidad y el estado de activación de un cliente compatible con MCP. Estas herramientas están disponibles a través de la puerta de enlace [CX Coworker Gateway](overview.md) unificada cuando su organización está habilitada y su cuenta de usuario tiene los permisos de Real-Time CDP requeridos.

>[!AVAILABILITY]
>
>La herramienta de producto de Real-Time CDP se encuentra en Beta. El acceso se realiza únicamente por invitación y requiere la habilitación de la organización de Adobe. Consulte [Herramientas de Access CX Coworker Gateway](access.md).

## Funcionalidades clave {#mcp-capabilities}

Las herramientas de Real-Time CDP proporcionan una superficie de monitorización y triaje de solo lectura. Se puede:

* Enumerar e inspeccionar audiencias, incluido el estado del ciclo vital, el origen y el área de nombres de identidad.
* Revise la evaluación de audiencias y los trabajos de exportación para identificar errores recientes.
* Inspeccione las cuentas de destino configuradas, los flujos de destino y el historial de ejecución de activación.
* Inspeccione los conectores de origen, las cuentas, los flujos y el historial de ejecución de ingesta.
* Enumerar áreas de nombres de identidad y políticas de combinación.

>[!IMPORTANT]
>
>Todas las herramientas de Real-Time CDP de la Beta actual son de solo lectura. No se puede crear, actualizar, activar o eliminar audiencias, destinos, fuentes o flujos de datos.

## Herramientas disponibles {#mcp-tools}

| Área | Herramienta | Descripción |
| --- | --- | --- |
| Públicos | `search_audiences` | Enumerar y buscar audiencias por nombre, tipo de entidad, estado del ciclo vital, área de nombres de identidad u origen. |
| Públicos | `preview_audience_membership` | Calcule el tamaño de una expresión de segmento de PQL o SDD antes de guardarla como audiencia. |
| Públicos | `inspect_audience_evaluation_jobs` | Recupere registros de trabajo de evaluación de segmentos para diagnosticar problemas de actualización de audiencias o confirmar el historial de evaluación reciente. |
| Públicos | `inspect_audience_export_jobs` | Recupere registros de trabajos de exportación de audiencias para confirmar que las exportaciones se han completado o aparecen detalles de error. |
| Destinos | `search_destination_connectors` | Enumerar los tipos de conectores de destino disponibles en la plataforma. |
| Destinos | `search_destination_accounts` | Enumerar cuentas de destino autenticadas. |
| Destinos | `search_destination_input_connections` | Recupere la entrada del lado del Experience Platform de un flujo de destino. |
| Destinos | `search_destination_output_connections` | Recupere el extremo externo de un flujo de destino, incluida la ruta de destino, el formato de archivo y la configuración de envío. |
| Destinos | `search_destination_flows` | Enumere e inspeccione los flujos de activación de destino configurados, incluido el estado, las asignaciones y la programación. |
| Destinos y fuentes | `inspect_flow_runs` | Recupere el historial de ejecución del flujo de origen y destino, incluido el estado, el tiempo, los recuentos de registros y los detalles del error. |
| Fuentes | `search_source_connectors` | Enumerar los tipos de conectores de origen disponibles en la plataforma. |
| Fuentes | `search_source_accounts` | Enumerar cuentas de origen autenticadas. |
| Fuentes | `search_source_input_connections` | Recupere lo que extrae un flujo de origen de una cuenta. |
| Fuentes | `search_source_output_connections` | Recupere el destino del conjunto de datos de Experience Platform para un flujo de origen. |
| Fuentes | `search_source_flows` | Enumere e inspeccione las canalizaciones de ingesta de origen configuradas, incluido el estado, las asignaciones y la programación. |
| Identidad | `search_identity_namespaces` | Enumerar definiciones de área de nombres de identidad en su zona protegida. |
| Identidad | `search_merge_policies` | Enumerar registros de políticas de combinación que controlan cómo se ensamblan los perfiles de clientes en tiempo real. |

## Ejemplos de peticiones {#mcp-use-cases}

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| Enumerar audiencias | &quot;Enumerar mis audiencias en la zona protegida `prod`&quot;. |
| Inspeccionar una audiencia | &quot;Mostrarme los detalles y el estado del ciclo de vida del ID de audiencia `abc123`&quot;. |
| Diagnosticar problemas de evaluación | &quot;Mostrarme los trabajos de evaluación de audiencia más recientes y los errores de indicadores&quot;. |
| Comprobación de trabajos de exportación | &quot;Enumerar los trabajos de exportación de audiencias recientes y mostrarme el estado de cada uno&quot;. |
| Calcular tamaño de audiencia | &quot;Calcule el tamaño de esta expresión de PQL antes de guardarla: `homeAddress.country = 'US'`.&quot; |
| Revisar configuración de destino | &quot;Enumerar mis flujos de activación de destino y mostrar cuáles están habilitadas o deshabilitadas&quot;. |
| Investigación de una ejecución de activación fallida | &quot;Mostrarme el historial de ejecución para el identificador de flujo `xyz789` y resumir los errores.&quot; |
| Revisar ingesta de origen | &quot;Mostrarme el historial de ejecución reciente para el identificador de flujo de origen `src456` y los errores de indicador&quot;. |
| Inspeccionar configuración de identidad | &quot;¿Qué áreas de nombres de identidad se configuran en mi zona protegida?&quot; |

## Permisos {#mcp-context}

La organización de Adobe y el contexto de la zona protegida se establecen una vez en el nivel de conexión de puerta de enlace y se aplican a cada familia de herramientas, por lo que no cambia de organización a zona protegida desde las herramientas de Real-Time CDP. Para establecer ese contexto para una sesión, consulte [Contexto del producto para las llamadas de herramienta](install.md#mcp-connect-params).

Su cuenta de usuario debe tener permiso para ver los recursos de Real-Time CDP que consulta. La puerta de enlace no omite los permisos del producto.

## Limitaciones conocidas {#mcp-limitations}

| Limitación | Descripción | Solución alternativa |
| --- | --- | --- |
| Superficie de solo lectura | Las herramientas de Real-Time CDP solo exponen las API de recuperación. No puede crear, actualizar, activar ni eliminar audiencias, destinos, fuentes ni flujos de datos. | Utilice la interfaz de usuario de Real-Time CDP o las API de Experience Platform para realizar operaciones de escritura. |
| Sin métricas de participación ni de envío | Las herramientas no devuelven estadísticas de envío descendente, participación o métricas de conversión desde las plataformas de destino. | Utilice los informes de la plataforma de destino, las herramientas de Customer Journey Analytics o las herramientas de Adobe Analytics para los datos de participación y conversión. |
| La consulta de segmentos debe crearse externamente | `preview_audience_membership` requiere una expresión PQL o SDD válida. La herramienta no crea la consulta por usted. | Cree la expresión en el Generador de segmentos o en la API del servicio de segmentación y péguela en su solicitud. |
| Paginación mediante tokens de continuación | Las herramientas de lista devuelven resultados paginados. La enumeración completa en zonas protegidas muy grandes requiere el encadenamiento de tokens de continuación. | Reduzca las consultas mediante filtros como nombre, estado, especificación de conexión o intervalo de tiempo. |
| El filtrado de la ejecución de activación solo se basa en el tiempo | La inspección de ejecución de activación admite el filtrado por estado y marca de tiempo de finalización, pero no por tipo de error o plataforma de destino directamente. | Filtrar por `flowId` primero para que el ámbito se ejecute en un flujo de destino específico. |

