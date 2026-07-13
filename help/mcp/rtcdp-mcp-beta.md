---
solution: Real-Time Customer Data Platform
title: Real-Time CDP MCP (Beta)
description: Obtenga información sobre cómo conectar Adobe Real-Time CDP a clientes MCP mediante el servidor MCP.
feature: Integrations
topic: Content Management, Artificial Intelligence
badge: label="Beta" type="Informative"
role: User, Developer
level: Beginner, Intermediate
hide: true
hidefromtoc: true
index: false
source-git-commit: baab2a961192305bd00ecaae076af277421be210
workflow-type: tm+mt
source-wordcount: '2634'
ht-degree: 0%

---

# Real-Time CDP MCP (Beta) {#rtcdp-mcp}

Puede utilizar la integración de MCP de Adobe Real-Time CDP para consultar audiencias, destinos y estado de activación mediante mensajes en lenguaje sencillo, sin escribir llamadas de API ni navegar por las pantallas de productos. Esta integración sirve tanto a los clientes de Adobe Real-Time CDP como a los de Adobe Real-Time CDP B2B edition, y ofrece una forma conversacional de inspeccionar los datos y flujos de trabajo de Real-Time CDP admitidos de clientes compatibles con MCP. Lea esta guía para conocer cómo funciona la integración, qué puede hacer con ella y cómo empezar.

>[!AVAILABILITY]
>
>El MCP de Real-Time CDP está en Beta. La funcionalidad y la documentación están sujetas a cambios. El servidor MCP de Real-Time CDP se distribuye como un **servidor de transporte HTTP remoto** que los usuarios instalan y configuran en las plataformas de aplicaciones y clientes MCP admitidos (por ejemplo, [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] o [!DNL VS Code]). La autenticación se administra a través de un **flujo de inicio de sesión basado en explorador**: cuando el cliente se conecta por primera vez al servidor, abre el explorador predeterminado para que pueda iniciar sesión con las credenciales de Adobe y autorizar el acceso. Póngase en contacto con su representante de Adobe para acceder a este programa de Beta.

## Beta, seguridad y avisos legales {#mcp-notices}

**Aviso sobre la documentación de Beta:** Esta documentación cubre una función de Beta y no constituye documentación final. El contenido que se describe aquí está relacionado con una versión de Beta y está sujeto a cambios antes de su publicación general. Adobe no realiza ninguna declaración sobre la integridad o precisión de esta documentación.

Al usar Adobe Real-Time CDP MCP Server (Beta) (&quot;Beta&quot;), Usted reconoce por la presente que Beta se proporciona **&quot;tal cual&quot; sin garantía de ningún tipo**. Adobe no tiene obligación de mantener, corregir, actualizar, cambiar, modificar o apoyar de otro modo Beta. Se recomienda tener precaución y no confiar en modo alguno en el correcto funcionamiento o rendimiento de dichos Beta y/o materiales de acompañamiento. Beta se considera información confidencial de Adobe. Cualquier &quot;comentario&quot; (información sobre Beta, incluidos, entre otros, problemas o defectos que encuentre al utilizar Beta, sugerencias, mejoras y recomendaciones) proporcionado por usted a Adobe se asigna a Adobe, incluidos todos los derechos, el título y el interés en y para dichos comentarios.

>[!WARNING]
>
>El Modelo de Protocolo de Contexto (MCP) es un estándar de código abierto emergente y puede presentar riesgos de seguridad o fiabilidad. Las integraciones del servidor de Adobe MCP y la documentación relacionada se proporcionan &quot;tal cual&quot;, sin garantías de ningún tipo.
>
>La conexión de clientes o servidores MCP a productos de Adobe es una configuración seleccionada por el cliente. Los clientes son responsables de evaluar la seguridad y la idoneidad de cualquier integración de MCP. Adobe no se responsabiliza de los problemas que se deriven de una configuración incorrecta, un uso incorrecto del MCP, vulnerabilidades en implementaciones de terceros o acciones no deseadas realizadas a través de flujos de trabajo habilitados para MCP.
>
>Para reducir el riesgo, Adobe recomienda probar las integraciones en un entorno de zona protegida antes de usarlas de forma productiva y revisar y validar cuidadosamente todas las acciones y respuestas iniciadas por MCP antes de confirmarlas o depender de ellas.

