---
title: Adobe Experience Platform Agent Orchestrator
description: Obtenga información sobre Adobe Experience Platform Agent Orchestrator.
source-git-commit: 860b0f2414dc006c23fedcd7b0e29727fc0641d4
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---

# Adobe Experience Platform Agent Orchestrator

Adobe Experience Platform Agent Orchestrator es la nueva capa agéntica de Adobe Experience Platform. Diseñado para aprovechar los abundantes datos y el conocimiento de los clientes de la plataforma, Experience Platform Agent Orchestrator potencia la inteligencia y el razonamiento detrás de los agentes de Adobe Experience Platform expertos creados específicamente, lo que les permite ejecutar tareas complejas de toma de decisiones y resolución de problemas a velocidad y escala, todo ello con supervisión humana. Cuando hace preguntas o solicita ayuda a través del lenguaje natural en una interfaz conversacional como el asistente de IA, Agent Orchestrator llama automáticamente a agentes especializados para que le obtengan las respuestas correctas. Agent Orchestrator recuerda el historial de sus conversaciones, lo que le permite basarse en preguntas anteriores de forma natural sin repetir el contexto, y combina las perspectivas de varios agentes para presentarle respuestas claras y unificadas.

Puede completar flujos de trabajo de extremo a extremo complejos a través de una interfaz conversacional intuitiva sin necesidad de saber qué agentes trabajan entre bastidores. El sistema entiende sus objetivos, crea planes paso a paso y ajusta su enfoque según sea necesario en función de sus comentarios. Puede explorar el panel de razonamiento para ver el proceso de pensamiento paso a paso y comprender mejor cómo se gestionan sus solicitudes. Con Agent Orchestrator, puede abordar flujos de trabajo complejos y optimizar estrategias en todas las aplicaciones de Adobe Experience Cloud.

Lea este documento para obtener más información sobre Agent Orchestrator.

## Componentes de Agent Orchestrator {#components}

Agent Orchestrator consta de varias partes clave, incluida la interfaz conversacional del asistente de IA, un motor de razonamiento para la toma de decisiones y la planificación, agentes especializados de Adobe Experience Platform y una base de conocimiento que proporciona acceso a información relevante.

![La arquitectura de marketing de Agent Orchestrator.](./images/agent-orchestrator/agentic-architecture.png)

### Interfaz conversacional del asistente de IA {#ai-assistant}

El asistente de IA es una experiencia conversacional que puede utilizar para acelerar los flujos de trabajo en aplicaciones de Adobe. Puede utilizar el asistente de IA para comprender mejor el conocimiento del producto, solucionar problemas o buscar a través de la información y encontrar perspectivas operativas. AI Assistant es compatible con Experience Platform, Real-Time Customer Data Platform, Adobe Journey Optimizer y Customer Journey Analytics. Puede utilizar el Asistente de IA para acceder a los agentes de Experience Platform y otras funciones de IA.

Para obtener más información, lea la [guía de la interfaz de usuario del Asistente de IA](../ai-assistant/ai-assistant-ui.md).

### Razonador {#reasoning-engine}

El motor de razonamiento interpreta sus objetivos en función de las indicaciones de su lenguaje natural, comprueba los límites o requisitos y crea planes paso a paso para ayudarle a alcanzar sus objetivos. A diferencia de los sistemas simples de preguntas y respuestas, puede ajustar sus planes a medida que cambian las cosas, y puede volver atrás y probar diferentes enfoques si es necesario. Los planes que crea se muestran en la interfaz conversacional del asistente de IA, para que pueda ver y seguir el proceso, así como intervenir si es necesario.

### Agentes Adobe Experience Platform {#agents}

