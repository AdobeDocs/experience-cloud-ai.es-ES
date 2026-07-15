---
title: Instalar Adobe CX Coworker Gateway
description: Aprenda a conectar clientes compatibles con MCP a Adobe CX Coworker Gateway.
source-git-commit: 9f654bc1f7282cad51ef54b86167dbea1757364a
workflow-type: tm+mt
source-wordcount: '1004'
ht-degree: 0%

---

# Instalar Adobe CX Coworker Gateway {#mcp-install}

Lea esta guía para aprender a conectar un cliente compatible con MCP a Adobe CX Coworker Gateway.  CX Coworker Gateway utiliza un punto final para todas las herramientas de producto documentadas:

```
https://cx-coworker-gateway.adobe.io/mcp
```

Antes de instalar, confirme que su organización y cuenta de usuario pueden acceder a las herramientas de producto que necesita. Consulte [Herramientas de Access CX Coworker Gateway](access.md).

## Funcionamiento de la instalación {#mcp-install-how}

CX Coworker Gateway utiliza un transporte HTTP remoto con un flujo de inicio de sesión Adobe basado en explorador. En todos los clientes admitidos, el patrón de configuración es el mismo:

1. Agregar la dirección URL del extremo: `https://cx-coworker-gateway.adobe.io/mcp`.
2. Guarde o habilite la conexión.
3. Complete el inicio de sesión de Adobe basado en explorador la primera vez que el cliente invoque una herramienta.
4. Defina el contexto del producto para la sesión si las herramientas lo requieren: organización para todos los productos, zona protegida para herramientas basadas en Experience Platform y vista de datos para Customer Journey Analytics. Ver [contexto de producto para llamadas de herramienta](#mcp-connect-params).

>[!NOTE]
>
>En la configuración del cliente de MCP no se requieren claves API, tokens de portador, secretos de cliente ni encabezados adicionales. La autenticación se administra mediante el flujo de inicio de sesión de Adobe la primera vez que se utiliza.

## Instalación empresarial (administrada por el administrador) {#mcp-install-enterprise}

La mayoría de los planes de cliente de MCP empresarial y de equipo requieren que un administrador agregue conectores personalizados para la organización. En estos entornos, la instalación tiene dos pasos:

1. Un administrador añade el punto final de CX Coworker Gateway una vez para la organización.
2. Cada usuario habilita el conector e inicia sesión con sus propias credenciales de Adobe.

### Paso 1: Un administrador agrega el extremo {#mcp-install-enterprise-admin}

El administrador agrega `https://cx-coworker-gateway.adobe.io/mcp` como conector personalizado o servidor MCP remoto en la configuración de organización del cliente. La ubicación exacta depende del cliente.

#### Claude Team y Enterprise {#mcp-install-enterprise-claude}

En los planes de [!DNL Claude] equipo y empresa, los conectores a nivel de organización son administrados por un **propietario** o **propietario principal** del área de trabajo.

1. Inicie sesión en [!DNL Claude] como **propietario** o **propietario principal**.
2. Vaya a **Configuración** > **Administración** > **Conectores**. En algunos planes, esto aparece como **Configuración de la organización** > **Conectores**.
3. Seleccione **Agregar conector personalizado**.
4. Escriba `https://cx-coworker-gateway.adobe.io/mcp` como URL del servidor y use un nombre reconocible, como &quot;Puerta de enlace de Adobe for CX Coworker&quot;.
5. Guarde el conector.

#### Equipo y empresa de ChatGPT {#mcp-install-enterprise-chatgpt}

En [!DNL ChatGPT] espacios de trabajo de equipo y empresariales, un administrador del espacio de trabajo agrega los conectores.

1. Inicie sesión en [!DNL ChatGPT] como administrador de área de trabajo.
2. Vaya a **Configuración** > **Conectores**. En algunos planes, esto aparece como **Configuración** > **Aplicaciones y conectores**.
3. Seleccione **Agregar conector**.
4. Escriba `https://cx-coworker-gateway.adobe.io/mcp` como URL del servidor.
5. Guarde el conector. Según la configuración del espacio de trabajo, este paso puede requerir la activación del modo de desarrollador o la concesión de una aprobación de nivel de espacio de trabajo.

#### Otros clientes administrados por la organización {#mcp-install-enterprise-other}

Para otros clientes que admiten conectores remotos administrados por la organización, agregue CX Coworker Gateway como servidor HTTP MCP remoto mediante `https://cx-coworker-gateway.adobe.io/mcp`. Deje vacíos los encabezados opcionales, los campos de token de portador, los campos de ID de cliente y los campos de secreto de cliente, a menos que el cliente requiera un valor de marcador de posición.

### Paso 2: Los usuarios habilitan el conector {#mcp-install-enterprise-user}

Una vez que un administrador añade CX Coworker Gateway, cada usuario lo activa para su propia cuenta:

1. Abra el conector personal, la aplicación o la configuración de MCP en el cliente.
2. Busque el conector CX Coworker Gateway y actívelo.
3. Inicie una conversación, invoque una de las herramientas de Adobe y complete el inicio de sesión de Adobe basado en el explorador cuando se le solicite.
4. Defina el contexto del producto para la sesión si las herramientas lo requieren: organización para todos los productos, zona protegida para herramientas basadas en Experience Platform y vista de datos para Customer Journey Analytics. Ver [contexto de producto para llamadas de herramienta](#mcp-connect-params).

Los usuarios no necesitan introducir la URL ellos mismos cuando un administrador ya ha añadido el conector para la organización.

## Instalación individual (autoservicio) {#mcp-install-individual}

Si utiliza un plan individual, un cliente para desarrolladores configurado localmente o una organización que permita a los miembros agregar sus propios conectores, agregue el punto de conexión directamente en la configuración de su propio cliente.

### Claude individual {#mcp-install-individual-claude}

Para `claude.ai` y [!DNL Claude] escritorio en un plan individual:

1. Abra **Configuración** > **Conectores**.
2. Seleccione **Agregar conector personalizado**.
3. Escriba `https://cx-coworker-gateway.adobe.io/mcp` como URL del servidor.
4. Guarde y habilite el conector y, a continuación, complete el flujo de inicio de sesión de Adobe la primera vez que lo utilice.

### ChatGPT individual {#mcp-install-individual-chatgpt}

1. Abra **Configuración** > **Conectores**. En algunos planes, esto aparece como **Configuración** > **Aplicaciones y conectores**.
2. Seleccione **Agregar conector**.
3. Escriba `https://cx-coworker-gateway.adobe.io/mcp` como URL del servidor.
4. Guarde y habilite el conector y, a continuación, complete el flujo de inicio de sesión de Adobe la primera vez que lo utilice.

### Cursor {#mcp-install-individual-cursor}

1. Abra **Configuración** > **MCP**.
2. Seleccione **Agregar nuevo servidor**.
3. Escriba `https://cx-coworker-gateway.adobe.io/mcp` como URL del servidor.
4. Seleccione **Conectar** y complete el flujo de inicio de sesión de Adobe.

Después de la conexión, las herramientas denominadas Adobe for CX Coworker Gateway están disponibles en los modos Compositor del cursor y Agente.

### Código Claude {#mcp-install-individual-claude-code}

Agregue el punto final desde el terminal:

```bash
claude mcp add --transport http cx-enterprise https://cx-coworker-gateway.adobe.io/mcp
```

A continuación, inicie [!DNL Claude Code] y ejecute:

```text
/mcp
```

Seleccione el servidor `cx-enterprise` y complete el flujo de inicio de sesión de Adobe en su explorador.

### Códice {#mcp-install-individual-codex}

Agregue el punto final desde el terminal:

```bash
codex mcp add cx-enterprise --url https://cx-coworker-gateway.adobe.io/mcp
```

Autenticar:

```bash
codex mcp login cx-enterprise
```

Compruebe la configuración:

```bash
codex mcp list
```

También puede agregar el extremo directamente a `~/.codex/config.toml`:

```toml
[mcp_servers.cx-enterprise]
url = "https://cx-coworker-gateway.adobe.io/mcp"
```

### Configuración general de JSON {#mcp-install-individual-json}

Para los clientes que aceptan una configuración de servidor MCP basada en JSON, utilice uno de los siguientes formatos en función de si el cliente admite HTTP remoto nativo o requiere un puente local.

**Vía `mcp-remote` puente**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "command": "npx",
      "args": [
        "mcp-remote",
        "https://cx-coworker-gateway.adobe.io/mcp"
      ]
    }
  }
}
```

**HTTP remoto nativo**

```json
{
  "mcpServers": {
    "cx-enterprise": {
      "url": "https://cx-coworker-gateway.adobe.io/mcp",
      "transport": "http"
    }
  }
}
```

### Otros clientes {#mcp-install-individual-other}

Para otros clientes de escritorio o web con compatibilidad con MCP remoto, agregue Adobe for CX Coworker Gateway como servidor HTTP remoto mediante `https://cx-coworker-gateway.adobe.io/mcp`. Deje vacíos los encabezados opcionales, los campos de token de portador, los campos de ID de cliente y los campos de secreto de cliente, a menos que el cliente requiera un valor de marcador de posición.

