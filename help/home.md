---
title: IA en aplicaciones de Experience Cloud
description: Descubra cómo las aplicaciones de Experience Cloud utilizan la IA generativa (GenAI), el asistente de IA y la IA agéntica.
TQID: https://experienceleague.adobe.com/heALjEZbowNaygG24oOM2HSlHa9oYVI5ViUNZDr19Ds
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 846
ht-degree: 17%

---

# IA en Experience Cloud

Le damos la bienvenida a la guía completa para las funcionalidades de IA en todas las aplicaciones de Adobe Experience Cloud. Esta documentación explica cómo los agentes de IA generativa, el asistente de IA y Adobe se integran en los flujos de trabajo de Experience Cloud para acelerar la productividad y mejorar la toma de decisiones.

## Qué se incluye en esta guía

### Asistente de IA

[Asistente de IA](./ai-assistant/ai-assistant-ui.md) es una herramienta inteligente de IA generativa y conversacional que aumentará la productividad y redefinirá el trabajo en aplicaciones basadas en Adobe Experience Platform. Los usuarios pueden obtener conocimientos del producto, solucionar problemas y encontrar perspectivas operativas a través de mensajes en lenguaje natural. También puede utilizar el Asistente de IA para acceder a los agentes de Adobe Experience Platform y otras funcionalidades de IA.

**Características principales:**

- **Interfaz de conversación**: puede elegir entre una interfaz de pantalla completa y una de vista de carril para adaptarla a sus preferencias de flujo de trabajo.
- **Indicadores de detección**: el Asistente para IA proporciona mensajes preconfigurados organizados por categorías como Aprender, Analizar y Optimizar.
- **Configuración de contexto**: puede configurar la aplicación, la zona protegida y la vista de datos para recibir respuestas adaptadas a sus necesidades.
- **Visualización de datos**: La herramienta ofrece gráficos y diagramas interactivos, lo que le permite obtener información de sus datos.
- **Verificación de respuestas**: todas las respuestas incluyen citas de la fuente, explicaciones del razonamiento de IA y mecanismos para proporcionar comentarios.


### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md) es la nueva capa agéntica de Adobe Experience Platform. Diseñado para aprovechar los abundantes datos y el conocimiento de los clientes de la plataforma, Experience Platform Agent Orchestrator potencia la inteligencia y el razonamiento que hay detrás de los agentes expertos de Adobe Experience Platform creados específicamente, lo que les permite ejecutar tareas complejas de toma de decisiones y resolución de problemas con rapidez y a gran escala, todo ello con supervisión humana. Cuando formula preguntas o solicita ayuda a través del lenguaje natural en una interfaz conversacional como el Asistente de IA, Agent Orchestrator llama automáticamente a agentes especializados para que le den las respuestas correctas. Agent Orchestrator recuerda el historial de sus conversaciones, lo que le permite basarse en preguntas anteriores de forma natural sin repetir el contexto, y combina la información de varios agentes para presentarle respuestas claras y unificadas.

**Componentes principales:**

- **Motor de razonamiento**: crea planes paso a paso y ajusta los enfoques según sea necesario
- **Agentes especializados**: agentes creados específicamente para tareas y dominios específicos
- **Base de conocimiento**: acceso seguro a inteligencia empresarial y documentación

### Agentes especializados

#### Audience Agent

Audience Agent proporciona perspectivas sobre audiencias que incluyen:

- Detectando cambios significativos en el tamaño de la audiencia.
- Identificación de audiencias duplicadas.
- Explorando el inventario de audiencias.
- Recuperando tamaños de audiencia.

Lea la [documentación de Audience Agent](./agents/audience.md) para obtener más información.

#### Data Insights Agent

Data Insights Agent, disponible en Customer Journey Analytics:

- Responde preguntas sobre sus datos con lenguaje natural.
- Genera visualizaciones relevantes en Analysis Workspace.
- Utiliza componentes de la vista de datos y datos reales.

