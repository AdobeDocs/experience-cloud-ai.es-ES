---
title: Herramientas de Adobe Analytics en Adobe CX Enterprise MCP
description: Descubra qué herramientas de Adobe Analytics están disponibles a través de Adobe CX Enterprise MCP.
source-git-commit: df05761a8555950366fcaa201ce9c0fd47bb0802
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 4%

---

# Herramientas de Adobe Analytics en Adobe CX Enterprise MCP {#aa-mcp}

Puede utilizar las herramientas de Adobe Analytics para explorar grupos de informes, descubrir dimensiones y métricas, ejecutar informes y administrar componentes de análisis seleccionados desde un cliente compatible con MCP. Estas herramientas están disponibles a través del [Adobe CX Enterprise MCP](overview.md) unificado cuando su cuenta tiene la licencia y los permisos de Adobe Analytics necesarios.

>[!AVAILABILITY]
>
>Las herramientas de Analytics están disponibles para los clientes con una licencia de Adobe Analytics. El acceso está controlado por el permiso **MCP Access** en Adobe Admin Console. Lea [Access CX Enterprise MCP tools](access.md) para obtener más información.

## Funcionalidades clave {#mcp-capabilities}

Las herramientas de Adobe Analytics admiten flujos de trabajo de análisis, descubrimiento y generación de informes desde su cliente de MCP. Se puede:

- Descubra los grupos de informes e inspeccione cómo se configuran.
- Busque dimensiones, métricas, métricas calculadas, segmentos, intervalos de fechas y proyectos de Workspace.
- Ejecute informes de tendencias y clasificación con dimensiones, métricas, intervalos de fechas y filtros de segmento.
- Cree y actualice los componentes reutilizables seleccionados, como segmentos e intervalos de fechas.
- Genere perspectivas a partir de datos de Adobe Analytics utilizando un lenguaje natural.

>[!IMPORTANT]
>
>Algunas herramientas de Adobe Analytics pueden crear o actualizar componentes de Analytics. Revise y valide todos los cambios iniciados por MCP antes de depender de ellos.

## Cobertura de herramienta {#mcp-tools}

| Área | Lo que puede hacer |
| --- | --- |
| Grupos de informes | Descubra los grupos de informes disponibles para su cuenta e inspeccione los detalles de configuración. |
| Componentes | Busque y describa dimensiones, métricas, métricas calculadas, segmentos e intervalos de fechas. |
| Creación de informes | Ejecute informes de tendencias y clasificación utilizando dimensiones, métricas, intervalos de fechas y filtros de segmento seleccionados. |
| Segmentos e intervalos de fechas | Cree y actualice segmentos reutilizables e intervalos de fechas en los que los permisos del producto lo permitan. |
| Proyectos Workspace | Descubra y describa proyectos de Analysis Workspace. |

Para obtener la lista completa y actual de herramientas, consulte la [referencia de la herramienta Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/reference){target="_blank"}.

## Ejemplos de peticiones {#mcp-use-cases}

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| Descubrir grupos de informes | &quot;Enumeración de los grupos de informes a los que puedo acceder&quot;. |
| Buscar componentes | &quot;Encuentre métricas relacionadas con los ingresos&quot;. |
| Ejecutar un informe | &quot;Ejecute un informe de clasificación de vistas de página por página durante los últimos 7 días&quot;. |
| Inspeccionar un segmento | &quot;Describa el segmento `[segment name]` y muéstreme su definición&quot;. |
| Explorar proyectos | &quot;Enumerar mis proyectos de Analysis Workspace relacionados con la adquisición&quot;. |

## Contexto y permisos del producto {#mcp-context}

Su cuenta debe pertenecer a un perfil de producto de Adobe Analytics que incluya el elemento de permiso **Acceso a MCP**, concedido por un administrador de sistemas o productos en Adobe Admin Console.

Los permisos del producto siguen aplicándose. Su cuenta debe poder ver los grupos de informes, los componentes, los informes y los proyectos que consulte, y debe tener los permisos de producto adecuados para las operaciones de escritura, como la creación o actualización de componentes reutilizables.

## Más información {#mcp-more}

Para obtener la referencia completa de la herramienta y la guía de introducción, consulte la [documentación de Adobe Analytics MCP](https://developer.adobe.com/analytics-mcp/docs/aa/){target="_blank"}.