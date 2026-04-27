---
title: Audience Agent
description: Aprenda a utilizar Audience Agent para crear audiencias, ver cambios de audiencia, detectar audiencias duplicadas y ver perspectivas de audiencia.
TQID: https://experienceleague.adobe.com/574QhqKI0YDoPHD9BFmB6jl-HET3zVom3eD4cJQABSE
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: e1e0219c-f879-479f-8427-888ed2a6e9c2
  - id: eb30f47f-d87a-400f-8f78-63ce7979ff56
source-git-commit: dd7883d8eccab3b0f006d55a850248e1c347d7e7
workflow-type: tm+mt
source-wordcount: 1242
ht-degree: 2%

---

# Audience Agent

>[!AVAILABILITY]
>
>Audience Agent está disponible para todos los clientes que tienen acceso a AI Assistant. Sin embargo, necesitará los siguientes permisos para utilizar completamente las funciones de Audience Agent.
>
>**Ver segmentos**: Este permiso le permite utilizar Audience Agent para ver información de las audiencias directamente en el Asistente de IA.
>
>**Administrar segmentos**: El permiso Para permite usar Audience Agent para crear nuevas audiencias directamente en el Ayudante de IA.

Audience Agent le permite ver información sobre las audiencias, como la detección de cambios significativos en el tamaño de la audiencia, la detección de audiencias duplicadas, la exploración del inventario de audiencias y la recuperación del tamaño de las audiencias.

>[!SLIDE](audience-agent-overview)

## Casos de uso admitidos

El asistente de Audience Agent en IA es compatible con los siguientes casos de uso:

- Explorar la audiencia de forma conversacional
   - Buscar tamaños de audiencia de audiencias existentes
   - Busque audiencias basadas en atributos completos o parciales llamados
   - Detección de audiencias duplicadas
   - Descubra los campos XDM que puede utilizar para definir una audiencia
- Detectar cambios significativos en el tamaño de la audiencia
   - Esto le permite encontrar audiencias que han crecido o disminuido de repente, lo que le permite analizar mejor los posibles cambios del mercado
- Creación de públicos
   - Esta aptitud le permite crear una audiencia basada en los atributos y eventos determinados
   - Además, esta aptitud le permite calcular el tamaño potencial de una audiencia antes de crearla, lo que le permite iterar rápidamente en la audiencia más eficaz antes de que esté lista para activarse

<!--
  - Find your audience size and detect significant changes in audience size
  - This lets you find audiences that have suddenly grown or shrunk, letting you better analyze potential market changes
- Detect duplicate audiences
  - This lets you reduce redundancies with your created audiences
- Find audiences based on full or partial attributes named
  - This lets you more easily navigate through your audience inventory
- Discover XDM fields you can use to define an audience
  - This skill lets you more easily identify the right fields to use in your audience based on context and relevance 
-->

Audience Agent no **admite actualmente** la siguiente característica:

- Exploración de audiencias basada en objetivos
   - La exploración de audiencias basada en objetivos permite descubrir conjuntos de datos y perfiles relevantes alineados con un objetivo empresarial mediante la aplicación de modelos de aprendizaje automático como la tendencia a comprar o convertir.

Además, al utilizar Audience Agent, debe tener en cuenta las siguientes restricciones:

- Audience Agent necesita al menos 24 horas para procesar sus datos
   - Por ejemplo, **no puede** tener una consulta que busque datos en las últimas 24 horas. Tendrá que mirar dentro de las últimas 48 horas, como mínimo.
- Audience Agent solo admite los siguientes tipos de audiencia:
   - **People-based** audiences that are evaluated using batch segmentation
   - **Account-based** audiences for the following use cases:
      - Conversational audience exploration
      - Duplicate audience detection

## Sample prompts

The following examples demonstrate sample prompts and responses for the Audience Agent.

### Conversational audience exploration

Show me fields for affluent buyers.

+++ Respuesta

![The AI Assistant shows a table displaying fields that are relevant to affluent buyers.](./images/audience/affluent-buyers.png)

+++

Which audiences have not been activated or used in any campaign in the last 30 days?

+++ Respuesta