## ¿Qué es el protocolo de contexto del modelo? {#mcp-overview}

Los equipos de marketing, datos y experiencia del cliente dependen cada vez más de las aplicaciones basadas en chat y las herramientas para desarrolladores, como Anthropic Claude, OpenAI ChatGPT, Cursor y Microsoft Copilot Studio, para optimizar su trabajo diario. Estas aplicaciones admiten el **Protocolo de contexto de modelo (MCP)**, un estándar abierto que permite a las aplicaciones exponer las herramientas back-end a modelos de lenguaje de gran tamaño (LLM) de manera uniforme.

Real-Time CDP ahora proporciona un servidor MCP que muestra las operaciones de audiencia, destino y activación directamente dentro de cualquier aplicación compatible con MCP. Con la integración de Real-Time CDP MCP, diferentes personas pueden colaborar en torno a los mismos datos de segmentación y activación, sin necesidad de escribir consultas contra las API de REST de Adobe Experience Platform ni navegar por varias pantallas de interfaz de usuario. Los clientes pueden describir su intención de manera conversacional y dejar que el LLM invoque las herramientas de MCP apropiadas.

## Funcionalidades clave {#mcp-capabilities}

El servidor MCP de Real-Time CDP es una superficie de supervisión y evaluación **de solo lectura**. Expone las API de recuperación en audiencias, destinos, fuentes, identidad y resolución de perfiles como respuestas en lenguaje sencillo dentro del asistente de IA, sin necesidad de escribir consultas ni navegar por las pantallas de producto. No se pueden crear, modificar ni eliminar datos a través del servidor MCP.

>[!IMPORTANT]
>
>Todas las herramientas del Beta actual son **de solo lectura**. No se admiten las operaciones de escritura, como crear, activar, actualizar o eliminar audiencias, destinos o flujos de datos.

La versión de Beta incluye las 18 herramientas siguientes:

| Herramienta | Descripción |
| --- | --- |
| `search_audiences` | Enumerar y buscar audiencias por nombre, tipo de entidad, estado del ciclo vital, área de nombres de identidad u origen. |
| `preview_audience_membership` | Calcule el tamaño de una expresión de segmento de PQL o SDD antes de guardarla como audiencia. |
| `inspect_audience_evaluation_jobs` | Recupere registros de trabajos de evaluación de segmentos para diagnosticar por qué una audiencia por lotes no se actualiza o para confirmar el historial de evaluación reciente. |
| `inspect_audience_export_jobs` | Recupere registros de trabajos de exportación de audiencias para confirmar que las exportaciones se han completado o ver detalles de errores. |
| `search_destination_connectors` | Enumerar los tipos de conectores de destino disponibles en la plataforma (por ejemplo, [!DNL Amazon S3], [!DNL Google Ads], [!DNL Salesforce] CRM). |
| `search_destination_accounts` | Enumerar cuentas de destino autenticadas: instancias configuradas de un tipo de conector de destino. |
| `search_destination_input_connections` | Recupere la entrada del lado del Experience Platform de un flujo de destino: la audiencia o el conjunto de datos que se exporta. |
| `search_destination_output_connections` | Recupere el extremo externo de un flujo de destino: ruta de destino, formato de archivo y configuración de envío. |
| `search_destination_flows` | Enumere e inspeccione los flujos de activación de destino configurados, incluido su estado, asignaciones y programación. |
| `inspect_flow_runs` | Recuperar el historial de ejecución para los flujos de origen y destino: estado, tiempo, recuentos de registros y detalles de error por ejecución. |
| `search_source_connectors` | Enumeración de los tipos de conector de origen disponibles en la plataforma. |
| `search_source_accounts` | Enumerar cuentas de origen autenticadas: instancias configuradas de un tipo de conector de origen. |
| `search_source_input_connections` | Recuperar la capa de selección de datos de un flujo de origen: lo que se extrae de una cuenta. |
| `search_source_output_connections` | Recupere el destino del conjunto de datos de Experience Platform de un flujo de origen donde aterrizan los datos introducidos. |
| `search_source_flows` | Enumere e inspeccione las canalizaciones de ingesta de origen configuradas, incluido su estado, asignaciones y programación. |
| `search_identity_namespaces` | Enumerar definiciones de área de nombres de identidad en su zona protegida: áreas de nombres estándar de Adobe y personalizadas. |
| `search_merge_policies` | Registros de políticas de combinación de listas que controlan cómo se ensamblan los perfiles de clientes en tiempo real a partir de fragmentos de perfil. |
| `search_organizations` | Lista de organizaciones de Adobe accesibles para el usuario autenticado. |

