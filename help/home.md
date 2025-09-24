---
title: IA en aplicaciones de Experience Cloud
description: Descubra cómo las aplicaciones de Experience Cloud utilizan IA generativa (GenAI), AI Assistant y IA auténtica.
source-git-commit: 860b0f2414dc006c23fedcd7b0e29727fc0641d4
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 0%

---

# IA en Experience Cloud

Le damos la bienvenida a la guía completa para las funcionalidades de IA en todas las aplicaciones de Adobe Experience Cloud. Esta documentación explica cómo los agentes de IA generativa, el asistente de IA y Adobe se integran en los flujos de trabajo de Experience Cloud para acelerar la productividad y mejorar la toma de decisiones.

## Qué se incluye en esta guía

### Asistente de IA

[Asistente de IA](./ai-assistant/ai-assistant-ui.md) es una herramienta inteligente de IA generativa y conversacional que aumentará la productividad y redefinirá el trabajo en aplicaciones basadas en Adobe Experience Platform. Los usuarios pueden obtener conocimientos del producto, solucionar problemas y encontrar perspectivas operativas a través de mensajes en lenguaje natural. También puede utilizar el Asistente de IA para acceder a los agentes de Adobe Experience Platform y otras funcionalidades de IA.

**Características principales:**

- **Interfaz de conversación**: opciones de vista de carril y pantalla completa para diferentes preferencias de flujo de trabajo
- **Indicadores de detección**: mensajes preconfigurados organizados por categoría (Aprender, Analizar, Optimizar)
- **Configuración de contexto**: configure la aplicación, la zona protegida y la vista de datos para las respuestas de destino
- **Visualización de datos**: Gráficos y diagramas interactivos para obtener datos
- **Verificación de respuestas**: citas de Source, explicaciones de razonamiento y mecanismos de comentarios

### Agent Orchestrator

[Adobe Experience Platform Agent Orchestrator](./agents/agent-orchestrator.md) es la nueva capa agéntica de Adobe Experience Platform. Diseñado para aprovechar los abundantes datos y el conocimiento de los clientes de la plataforma, Experience Platform Agent Orchestrator potencia la inteligencia y el razonamiento detrás de los agentes de Adobe Experience Platform expertos creados específicamente, lo que les permite ejecutar tareas complejas de toma de decisiones y resolución de problemas a velocidad y escala, todo ello con supervisión humana. Cuando hace preguntas o solicita ayuda a través del lenguaje natural en una interfaz conversacional como el asistente de IA, Agent Orchestrator llama automáticamente a agentes especializados para que le obtengan las respuestas correctas. Agent Orchestrator recuerda el historial de sus conversaciones, lo que le permite basarse en preguntas anteriores de forma natural sin repetir el contexto, y combina las perspectivas de varios agentes para presentarle respuestas claras y unificadas.

**Componentes principales:**

- **Motor de razonamiento**: crea planes paso a paso y ajusta los enfoques según sea necesario
- **Agentes especializados**: agentes creados específicamente para tareas y dominios específicos
- **Base de conocimiento**: acceso seguro a inteligencia empresarial y documentación

### Agentes especializados

#### Audience Agent

Proporciona información sobre las audiencias, lo que incluye:

- Detección de cambios significativos en el tamaño de audiencia
- Identificación de audiencias duplicadas
- Exploración del inventario de audiencias
- Recuperando tamaños de audiencia

#### Data Insights Agent

Disponible en Customer Journey Analytics, este agente:

- Responde preguntas sobre sus datos con lenguaje natural
- Crea visualizaciones relevantes en Analysis Workspace
- Utiliza componentes de la vista de datos y datos reales

#### Journey Agent

Permite a los usuarios de Journey Optimizer:

- Cree, analice y optimice recorridos con lenguaje natural
- Detectar y resolver conflictos de programación o audiencia
- Analizar el rendimiento y los puntos de entrega
- Identificar los recorridos de mayor rendimiento para la replicación

#### Agente de soporte del producto

Ofrece depuración de autoservicio y solución de problemas:

- Solución de problemas de funciones de Adobe Experience Platform sin abandonar flujos de trabajo
- Creación de vales de soporte con contexto a partir de interacciones del asistente de IA
- Comprobación de actualizaciones de tickets mediante el asistente de IA

## Primeros pasos

### Requisitos de acceso

Para utilizar el asistente de IA y agentes de Experience Platform, el administrador de Adobe debe configurar los permisos adecuados:

- **Real-Time CDP y Adobe Journey Optimizer**: se necesita el permiso &quot;Habilitar el asistente de IA&quot; y el permiso &quot;Ver perspectivas operativas&quot; para preguntas operativas
- **Customer Journey Analytics**: acceso a través del control de acceso de Customer Journey Analytics para obtener información sobre el producto y preguntas sobre datos
- **Adobe Experience Manager**: acceso a través de Adobe Admin Console

### Privacidad y seguridad

El asistente de IA está diseñado con privacidad, seguridad y gobernanza en la vanguardia:

- No se utilizan datos personales para la formación
- Se respetan todas las políticas de control de acceso existentes
- Preparado para la HIPAA cuando se utiliza con Adobe Experience Platform Healthcare Shield
- Política de retención de 30 días para registros de interacción
- Aislamiento de datos específico de una zona protegida

## Prácticas recomendadas

- **Sea específico** en sus indicaciones para obtener información de destino
- **Verificar respuestas** usando citas de origen y explicaciones de razonamiento
- **Use la configuración de contexto** para garantizar que las fuentes de datos sean relevantes
- **Proporcione comentarios** para ayudar a mejorar el rendimiento del Asistente de IA
- **Combine datos** de varios agentes para realizar un análisis exhaustivo

## Consideraciones legales

- Actualmente, el asistente de IA solo admite inglés
- Compruebe siempre las respuestas, ya que los modelos de idioma pueden cometer errores
- Revisar los pasos de razonamiento y las explicaciones proporcionadas
- Envíe comentarios por cualquier problema o inexactitud

Esta guía proporciona todo lo necesario para utilizar de forma eficaz las capacidades de IA en todas las aplicaciones de Experience Cloud, desde interacciones básicas hasta orquestación de agentes avanzada y flujos de trabajo especializados.