#### Agente de análisis de recorrido

El agente de análisis de Recorrido permite a los usuarios de Adobe Journey Optimizer lo siguiente:

- Analice y optimice los recorridos con lenguaje natural.
- Detectar y resolver conflictos de programación o audiencia.
- Analice el rendimiento y los puntos de entrega.

Lea la [documentación de Journey Agent](./agents/ajo-agent.md) para obtener más información.

#### Agente de soporte del producto

Utilice el Agente de soporte del producto para la depuración de autoservicio y la resolución de problemas:

- Solucionar problemas de funciones de Adobe Experience Platform sin abandonar los flujos de trabajo.
- Cree vales de soporte con contexto a partir de las interacciones del asistente de IA.
- Consulte las actualizaciones de tickets a través del asistente de IA.

Lea la [Documentación del agente de soporte técnico](./agents/product-support.md) para obtener más información.

<!--
#### Adobe Marketing Agent for [!DNL Microsoft 365 Copilot]

Use the Adobe Marketing Agent for [!DNL Microsoft 365 Copilot] to retrieve marketing insights from Experience Platform in [!DNL Microsoft 365] apps like [!DNL Teams], [!DNL Word], [!DNL Powerpoint], and [!DNL Excel]. With this agent, you can:

- Make faster, data-driven marketing decisions.
- Reduce time spent switching between tools.
- Simplify access to audience and journey insights across teams.

Read the [Adobe Marketing Agent documentation](./agents/ama-ms.md) for more information.
-->

## Introducción

### Requisitos de acceso

Para utilizar el asistente de IA y agentes de Experience Platform, el administrador de Adobe debe configurar los permisos adecuados:

- Para utilizar el asistente de IA en Real-Time CDP y Adobe Journey Optimizer, necesita el permiso &quot;Habilitar el asistente de IA&quot;, así como el permiso &quot;Ver perspectivas operativas&quot; para acceder a preguntas operativas.
- El acceso a AI Assistant en Customer Journey Analytics se administra mediante el control de acceso de Customer Journey Analytics, que le permite hacer preguntas sobre el conocimiento del producto y la información de los datos.
- Para Adobe Experience Manager, puede acceder al asistente de IA a través de los permisos establecidos en Adobe Admin Console.

### Privacidad y seguridad

El asistente de IA está diseñado con privacidad, seguridad y gobernanza en la vanguardia:

- No se utilizan datos personales para la formación.
- Se respetan todas las políticas de control de acceso existentes.
- Preparado para la HIPAA cuando se utiliza con Adobe Experience Platform Healthcare Shield.
- Política de retención de 30 días para registros de interacción.
- Aislamiento de datos específico de una zona protegida.

## Prácticas recomendadas

Para sacar el máximo partido a la experiencia del asistente de IA, siga estas prácticas recomendadas:

- **Sea específico** en sus indicaciones para obtener información relevante y dirigida del Asistente de IA.
- **Verifique las respuestas** revisando las citas de origen y las explicaciones de razonamiento proporcionadas por el Asistente de inteligencia artificial.
- **Use la configuración de contexto** para asegurarse de que se usan las fuentes de datos más relevantes para sus preguntas.
- **Proporcione comentarios** para ayudar a mejorar el rendimiento y la precisión del Ayudante de IA a lo largo del tiempo.
- **Combine datos** de varios agentes para lograr un análisis más completo y completo.

## Consideraciones legales

Al utilizar el asistente de IA, es importante tener en cuenta las consideraciones legales y prácticas clave. Actualmente, el asistente de IA solo admite respuestas en inglés. Tenga siempre cuidado de verificar la información proporcionada, ya que los modelos de idioma pueden cometer errores ocasionalmente. Utilice los pasos y explicaciones de razonamiento que se incluyen en las respuestas para comprender mejor las respuestas que recibe. Si encuentra algún problema o imprecisión, envíe sus comentarios para ayudar a mejorar el asistente de IA a lo largo del tiempo.