## Casos de uso {#mcp-use-cases}

El servidor MCP de Real-Time CDP está diseñado para **supervisión y evaluación**. Dado que el servidor funciona con identificadores en lugar de con nombres, un flujo de trabajo típico comienza con una lista: pídale a Claude que le muestre lo que está disponible, elija el elemento que desee y, a continuación, haga preguntas de seguimiento utilizando el identificador que devuelve.

| Objetivo | Mensaje de ejemplo |
| --- | --- |
| **Enumerar sus audiencias** | &quot;Enumerar mis audiencias en la zona protegida `prod`&quot;. |
| **Inspeccionar una audiencia específica** | &quot;Mostrarme los detalles y el estado del ciclo de vida del ID de audiencia `abc123`&quot;. |
| **Diagnosticar un error de evaluación** | &quot;Mostrarme los trabajos de evaluación más recientes y marcar cualquier error&quot;. |
| **Comprobar un trabajo de exportación** | &quot;Enumerar los trabajos de exportación de audiencias recientes y mostrarme el estado de cada uno&quot;. |
| **Estimar el tamaño de la audiencia** | &quot;Calcule el tamaño de esta expresión de PQL antes de guardarla: `homeAddress.country = 'US'`.&quot; |
| **Enumerar tipos de conector de destino** | &quot;¿Qué tipos de conectores de destino están disponibles en mi zona protegida?&quot; |
| **Enumerar cuentas de destino configuradas** | &quot;Enumerar mis cuentas de destino y su estado de conexión&quot;. |
| **Enumerar flujos de destino** | &quot;Enumerar mis flujos de activación de destino y mostrar cuáles están habilitadas o deshabilitadas&quot;. |
| **Inspeccionar un flujo de destino** | &quot;Mostrarme la configuración completa para el ID de flujo de destino `xyz789`&quot;. |
| **Comprobar el estado de la cuenta de destino** | &quot;Enumerar mis cuentas de destino y marcar cualquiera que esté en estado de error&quot;. |
| **Supervisar ejecuciones de activación recientes** | &quot;Mostrar el flujo se ejecuta desde las últimas 24 horas y marcar cualquier error&quot;. |
| **Investigar una ejecución fallida** | &quot;Mostrarme el historial de ejecución para el identificador de flujo `xyz789` y resumir los errores.&quot; |
| **Flujos de origen de lista** | &quot;Enumerar mis flujos de ingesta de origen y mostrar su estado actual&quot;. |
| **Inspeccionar un flujo de origen** | &quot;Mostrarme la configuración del ID de flujo de origen `src456`: ¿qué está ingiriendo y dónde aterriza?&quot; |
| **Comprobar estado de ejecución de ingesta** | &quot;Mostrarme el historial de ejecución reciente para el identificador de flujo de origen `src456` y los errores de indicador&quot;. |
| **Enumerar áreas de nombres de identidad** | &quot;¿Qué áreas de nombres de identidad se configuran en mi zona protegida?&quot; |
| **Políticas de combinación de listas** | &quot;Enumerar mis políticas de combinación y mostrar cuál es la predeterminada&quot;. |
| **Encuentre su ID de organización** | &quot;Enumerar las organizaciones de Adobe a las que tengo acceso&quot;. |

## Acceso y activación {#mcp-access}

>[!AVAILABILITY]
>
>El servidor MCP de Real-Time CDP está en Beta y no está abierto para la inscripción de autoservicio. El acceso se realiza únicamente por invitación y requiere que la organización de Adobe esté explícitamente incluida en la lista de permitidos para poder conectarse.

Para solicitar acceso:

