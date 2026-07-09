---
title: Servidor MCP empresarial de Adobe CX
description: El servidor MCP de Adobe CX Enterprise es el MCP unificado para Adobe CX Enterprise, lo que proporciona a los clientes de MCP una única conexión a las herramientas de producto compatibles.
source-git-commit: b40034bdc866a2737b909386b79c028793f324cb
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 4%

---

# Servidor MCP empresarial de Adobe CX {#mcp-overview}

El servidor MCP de Adobe CX Enterprise es el protocolo de contexto de modelo unificado (MCP) para Adobe CX Enterprise. Con una conexión, los clientes compatibles con MCP pueden acceder a las herramientas de producto de Adobe que su organización y su cuenta pueden utilizar.

>[!IMPORTANT]
>
>Para poder utilizar las herramientas MCP de CX Enterprise, su organización de Adobe debe estar habilitada. Si su organización aún no tiene acceso, póngase en contacto con el equipo de cuenta de Adobe para solicitar la habilitación de su organización.

Use el punto final de CX Enterprise para toda la configuración de cliente de MCP:

```
https://cx-enterprise.adobe.io/mcp
```

Después de conectarse, el extremo expone las herramientas disponibles para su organización y credenciales de Adobe. Las páginas específicas del producto en esta guía describen qué puede hacer cada herramienta de producto, a qué datos puede acceder y cualquier limitación específica del producto.

## ¿Qué es el protocolo de contexto del modelo? {#mcp-what-is}

MCP (Model Context Protocol) es un estándar de código abierto para conectar aplicaciones de IA a sistemas externos. Los clientes compatibles con MCP como [!DNL Claude], [!DNL ChatGPT], [!DNL Cursor], [!DNL Claude Code], [!DNL Codex] y [!DNL VS Code] pueden utilizar esas herramientas para recuperar el contexto del producto, ejecutar operaciones compatibles y devolver respuestas en lenguaje natural.

CX Enterprise proporciona un punto final controlado para las herramientas de producto de CX Enterprise. En lugar de añadir servidores de producto independientes, conéctese una vez al punto de conexión y utilice las herramientas de producto que aparecen para las soluciones con derechos.

## Herramientas de producto disponibles {#available-product-tools}

En esta guía se documentan las siguientes herramientas de producto:


| Herramientas de producto | Lo que expone a través del extremo | Disponibilidad | Documentación |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ------------ | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Real-Time CDP** | Audiencias, destinos, fuentes, áreas de nombres de identidad y estado de activación (solo lectura) | Beta | [Herramientas de Real-Time CDP](rtcdp-mcp.md) |
| **Experience Platform** | Esquemas, conjuntos de datos, control de datos, servicio de consultas y eventos de auditoría (solo lectura) | Beta | [Herramientas de Experience Platform](aep-mcp.md) |
| **Journey Optimizer** | Campañas y configuraciones de canal (solo lectura) | Beta | [Herramientas de Journey Optimizer](ajo-mcp.md) |
| **Customer Journey Analytics** | Vistas de datos, dimensiones, métricas, informes, segmentos, intervalos de fechas, proyectos y audiencias (lectura y escritura) | Disponible | [Herramientas de Customer Journey Analytics](cja-mcp.md) |
| **Adobe Analytics** | Grupos de informes, dimensiones, métricas, informes, segmentos, intervalos de fechas y proyectos de Workspace (lectura y escritura para componentes compatibles) | Disponible | [Herramientas de Adobe Analytics](analytics-mcp.md) |
| **Workfront** | Herramientas de administración de trabajo para proyectos, tareas y flujos de trabajo de aprobación | Vista previa | [Servidor MCP de Workfront](https://experienceleague.adobe.com/en/docs/workfront/using/basics/workfront-mcp-server/workfront-mcp-server-overview) |


>[!NOTE]
>
>La disponibilidad de las herramientas depende de las licencias de los productos, la habilitación de la organización, los permisos de los productos y las credenciales de Adobe utilizadas para la autenticación. El MCP solo muestra las herramientas a las que su organización y su cuenta de usuario tienen derecho de acceso. Consulte [Acceder a las herramientas de MCP de CX Enterprise](access.md).



## Introducción {#mcp-get-started}

1. Revise [Acceder a las herramientas de MCP de CX Enterprise](access.md) para confirmar la disponibilidad, habilitación y permisos del producto.
2. Siga [Instalar Adobe para CX Enterprise MCP](install.md) para conectar su cliente MCP al extremo.
3. Revise la página del producto para cada herramienta de producto que planee utilizar.

