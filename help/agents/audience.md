---
title: Audience Agent
description: Aprenda a utilizar Audience Agent para crear audiencias, ver cambios de audiencia, detectar audiencias duplicadas y ver perspectivas de audiencia.
source-git-commit: d91aac948a6fef36949218004dc0481dc8f5cf7f
workflow-type: tm+mt
source-wordcount: '816'
ht-degree: 0%

---


# Audience Agent

>[!AVAILABILITY]
>
>Audience Agent está disponible para todos los clientes que tienen acceso a AI Assistant. Sin embargo, necesitará los siguientes permisos para utilizar completamente las funciones de Audience Agent.
>
>**Ver segmentos**: Este permiso le permite utilizar Audience Agent para ver información de las audiencias directamente en el Asistente de IA.
>>**Administrar segmentos**: El permiso Para permite utilizar Audience Agent para crear nuevas audiencias directamente en el Asistente de IA.

Audience Agent le permite ver información sobre las audiencias, como la detección de cambios significativos en el tamaño de la audiencia, la detección de audiencias duplicadas, la exploración del inventario de audiencias y la recuperación del tamaño de las audiencias.

## Casos de uso admitidos

El asistente de Audience Agent en IA es compatible con los siguientes casos de uso:

- Busque el tamaño de su audiencia y detecte cambios significativos en el tamaño de la audiencia
   - Esto le permite encontrar audiencias que han crecido o disminuido de repente, lo que le permite analizar mejor los posibles cambios del mercado
- Detección de audiencias duplicadas
   - Esto permite reducir las redundancias con las audiencias creadas
- Buscar audiencias en función de atributos completos o parciales llamados
   - Esto permite navegar con mayor facilidad por el inventario de audiencias
- Descubra los campos XDM que puede utilizar para definir una audiencia
   - Esta aptitud le permite identificar con mayor facilidad los campos correctos para su audiencia en función del contexto y la relevancia

Audience Agent no **admite actualmente** las siguientes características:

- Creación de audiencias basada en el conocimiento
   - La creación de audiencias basada en el conocimiento consiste en crear una audiencia basada en los atributos y eventos determinados
   - Además, puede estimar el tamaño potencial de la audiencia antes de la creación de la misma. Esto le permite iterar rápidamente en la audiencia más eficaz antes de que esté lista para activarse
   - La compatibilidad con esta función estará disponible próximamente
- Exploración de audiencias basada en objetivos
   - La exploración de audiencias basada en objetivos permite descubrir conjuntos de datos y perfiles relevantes alineados con un objetivo empresarial mediante la aplicación de modelos de aprendizaje automático como la tendencia a comprar o convertir.

Además, al utilizar Audience Agent, debe tener en cuenta las siguientes restricciones:

- Audience Agent necesita al menos 24 horas para procesar sus datos
   - Por ejemplo, **no puede** tener una consulta que busque datos en las últimas 24 horas. Tendrá que mirar dentro de las últimas 48 horas, como mínimo.
- Audience Agent solo admite audiencias basadas en **people** que se evalúan mediante la segmentación por lotes

## Ejemplos de peticiones de datos

Los siguientes ejemplos muestran mensajes y respuestas de ejemplo para Audience Agent.

### Exploración de audiencia de conversación

Muéstrame campos para compradores adinerados.

+++ Respuesta

![El asistente de IA muestra una tabla con campos relevantes para los compradores adinerados.](./images/audience/affluent-buyers.png)

+++

¿Qué audiencias no se han activado ni utilizado en ninguna campaña en los últimos 30 días?

+++ Respuesta

![El Asistente para IA muestra una tabla con audiencias que no se han activado o utilizado en campañas en los últimos 30 días.](./images/audience/not-activated.png)

+++

Enumerar todas las audiencias que se han asignado a nuevos destinos en los últimos 3 meses.

+++ Respuesta

![El Asistente para IA enumera una audiencia que se ha asignado a un nuevo destino en los últimos tres meses.](./images/audience/new-destination.png)

+++

### Detección de audiencias duplicadas

¿Tengo audiencias con descripciones idénticas o similares?

+++ Respuesta

![El Asistente de IA muestra una tabla que contiene la definición del segmento y los nombres de las audiencias con las mismas definiciones de segmento.](./images/audience/similar-descriptions.png)

+++

Identifique las audiencias que tienen las mismas reglas pero tienen nombres diferentes.

+++ Respuesta

![El Asistente para IA muestra una tabla con los nombres de audiencias que comparten las mismas reglas de audiencia.](./images/audience/same-rules-different-names.png)

+++

Mostrar todas las audiencias que tengan las mismas reglas pero distintos destinos de activación.

+++ Respuesta

![El Asistente de IA muestra que no hay definiciones de segmento duplicadas para diferentes destinos.](./images/audience/same-rules-different-destinations.png)

+++

### Recuperar tamaño de audiencia

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

## Pasos siguientes

Después de leer esta guía, debería comprender mejor Audience Agent y qué funciones admite. Para obtener más información sobre los agentes de Adobe Experience Platform, lea la [descripción general de Agent Orchestrator](./agent-orchestrator.md).