![The AI Assistant shows a table that displays audiences that haven&#39;t been activated or used in campaigns in the last 30 days.](./images/audience/not-activated.png)

+++

List all the audiences that have been mapped to new destinations in the last 3 months.

+++ Respuesta

![The AI Assistant lists the one audience that has been mapped to a new destination in the last 3 months.](./images/audience/new-destination.png)

+++

Which account audience has the largest audience size and what is that size?

+++ Respuesta

![The AI Assistant shows a table that displays the largest account audiences.](./images/audience/largest-account-audience.png)

+++

### Detect duplicate audiences

Do I have any audiences with identical or similar descriptions?

+++ Respuesta

![The AI Assistant displays a table that contains the segment definition and the names of the audiences with the same segment definitions.](./images/audience/similar-descriptions.png)

+++

Identify audiences that have the same rules but have different names.

+++ Respuesta

![The AI Assistant displays a table that contains the names of audiences that share the same audience rules.](./images/audience/same-rules-different-names.png)

+++

Show me all the audiences that have the same rules but different activation destinations.

+++ Respuesta

![The AI Assistant shows that there are no duplicate segment definitions to different destinations.](./images/audience/same-rules-different-destinations.png)

+++

Identify account audiences that have the same rules but have different names.

+++ Respuesta

![The AI Assistant displays a table that contains the names and IDs of account audiences that share the same audience rules.](./images/audience/duplicate-account-audience.png)

+++

### Retrieve audience size

¿Cuál es el tamaño actual de mi audiencia &quot;Miembros Gold-star en California_f153e1&quot;?

+++ Respuesta

![El Asistente para IA indica el tamaño actual de la audiencia sobre la que se preguntó.](./images/audience/current-size.png)

+++

¿Cuál es mi mayor audiencia?

+++ Respuesta

![El Asistente para IA proporciona información sobre la audiencia con la mayor cantidad de perfiles, incluidos el nombre y el ID de audiencia.](./images/audience/largest-audience.png)

+++

### Detectar cambios significativos en el tamaño de la audiencia

¿Qué audiencias han aumentado en más de un 20 % en la última semana?

+++ Respuesta

![El Asistente de IA muestra una tabla con los nombres de todas las audiencias que coinciden con la consulta. También muestra el aumento porcentual, el tamaño actual de la audiencia, así como el tamaño anterior de la audiencia.](./images/audience/increase-past-week.png)

+++

¿Qué audiencias han disminuido en más del 10 % en el último mes?

+++ Respuesta

![El Asistente de IA muestra una tabla con los nombres de todas las audiencias que coinciden con la consulta. También muestra el tamaño de audiencia actual, el tamaño de la audiencia anterior y la fecha del tamaño de audiencia anterior.](./images/audience/decrease-month.png)

+++

¿Cuál es mi audiencia que crece más rápido?

+++ Respuesta

![El Asistente para IA indica el nombre de la audiencia que crece más rápido, así como el tamaño actual y el porcentaje de crecimiento.](./images/audience/fastest-growing.png)

+++

### Crear un público

>[!AVAILABILITY]
>
>Solo puede utilizar la habilidad Crear audiencia si forma parte del programa Explorador de Agent Orchestrator. Para obtener más información, póngase en contacto con el Servicio de atención al cliente de Adobe.

Al crear una audiencia con Audience Agent, el asistente de IA le guiará a través de un plan. Por ejemplo, puede pedir que &quot;se cree una audiencia compuesta por personas que viven en California&quot;. A continuación, AI Assistant enumera el plan que llevará a cabo para crear la audiencia.

+++ Respuesta

![El Asistente para IA muestra el plan para crear una audiencia.](./images/audience/audience-create-plan.png)

+++

Este plan consta de tres pasos:

1. [Identificación de características de audiencia](#identify)
2. [Calcular tamaño de audiencia](#estimate)
3. [Creación y persistencia de una nueva audiencia](#create)

#### Identificación de características de audiencia {#identify}

![Paso 1 del plan, que consiste en identificar las características de la audiencia.](./images/audience/plan-step-1.png){align="center" width="80%"}

Después de aceptar el plan, el asistente de IA recopilará las características de la audiencia en función de su consulta inicial.

+++ Respuesta

![Definición de audiencia basada en la consulta del usuario.](./images/audience/audience-create-definition.png)

Para esta consulta, AI Assistant genera el Profile Query Language (PQL) relevante que buscaría personas que viven en California. En este caso de uso, la consulta de PQL tendría el siguiente aspecto:

```sql
homeAddress.state.equals("California", false)
```

Para obtener más información sobre PQL, lea la [descripción general de PQL](https://experienceleague.adobe.com/en/docs/experience-platform/segmentation/pql/overview).

+++

Si la definición de audiencia del asistente de IA es correcta, puede aprobarla y pasar al siguiente paso.

#### Calcular tamaño de audiencia {#estimate}

![Paso 2 del plan, que es estimar el tamaño de la audiencia potencial.](./images/audience/plan-step-2.png){align="center" width="80%"}

Después de aprobar las características de audiencia identificadas, el asistente de IA calculará el tamaño de la audiencia potencial y los detalles de definición de audiencia.

+++ Respuesta

![Se muestra la estimación de muestra de la audiencia potencial. Se muestran el tamaño estimado y la definición del segmento.](./images/audience/audience-create-estimate.png)

+++

Si el tamaño estimado parece correcto, puede aprobarlo y pasar al siguiente paso.

#### Crear y mantener nueva audiencia {#create}

![Paso 3 del plan, que es terminar de crear la audiencia.](./images/audience/plan-step-3.png){align="center" width="80%"}

Por último, si las características y el tamaño de la audiencia parecen correctos, puede aprobar o rechazar la creación de la audiencia.

+++ Respuesta

En primer lugar, puede revisar la audiencia propuesta a través de la cuadrícula de datos proporcionada.

![Se muestra la pantalla de revisión.](./images/audience/audience-create-review.png)

Si la audiencia tiene el aspecto correcto, puede aceptar la propuesta seleccionando **[!UICONTROL Crear]** para finalizar la creación de la audiencia.

![Se muestra la propuesta completa para la audiencia.](./images/audience/audience-create-proposal.png)

+++

Se crea la audiencia.

![Se aceptó la propuesta de audiencia y se creó la audiencia.](./images/audience/audience-finish-create.png){align="center" width="80%"}

## Próximos pasos

Después de leer esta guía, debería comprender mejor Audience Agent y qué funciones admite. Para obtener más información sobre los agentes de Adobe Experience Platform, lea la [descripción general de Agent Orchestrator](./agent-orchestrator.md).

