---
title: Herramientas de Customer Journey Analytics en Adobe CX Enterprise MCP
description: Descubra qué herramientas de Adobe Customer Journey Analytics están disponibles a través de Adobe CX Enterprise MCP.
source-git-commit: 6c73b4d2e452a82597565d71279df2dba605a977
workflow-type: tm+mt
source-wordcount: '674'
ht-degree: 3%

---


# Herramientas de Customer Journey Analytics en Adobe CX Enterprise MCP {#cja-mcp}

Utilice las herramientas de producto de Customer Journey Analytics para explorar vistas de datos, descubrir dimensiones y métricas, ejecutar informes y administrar componentes de análisis seleccionados desde un cliente compatible con MCP. Estas herramientas están disponibles a través de [CX Enterprise MCP](overview.md) cuando su cuenta tiene la licencia y los permisos de Customer Journey Analytics requeridos.

>[!AVAILABILITY]
>
>Las herramientas de Customer Journey Analytics están disponibles para los clientes con una licencia de Customer Journey Analytics. El acceso está controlado por el permiso **MCP Access** en Adobe Admin Console. Consulte [Acceder a las herramientas de MCP de CX Enterprise](access.md).

## Funcionalidades clave {#mcp-capabilities}

Las herramientas de Customer Journey Analytics admiten flujos de trabajo de análisis controlados desde su cliente de MCP. Se puede:

* Descubra las vistas de datos e inspeccione cómo se configuran.
* Busque dimensiones, métricas, métricas calculadas, segmentos, intervalos de fechas, audiencias y proyectos.
* Ejecute informes de tendencias y clasificación con dimensiones, métricas, intervalos de fechas y filtros de segmento.
* Inspeccione las definiciones y el uso de componentes.
* Cree o actualice los componentes de Analytics y los proyectos de Workspace seleccionados.

>[!IMPORTANT]
>
>A diferencia de las herramientas de producto de solo lectura [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) y [Journey Optimizer](ajo-mcp.md), las herramientas de Customer Journey Analytics incluyen operaciones de escritura. Pueden crear y actualizar segmentos, métricas calculadas, intervalos de fechas, proyectos y audiencias. Revise y valide todos los cambios iniciados por MCP antes de depender de ellos.

## Herramientas disponibles {#mcp-tools}

| Área | Herramienta | Descripción |
| --- | --- | --- |
| Configuración y guías | `describeCja` | Devuelve guías de referencia para herramientas, dimensiones, métricas, segmentos, métricas calculadas y estructuras de proyecto. |
| Configuración y guías | `setDefaultSessionDataViewId` | Configura la vista de datos predeterminada en el nivel de sesión para las llamadas a herramientas subsiguientes. |
| Detección | `findDimensions` | Localiza las dimensiones disponibles, con compatibilidad con búsquedas semánticas. |
| Detección | `findMetrics` | Detecta métricas estándar y personalizadas, excluidas las métricas calculadas. |
| Detección | `findCalculatedMetrics` | Explora las métricas calculadas creadas por el usuario y compartidas. |
| Detección | `findSegments` | Enumera los segmentos accesibles para el usuario actual. |
| Detección | `findDateRanges` | Recupera componentes de intervalo de fechas guardados. |
| Detección | `findDataViews` | Detecta las vistas de datos disponibles. |
| Detección | `findProjects` | Localiza proyectos de Workspace. |
| Detección | `findAudiences` | Muestra los componentes de audiencia disponibles. |
| Creación de informes y análisis | `runReport` | Ejecuta informes de clasificación con dimensiones, métricas, intervalos de fechas y filtros de segmento opcionales. |
| Creación de informes y análisis | `searchDimensionItems` | Recupera los valores de dimensión necesarios para los informes de desglose. |
| Detalles del componente | `describeDimension` | Muestra metadatos detallados para una dimensión específica. |
| Detalles del componente | `describeMetric` | Devuelve metadatos de métricas y detalles de mediciones. |
| Detalles del componente | `describeSegment` | Muestra la definición de un segmento y la información de compatibilidad. |
| Detalles del componente | `describeCalculatedMetric` | Muestra la fórmula y las métricas base utilizadas. |
| Detalles del componente | `describeProject` | Detalla la configuración de un proyecto de Workspace. |
| Detalles del componente | `describeAudience` | Devuelve los metadatos de audiencia y el estado de publicación. |
| Uso de componentes | `listComponentUsage` | Clasifica los componentes por frecuencia de uso. |
| Uso de componentes | `listFrequentlyUsedWith` | Identifica los componentes que comúnmente se emparejan entre sí. |
| Uso de componentes | `listSimilarTo` | Encuentra componentes alternativos con fines similares. |
| Crear y actualizar | `upsertSegment` | Crea un segmento nuevo o modifica uno existente. |
| Crear y actualizar | `upsertCalculatedMetric` | Crea una nueva métrica calculada o modifica una existente. |
| Crear y actualizar | `createDateRange` | Crea un componente de intervalo de fechas reutilizable. |
| Crear y actualizar | `upsertProject` | Crea un nuevo proyecto de Workspace o modifica uno existente. |
| Crear y actualizar | `upsertAudience` | Crea una nueva definición de audiencia o modifica una existente. |

## Ejemplos de peticiones {#mcp-use-cases}

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| Enumerar vistas de datos | &quot;Enumerar las vistas de datos disponibles para mí en Customer Journey Analytics&quot;. |
| Descubrir componentes | &quot;Busque métricas relacionadas con los ingresos en la vista de datos `[data view name]`.&quot; |
| Ejecutar un informe | &quot;Ejecutar un informe de tendencias de pedidos por mes para el último trimestre.&quot; |
| Desglose de una métrica | &quot;Mostrarme los 10 canales de marketing principales por visitas, desglosados por tipo de dispositivo&quot;. |
| Inspeccione un componente | &quot;Describa el segmento `[segment name]` y muéstreme su definición&quot;. |
| Uso de auditoría | &quot;¿Qué dimensiones se utilizan con mayor frecuencia en mis proyectos?&quot; |
| Creación de segmentos | &quot;Cree un segmento para los usuarios que vieron la página de precios en los últimos 30 días&quot;. |

## Contexto y permisos del producto {#mcp-context}

Su cuenta debe pertenecer a un perfil de producto de Customer Journey Analytics que incluya el elemento de permiso **Acceso a MCP**, concedido por un administrador de sistemas o productos en Adobe Admin Console.

Los permisos del producto siguen aplicándose. Su cuenta debe poder ver las vistas de datos, los componentes, los proyectos y las audiencias que consulte, y debe tener los permisos de producto adecuados para las operaciones de escritura, como la creación o actualización de segmentos, métricas calculadas, intervalos de fechas, proyectos o audiencias.

## Míralo en acción {#mcp-videos}

**Información general**

>[!VIDEO](https://video.tv.adobe.com/v/3486313/?learn=on&enablevpops)

**En acción**

>[!VIDEO](https://video.tv.adobe.com/v/3486314/?learn=on&enablevpops)

## Más información {#mcp-more}

Para obtener la referencia completa de la herramienta y la guía de introducción, consulte la [documentación de Customer Journey Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/cja/){target="_blank"}.