1. Póngase en contacto con su representante de cuentas de Adobe (Customer Success Manager, Technical Account Manager o Account Executive) y exprese su interés en el programa Beta de MCP de Real-Time CDP.
2. El representante de Adobe se coordinará con el equipo del producto para evaluar la idoneidad y habilitar el ID de la organización.
3. Una vez activado, su representante de Adobe confirmará el acceso y proporcionará cualquier material de incorporación adicional.

>[!NOTE]
>
>Solo las organizaciones que se han habilitado explícitamente pueden conectarse al servidor MCP de Real-Time CDP. Si se intenta conectar antes de la activación, se producirá un error de autenticación.

## Requisitos previos {#mcp-prerequisites}

Antes de conectar el servidor MCP de Real-Time CDP a su cliente MCP, asegúrese de lo siguiente:

* Tiene una licencia de Real-Time CDP activa.
* Su representante de Adobe ha habilitado a su organización de Adobe para el programa Beta (consulte [Acceso y habilitación](#mcp-access)).
* Tiene acceso a un cliente MCP admitido como [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] o [!DNL VS Code].
* Tiene el ID de organización y el nombre de la zona protegida que desea consultar.
* Tiene los permisos necesarios en Adobe Experience Platform para ver audiencias, destinos y entidades de servicios de flujo.

## Conexión del servidor MCP de Real-Time CDP {#mcp-connect}

El punto final del servidor MCP de Real-Time CDP es:

```
https://rtcdp-mcp.adobe.io/mcp
```

El servidor usa un **transporte HTTP remoto (HTTP transmisible)** con un **flujo de inicio de sesión de Adobe basado en explorador**. En cada cliente, el patrón de configuración es el mismo:

1. Agregar la dirección URL del servidor: `https://rtcdp-mcp.adobe.io/mcp`
2. Guarde o habilite la conexión.
3. Complete el **inicio de sesión en Adobe basado en explorador** la primera vez que el cliente invoque una herramienta.
4. Proporcione `imsOrgId` y `sandboxName` al principio de cada sesión.

### Configuración general de JSON {#mcp-connect-json}

Para los clientes que aceptan una configuración de servidor MCP basada en JSON, como Claude Desktop (`claude_desktop_config.json`), VS Code o cualquier cliente que lea un archivo `mcp.json`, utilice uno de los siguientes formatos en función de si el cliente admite HTTP remoto nativo o requiere un puente local:

**A través del puente `mcp-remote` (Claude Desktop y otros clientes que necesitan un puente local)**

```json
{
  "mcpServers": {
    "rtcdp": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://rtcdp-mcp.adobe.io/mcp"
      ]
    }
  }
}
```

**HTTP remoto nativo (clientes que lo admiten directamente)**

```json
{
  "mcpServers": {
    "rtcdp": {
      "url": "https://rtcdp-mcp.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

>[!NOTE]
>
>No se requieren claves API, tokens de portador ni encabezados adicionales en la configuración. La autenticación se administra completamente mediante el flujo de inicio de sesión de Adobe basado en el explorador la primera vez que se utiliza.

### Instalar en clientes basados en IU {#mcp-connect-ui}

#### Claude

Para `claude.ai` y Claude Desktop, agregue el servidor MCP de Real-Time CDP como **conector personalizado** mediante la dirección URL del servidor `https://rtcdp-mcp.adobe.io/mcp`.

* **Planes individuales**: en Claude, vaya a **Personalizar → Connectors**, seleccione **Agregar conector** e introduzca la dirección URL del servidor.
* **Planes de equipo y empresa** — Un **propietario** o **propietario principal** del área de trabajo agrega el conector en **Configuración de la organización → Conectores**. Una vez agregado, cada usuario lo habilita en su propia configuración de Claude.

Una vez agregado el conector, habilítelo en una conversación y complete el inicio de sesión del explorador Adobe la primera vez que lo use. Claude detecta automáticamente el servidor de autorización de Adobe; no se requiere ID de cliente ni secreto de cliente.

#### ChatGPT

En [!DNL ChatGPT], agregue el servidor MCP de Real-Time CDP como **conector personalizado**:

1. Vaya a **Configuración → Conectores** (o **Configuración → Aplicaciones y Conectores**, según su plan).
2. Seleccione **Agregar conector** e introduzca `https://rtcdp-mcp.adobe.io/mcp` como dirección URL del servidor.
3. Guarde el conector. Según el plan de [!DNL ChatGPT], este paso puede requerir **modo de desarrollador** o la aprobación del administrador del área de trabajo.
4. Una vez habilitado el conector, realice la autenticación mediante el inicio de sesión en el explorador Adobe cuando se le solicite la primera vez que utilice.

#### Cursor

En Cursor, agregue el servidor MCP de Real-Time CDP como servidor MCP remoto:

1. Abra **Configuración → MCP**.
2. Seleccione **Agregar nuevo servidor** e introduzca `https://rtcdp-mcp.adobe.io/mcp` como dirección URL del servidor.
3. Seleccione **connect** para almacenar en déclencheur el inicio de sesión de Adobe basado en explorador y autenticarse.

Una vez conectadas, las herramientas de Real-Time CDP están disponibles en los modos Compositor del cursor y Agente.

#### Otros clientes basados en IU

Para clientes como código VS u otras aplicaciones de escritorio y web con compatibilidad con MCP remoto, agregue el servidor MCP de Real-Time CDP como un servidor HTTP **remoto** usando `https://rtcdp-mcp.adobe.io/mcp`. Si el cliente admite encabezados opcionales o tokens de portador, déjelos vacíos: la autenticación se administra mediante el flujo de inicio de sesión de Adobe basado en el explorador la primera vez que se utiliza.

### Instalar en clientes técnicos {#mcp-connect-technical}

#### Código Claude

Añada el servidor desde el terminal:

```bash
claude mcp add --transport http rtcdp https://rtcdp-mcp.adobe.io/mcp
```

A continuación, inicie Claude Code y ejecute:

```text
/mcp
```

Seleccione el servidor `rtcdp` y complete el flujo de inicio de sesión de Adobe en su explorador. Si ya agregó el servidor en `claude.ai`, puede aparecer automáticamente en el código de la cláusula cuando ambos hayan iniciado sesión en la misma cuenta.

#### Códice

Añada el servidor desde el terminal:

```bash
codex mcp add rtcdp --url https://rtcdp-mcp.adobe.io/mcp
```

Autentique el servidor:

```bash
codex mcp login rtcdp
```

Compruebe la configuración:

```bash
codex mcp list
```

También puede agregar el servidor directamente a `~/.codex/config.toml`:

```toml
[mcp_servers.rtcdp]
url = "https://rtcdp-mcp.adobe.io/mcp"
```

### Parámetros de solicitud requeridos {#mcp-connect-params}

Cada llamada a la herramienta requiere dos parámetros que amplían el ámbito de la solicitud a su inquilino de Adobe Experience Platform:

* `imsOrgId`: su ID de organización, asignado al encabezado `x-gw-ims-org-id` en las llamadas a la API de Experience Platform descendentes.
* `sandboxName`: el nombre de la zona protegida de Experience Platform, asignado al encabezado `x-sandbox-name`.

Proporciónelos al principio de cada sesión. Por ejemplo:

> &quot;Use la organización `1234ABCD@AdobeOrg` y la zona protegida `prod` para esta sesión&quot;.

Si no conoce su identificador de organización, pídale al asistente de IA que llame a `search_organizations`, ya que devolverá todas las organizaciones a las que puedan acceder sus credenciales de Adobe.

## Limitaciones conocidas (Beta) {#mcp-limitations}

Las siguientes limitaciones se aplican a la versión actual de Beta del servidor MCP [!DNL Adobe Real-Time CDP]:

| Limitación | Descripción | Solución alternativa |
| --- | --- | --- |
| **Superficie de solo lectura** | El servidor MCP solo expone las API de recuperación. No puede crear, actualizar, activar ni eliminar audiencias, destinos o flujos de datos. | Utilice la interfaz de usuario de Real-Time CDP o las API de REST de Experience Platform para operaciones de escritura. |
| **Sin métricas de participación o envío** | El servidor MCP no devuelve estadísticas de envío descendente, participación o métricas de conversión desde las plataformas de destino. | Utilice los propios informes de la plataforma de destino, Customer Journey Analytics MCP o Adobe Analytics MCP para los datos de participación y conversión. |
| **La consulta de segmentos debe crearse externamente** | `Preview Audience Membership` requiere una expresión PQL o SDD válida como entrada; el servidor MCP no crea la consulta automáticamente. | Cree la expresión PQL/SDD en la interfaz de usuario del Generador de segmentos o a través de la API del servicio de segmentación y péguela en el símbolo del sistema de MCP. |
| **Paginación mediante tokens de continuación** | Las herramientas de lista devuelven resultados paginados. La enumeración completa en zonas protegidas muy grandes requiere encadenar `continuationToken` llamadas. | Reduzca las consultas mediante filtros (nombre, estado, especificación de conexión, intervalo de tiempo) en lugar de enumerar la lista completa. |
| **El filtrado de la ejecución de activación solo se basa en el tiempo** | `Inspect Activation Runs` admite el filtrado por estado y marca de tiempo de finalización (epoch ms UTC), pero no por tipo de error o plataforma de destino directamente. | Filtre primero por `flowId` (obtenido de `List Configured Destinations`) para que el ámbito se ejecute en un destino específico. |
| **Se requiere el identificador de organización al inicio de la sesión** | Cada llamada de herramienta (excepto `search_organizations`) requiere `imsOrgId` y `sandboxName` como parámetros explícitos. Si no se proporcionan, las llamadas a la herramienta fallarán. | Al principio de cada sesión, informe a su asistente de IA: &quot;Utilice la organización `<YOUR_ORG_ID>` y la zona protegida `<SANDBOX_NAME>` para esta sesión&quot;. Si no conoce su identificador de organización, llame primero a `search_organizations` y se devolverán las organizaciones a las que sus credenciales pueden acceder. |

## Preguntas frecuentes {#mcp-faq}

+++¿Qué clientes MCP son compatibles?

El servidor MCP de Real-Time CDP funciona con cualquier cliente que admita servidores MCP remotos o conectores personalizados, incluidos [!DNL Claude], [!DNL ChatGPT], [!DNL Claude Code], [!DNL Codex], [!DNL Cursor] y [!DNL VS Code]. El flujo de instalación depende del cliente: los clientes basados en la interfaz de usuario suelen agregar el servidor desde un panel de configuración o conectores, mientras que los clientes técnicos como Claude Code y Codex pueden agregarlo desde la línea de comandos o archivos de configuración.
+++

+++¿Cómo obtengo acceso?

El acceso se realiza por invitación únicamente durante la Beta. Póngase en contacto con su representante de cuentas de Adobe (Customer Success Manager, Technical Account Manager o Account Executive) para solicitar la inscripción. El representante de Adobe se coordinará con el equipo de productos para habilitar a su organización. Consulte [Acceso y habilitación](#mcp-access) para obtener detalles.
+++

+++¿Cómo funciona la autenticación?

La autenticación se administra mediante un **inicio de sesión basado en explorador**. Cuando el cliente de MCP invoca una herramienta por primera vez, abre el explorador predeterminado a una página de inicio de sesión de Adobe. Después de autenticar y autorizar al cliente, se establece la sesión y las llamadas de herramienta posteriores lo vuelven a utilizar. No es necesario almacenar claves API ni credenciales de larga duración en la configuración del cliente.
+++

+++¿A qué objetos de Real-Time CDP puedo acceder a través de MCP?

Puede acceder a audiencias, tipos de destino, cuentas de destino configuradas, flujos de datos de destino, conexiones de origen y destino e historial de ejecución de activación. Las operaciones son de solo lectura (recuperar API); las operaciones de escritura no son compatibles con la versión actual.
+++

+++¿Necesito acceso de desarrollador para utilizar el servidor MCP de Real-Time CDP?

No. El servidor MCP está diseñado tanto para personalidades técnicas como de marketing. Los especialistas en marketing pueden interactuar con él mediante peticiones de datos en lenguaje natural en cualquier cliente de MCP admitido, mientras que los ingenieros de datos y los desarrolladores pueden utilizarlo en herramientas para desarrolladores compatibles con MCP.
+++
