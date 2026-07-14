---
title: Herramientas de contexto de sesión en CX Coworker Gateway
description: Obtenga información sobre las herramientas principales que establecen el contexto de organización, zona protegida y vista de datos para todas las llamadas a la herramienta CX Coworker Gateway.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '656'
ht-degree: 0%

---

# Herramientas de contexto de sesión en Adobe CX Coworker Gateway {#mcp-core}

Adobe CX Coworker Gateway incluye un conjunto de herramientas de contexto de sesión que establecen la organización de Adobe, la zona protegida de Adobe Experience Platform y la vista de datos de Customer Journey Analytics en las que funcionan todas las demás herramientas de producto. No se requiere ninguna licencia ni habilitación adicional: estas herramientas están disponibles para todos los usuarios autenticados después de conectarse al [servidor CX Coworker Gateway](overview.md).

## Funcionamiento del contexto {#mcp-core-how}

CX Coworker Gateway analiza cada llamada de herramienta a una organización de Adobe activa. Además, los requisitos de contexto dependen del producto:

- **Los productos basados en Experience Platform** — las herramientas [Real-Time CDP](rtcdp-mcp.md), [Experience Platform](aep-mcp.md) y [Journey Optimizer](ajo-mcp.md) funcionan dentro de una zona protegida de Experience Platform. Establezca la zona protegida una vez por sesión con `core-set_sandbox`; los tres la comparten.
- **Otros productos**: los productos que no se hayan creado en Experience Platform no usan el contexto de zona protegida. Por ejemplo, las herramientas de [Customer Journey Analytics](cja-mcp.md) se resuelven con una vista de datos y las herramientas de [Adobe Analytics](analytics-mcp.md) se resuelven con los grupos de informes.

Definir contexto una vez al principio de una sesión: las herramientas de producto individuales no cambian entre organizaciones, zonas protegidas o vistas de datos a mitad de la sesión.

## Herramientas disponibles {#mcp-core-tools}

| Herramienta | Descripción |
| --- | --- |
| `core-list_orgs` | Muestra las organizaciones de Adobe accesibles para el usuario autenticado. Devuelve el nombre para mostrar y el identificador `@AdobeOrg` de cada organización. Use esto para buscar el identificador de organización antes de llamar a `core-switch_org`. |
| `core-switch_org` | Establece la organización de Adobe activa para la sesión. Todas las llamadas de herramienta subsiguientes se vinculan a esta organización hasta que finalice la sesión o se vuelva a cambiar la organización. |
| `core-list_sandboxes` | Muestra los entornos limitados de Experience Platform disponibles en la organización activa. Devuelve el nombre, el título, el tipo (producción o desarrollo) y el estado de cada zona protegida. Use esto para buscar un nombre de zona protegida antes de llamar a `core-set_sandbox`. |
| `core-set_sandbox` | Establece la zona protegida de Experience Platform activa para la sesión. Las herramientas de Real-Time CDP, Experience Platform y Journey Optimizer enmarcan sus datos en esta zona protegida. |
| `core-list_dataviews` | Enumera las vistas de datos de Customer Journey Analytics disponibles para el usuario autenticado en el contexto actual. Devuelve los ID de vista de datos y los nombres para mostrar. Use esto para buscar una vista de datos antes de llamar a `core-set_dataview`. |
| `core-set_dataview` | Establece la vista de datos predeterminada de Customer Journey Analytics para la sesión. Cuando se configura, las herramientas de CJA que requieren una vista de datos (como `findDimensions`, `findMetrics` y `runReport`) utilizarán este valor automáticamente a menos que se especifique una vista de datos diferente en la llamada de herramienta individual. |

## Configuración típica de la sesión {#mcp-core-setup}

Establezca el contexto al principio de una sesión antes de invocar las herramientas de producto:

1. **Organización** — Llame a `core-list_orgs` para enumerar sus organizaciones accesibles y luego a `core-switch_org` con el identificador de organización de destino.
2. **Zona protegida**: si planea usar herramientas de Real-Time CDP, Experience Platform o Journey Optimizer, llame a `core-list_sandboxes` para ver una lista de las zonas protegidas disponibles y, a continuación, `core-set_sandbox` con el nombre de la zona protegida de destino.
3. **Vista de datos** (solo CJA): si planea usar las herramientas de Customer Journey Analytics, llame a `core-list_dataviews` para ver una lista de las vistas de datos disponibles y luego a `core-set_dataview` con la vista de datos que haya elegido.

Puede pedir a su cliente MCP que complete esta configuración en una única solicitud en lenguaje natural:

> &quot;Use la organización `1234ABCD@AdobeOrg`, la zona protegida `prod` y la vista de datos `My Company — Global` para esta sesión&quot;.

El cliente llamará a las herramientas adecuadas y confirmará una vez establecido el contexto.

>[!TIP]
>
>Si las credenciales de Adobe pertenecen a una sola organización, `core-list_orgs` y `core-switch_org` siguen funcionando, pero la organización efectiva será la misma independientemente. Aún debe llamar a `core-set_sandbox` si planea usar las herramientas de Real-Time CDP, Experience Platform o Journey Optimizer, y a `core-set_dataview` si planea usar las herramientas de Customer Journey Analytics.

## Ejemplos de peticiones {#mcp-core-examples}

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| Descubra las organizaciones disponibles | &quot;¿A qué organizaciones de Adobe tengo acceso?&quot; |
| Definir contexto de organización | &quot;Cambiar a la organización `My Org (1234ABCD@AdobeOrg)`.&quot; |
| Descubra las zonas protegidas disponibles | &quot;Enumerar los entornos limitados disponibles en mi organización actual&quot;. |
| Establecer contexto de zona protegida | &quot;Usar la zona protegida `prod` para esta sesión&quot;. |
| Descubra las vistas de datos disponibles | &quot;¿A qué vistas de datos de Customer Journey Analytics puedo acceder?&quot; |
| Establecer contexto de vista de datos | &quot;Establecer `My Company — Global` como vista de datos predeterminada.&quot; |
| Configuración de sesión completa | &quot;Configure una sesión utilizando la organización `1234ABCD@AdobeOrg`, la zona protegida `prod` y la vista de datos `My Company — Global`&quot;. |

## Páginas relacionadas {#mcp-core-related}

- [Instalar Adobe CX Coworker Gateway](install.md): cómo conectar su cliente MCP, incluida la sección de configuración del contexto del producto.
- [Acceder a las herramientas de puerta de enlace de Coworker de CX](access.md) — requisitos de acceso por producto.