## Contexto del producto para llamadas de herramienta {#mcp-connect-params}

El MCP define cada llamada de herramienta a una organización de Adobe activa. Además, los requisitos de contexto dependen del producto:

- **Productos basados en Experience Platform**: Las herramientas de Real-Time CDP, Experience Platform y Journey Optimizer funcionan dentro de una zona protegida de Experience Platform. Configure la zona protegida una vez por sesión; los tres la comparten.
- **Otros productos**: los productos que no se hayan creado en Experience Platform no usan el contexto de zona protegida. Las herramientas Adobe Analytics, Customer Journey Analytics, Workfront, Marketo y Target se resuelven con sus propios recursos de producto; por ejemplo, vistas de datos para Customer Journey Analytics y grupos de informes para Adobe Analytics.

Definir contexto una vez al principio de una sesión: las herramientas de producto individuales no cambian entre organizaciones, zonas protegidas o vistas de datos a mitad de la sesión. Consulte [Herramientas de contexto de sesión](context-tools.md) para ver las herramientas que definen el contexto de la organización, la zona protegida y la vista de datos.

Ejemplo:

> &quot;Use la organización `1234ABCD@AdobeOrg`, la zona protegida `prod` y la vista de datos `My Company — Global` para esta sesión&quot;.

Si no conoce los valores requeridos, pídale a su cliente de MCP que enumere las organizaciones, zonas protegidas o vistas de datos disponibles para sus credenciales de Adobe.