| Agente | Detalles | Aplicaciones compatibles |
| --- | --- | --- |
| [Audience Agent](audience.md) | Audience Agent le permite ver información sobre las audiencias, como la detección de cambios significativos en el tamaño de las audiencias, la detección de audiencias duplicadas, la exploración del inventario de audiencias y la recuperación del tamaño de estas. | <ul><li>Real-Time CDP</li><li>Adobe Journey Optimizer</li></ul> |
| [Data Insights Agent](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/data-analysis-ai) | Data Insights Agent, al que se puede acceder desde el asistente de IA de Customer Journey Analytics, es un agente de conversación de IA generativo que responde de forma rápida y eficaz a las preguntas sobre sus datos. Crea visualizaciones relevantes en Analysis Workspace utilizando componentes de la vista de datos y utilizando los datos reales. | Customer Journey Analytics |
| Agente de experimentación | El agente de experimentación ayuda a los equipos a aprender más rápido analizando los resultados de los experimentos, prediciendo el impacto y proponiendo nuevos experimentos. Centraliza los experimentos pasados y activos para que pueda aprovechar lo que ya ha aprendido, detectar brechas y priorizar qué probar a continuación. | Adobe Journey Optimizer Experimentation Accelerator |
| [Journey Agent](./ajo-agent-analyze.md) | Journey Agent permite a los usuarios de Adobe Journey Optimizer crear, analizar y optimizar recorridos mediante una interfaz de lenguaje natural. Con Journey Agent, puede crear recorridos rápidamente, detectar y resolver conflictos de programación o audiencia, analizar el rendimiento y los puntos de entrega e identificar recorridos de alto rendimiento para replicarlos en futuras campañas. Le ayuda a tomar decisiones basadas en datos, mejorar la participación de los clientes y optimizar la organización de recorridos. | Adobe Journey Optimizer |
| [Agente de soporte técnico](https://experienceleague.adobe.com/en/docs/experience-platform/ai-assistant/new-features/customer-support) | El agente de asistencia técnica de productos es una capacidad de depuración y solución de problemas de autoservicio que le ayuda a solucionar problemas de funciones y aplicaciones de Adobe Experience Platform sin abandonar sus flujos de trabajo. Los administradores de asistencia pueden crear vales de soporte al cliente con contexto a partir de las interacciones del asistente de IA, y puede consultar las actualizaciones de vales a través del asistente de IA. | <ul><li>Adobe Experience Platform</li><li>Real-Time CDP</li><li>Adobe Journey Optimizer</li><li>Adobe Journey Optimizer B2B edition</li><li>Customer Journey Analytics</li><li>Adobe Experience Manager</li></ul> |

### Base de conocimiento {#knowledge-base}

La base de conocimiento proporciona a los agentes acceso seguro al conocimiento empresarial del cliente a través de fuentes de datos estructuradas y no estructuradas, incluida la documentación de productos de Adobe, los metadatos de clientes sobre objetos comerciales y los datos de análisis.

## Acceso {#access}

Las solicitudes del asistente de IA se autentican mediante los servicios de Identity Management de Adobe. Las autorizaciones las aplican el Control de acceso de Adobe Experience Platform y el Control de acceso de Customer Journey Analytics.

Para obtener acceso a la interfaz conversacional del Asistente de IA y utilizar uno o más agentes de Experience Platform, el administrador de Adobe debe otorgarle los permisos relevantes en la interfaz de usuario de permisos o en Adobe Admin Console:

* **Real-Time CDP** y **Adobe Journey Optimizer**: el administrador debe concederle el permiso **Habilitar el asistente de IA** para que pueda acceder al asistente de IA. El administrador también debe concederle los permisos de **Ver perspectivas operativas** para que pueda hacer preguntas sobre perspectivas operativas en el Asistente de inteligencia artificial. El administrador establece ambos permisos en la interfaz de usuario de permisos.

* **Customer Journey Analytics**: el administrador debe concederle permiso para acceder al Asistente de IA a través de [Control de acceso de Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/technotes/access-control). Esto le permite hacer preguntas sobre el conocimiento del producto y las perspectivas de datos.

>[!NOTE]
>
>Las preguntas de información operativa no están disponibles para Customer Journey Analytics; por lo tanto, no se aplican permisos adicionales.

* **Adobe Experience Manager**: el administrador debe concederle permiso para acceder al Asistente de IA a través de [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html).


