---
title: Guía del usuario y descripción general de aptitudes del agente de análisis de recorrido
description: Guía completa sobre la aptitud para analizar de Journey Agent, que permite a los usuarios analizar los recorridos de marketing, detectar problemas, descubrir perspectivas y optimizar la participación del cliente.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer,Leader
source-git-commit: 56dbe826fc73cbf699f08b12014b2b73d2bab71b
workflow-type: tm+mt
source-wordcount: '937'
ht-degree: 0%

---


# Agente de análisis de recorrido: información general de aptitudes y guía del usuario

## Información general

Journey Agent permitirá a los usuarios de Journey Optimizer analizar y optimizar los recorridos mediante una interfaz de lenguaje natural. Con Journey Agent, los profesionales pueden identificar y resolver rápidamente conflictos de programación o audiencia, detectar puntos de abandono de usuarios en un recorrido y proporcionar perspectivas o recomendaciones. Permite a los profesionales tomar decisiones basadas en datos, mejorar la participación de los clientes y optimizar la organización de recorridos.

>[!AVAILABILITY]
>
>Journey Agent está disponible para todos los clientes que tienen acceso a AI Assistant. Sin embargo, necesitará los siguientes permisos para utilizar completamente las funciones de Journey Agent.
>
>**Ver Recorridos**: este permiso le permite usar Journey Agent para ver información sobre el recorrido directamente en el Asistente de IA.
>>**Administrar Recorridos**: El permiso Para permite utilizar Journey Agent para crear nuevos recorridos directamente en el Asistente de IA.
>>**Ver segmentos**: Este permiso le permite utilizar Journey Agent para ver información de las audiencias directamente en el Asistente de IA.
>>**Administrar segmentos**: El permiso Para permite utilizar Journey Agent para crear nuevas audiencias directamente en el Asistente de IA.

![Muestra para el agente de AJO](./images/ajo-agent/ajo-agent-sample.png)

## Casos de uso

### Casos de uso clave de Journey Agent Analyze

La aptitud de Journey Agent Analyze ofrece una serie de funcionalidades que se pueden aprovechar para optimizar los esfuerzos de marketing:

1. **Análisis de abandonos de Recorrido**

   - Identificar dónde y por qué los clientes abandonan durante un recorrido.
   - Detectar patrones en el comportamiento del cliente que conducen a la desparticipación.
   - Utilice perspectivas para refinar el diseño del recorrido y mejorar la retención.

1. **Análisis de superposición de audiencia de Recorrido**

   - Analizar la superposición de audiencias en varios recorridos.
   - Evite la fatiga de la audiencia causada por la segmentación excesiva.
   - Optimice la segmentación para garantizar una participación equilibrada.

1. **Análisis de superposición de programación de Recorrido**

   - Detectar conflictos de sincronización entre recorridos programados dirigidos a la misma audiencia.
   - Evite la comunicación excesiva y mejore la eficacia de la programación.
   - Maximice el impacto de la audiencia asegurándose de que los recorridos se ejecuten en momentos óptimos.

1. **Datos operativos**

   - Perspectivas de Recorrido basadas en mensajes - Perspectivas operativas de la superficie sobre recorridos , es decir, &quot;muéstreme todos los recorridos en directo&quot;.

Para cada uno de estos análisis, el agente no solo detecta problemas, sino que también proporciona **recomendaciones procesables para resolverlos**.


## Habilidades dentro y fuera de ámbito

### **En ámbito**

Journey Agent Analyze admite las siguientes funciones:

- **Consultas reactivas**: permite a los usuarios hacer preguntas específicas sobre el rendimiento del recorrido, el uso de la audiencia y los conflictos de programación.
- **Integración con otros agentes**: colabora con Audience Agent y Data Insights Agent para realizar un análisis más profundo.
- **Estructura de la respuesta del agente**: razonamiento (explicar la lógica), resumen del análisis (resaltar puntos clave), detalles del problema (describir el problema) y recomendación (proponer pasos siguientes).

### **Fuera de ámbito**

Actualmente no se admiten las siguientes funcionalidades:

- **Creación automatizada de Recorrido**
- **Detección de anomalías en tiempo real**
- **Superposición de canales**
- **análisis de entrada de Recorrido**
- **Análisis de problemas técnicos**
- **Análisis de fatiga**

## Indicadores de ejemplo / Indicadores de ejemplo

### Indicadores comunes para el análisis de Recorrido

Estos son ejemplos de indicaciones útiles que los usuarios pueden aprovechar para explorar, monitorizar y solucionar problemas de sus recorridos.

### Preguntas del ciclo vital de recorrido

- &quot;¿Cuándo se publicó [Nombre de Recorrido]?&quot;
- &quot;¿Cuándo se detuvo [Nombre de Recorrido]?&quot;
- &quot;Enumerar todos los recorridos que están actualmente en modo de prueba&quot;

### Preguntas de recursos de recorrido

- &quot;¿Cuántos recorridos de vida tengo?&quot;
- &quot;Dame una lista de todos los recorridos recurrentes programados y sus tiempos de ejecución esperados&quot;.

### Audience and Recorrido Insights

- &quot;¿Qué audiencias se utilizan en más de X recorridos?&quot;
- &quot;Enumerar todos los recorridos con la audiencia [audience name]&quot;.

### Análisis de abandonos



### Indicadores de análisis de conflicto

Utilice estos indicadores para analizar posibles conflictos entre recorridos, incluida la programación y las superposiciones de audiencias:

- &quot;¿Puede hacer un análisis completo de los conflictos de nuestro recorrido [Nombre del Recorrido] con información de tipo de conflicto (programación/audiencia) con recorridos en vivo/en ejecución?&quot;
- &quot;Realice un análisis de conflictos de programación para el recorrido [Nombre del Recorrido] con información de tipo de conflicto.&quot;
- &quot;Realice un análisis de superposición de audiencias para el recorrido [Nombre del Recorrido] con información del tipo de conflicto.&quot;
- &quot;¿Hay algún conflicto de programación para el recorrido [Nombre de Recorrido]?&quot;
- &quot;Mostrarme conflictos de superposición de audiencias para el recorrido [Nombre del Recorrido]&quot;.
- &quot;Analice todos los conflictos del recorrido [Nombre de Recorrido] con otros recorridos activos.&quot;
- &quot;¿Cuáles son los conflictos actuales para el recorrido [Nombre de Recorrido]?&quot;
- &quot;Compruebe si el recorrido [Nombre de Recorrido] tiene conflictos de audiencia con otros recorridos&quot;.
- &quot;Compruebe si hay conflictos de programación que impliquen el recorrido [Nombre de Recorrido].&quot;
- &quot;Deseo obtener información sobre todos los conflictos de recorrido de [Nombre de Recorrido]&quot;.
- &quot;¿Hay algún recorrido activo que entre en conflicto con [Nombre de Recorrido] por programación o audiencia?&quot;
- &quot;Identifique los tipos de recorrido [Nombre de Recorrido] en comparación con los recorridos en ejecución.&quot;
- &quot;Mostrar audiencias superpuestas para el recorrido [Nombre del Recorrido] y otros recorridos&quot;.
- &quot;Resaltar las superposiciones de programación entre el recorrido [Nombre del Recorrido] y los recorridos activos.&quot;
- &quot;¿El recorrido [Nombre de Recorrido] está en conflicto con algún otro recorrido?&quot;
- &quot;Detecte y enumere los conflictos de [nombre de Recorrido].&quot;
- &quot;Notificar todos los tipos de conflictos para el recorrido [Nombre del Recorrido].&quot;
- &quot;Proporcionarme un desglose de conflictos (programación y audiencia) para [Nombre de Recorrido]&quot;.
- &quot;¿Tiene [Nombre de Recorrido] algún conflicto que pueda afectar al rendimiento?&quot;
- &quot;¿Hay algún conflicto activo que afecte a [Nombre de Recorrido]?&quot;
- &quot;Enumerar recorridos que entran en conflicto con [Nombre de Recorrido] por programación o audiencia&quot;.
- &quot;¿Ha activado el recorrido [Nombre de Recorrido] alguna alerta de conflicto?&quot;
- &quot;Buscar posibles conflictos de audiencia para el recorrido [Nombre de Recorrido]&quot;.
- &quot;Analice el riesgo de conflicto para el recorrido [Nombre de Recorrido].&quot;
- &quot;Proporcionar diagnósticos de conflicto para [Nombre de Recorrido].&quot;


## Prácticas recomendadas

### Prácticas recomendadas de solicitud

Para maximizar la eficacia del análisis de Journey Agent, siga estas prácticas recomendadas:

1. **Sea específico**: Use mensajes claros y concisos para obtener información objetivo. Por ejemplo, en lugar de preguntar &quot;¿Cuáles son mis recorridos?&quot;, especifique &quot;Enumerar todos los recorridos creados en el último mes&quot;.
1. **Combinar perspectivas**: integre perspectivas de Audience Agent y Data Insights Agent para obtener una vista integral del rendimiento del recorrido.
1. **Refinamiento iterativo**: utilice el análisis de visitas en el orden previsto y superposición para refinar iterativamente el diseño y la programación del recorrido.


### Prácticas recomendadas de configuración

- **Definir objetivos claros**: antes de analizar los recorridos, establezca objetivos claros (por ejemplo, mejorar la retención y aumentar las conversiones).
- **Supervisar con regularidad**: Programe revisiones periódicas del rendimiento del recorrido para identificar tendencias y anomalías.
- **Optimizar segmentación**: Asegúrese de que la segmentación de audiencia esté equilibrada para evitar fatiga y maximizar la participación.