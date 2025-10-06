---
title: Guía del usuario y descripción general de aptitudes del agente de análisis de recorrido
description: Guía completa de la capacidad de análisis de Journey Agent que permite a los usuarios analizar los recorridos de marketing, detectar problemas, descubrir información y optimizar la participación del cliente.
solution: Journey Optimizer
product: journey optimizer
role: Admin,User,Developer,Leader
source-git-commit: 26b579471b591d3c436f4275d07303d297e0fbf8
workflow-type: tm+mt
source-wordcount: '979'
ht-degree: 38%

---


# Agente de análisis de recorrido: información general de aptitudes y guía del usuario

## Información general

Journey Agent permitirá a los usuarios de Journey Optimizer analizar y optimizar los recorridos mediante una interfaz de lenguaje natural. Con Journey Agent, los profesionales pueden identificar y resolver rápidamente conflictos de programación o audiencia, detectar puntos de abandono de usuarios en un recorrido y proporcionar perspectivas o recomendaciones. Permite a los profesionales tomar decisiones basadas en datos, mejorar la participación del cliente y agilizar la orquestación del recorrido.

Obtenga más información y descubra el agente rápidamente en esta [descripción general](https://experienceleague.adobe.com/en/slides/journey-agent-overview).

>[!AVAILABILITY]
>
>Journey Agent está disponible para todos los clientes que tienen acceso a AI Assistant. Sin embargo, necesitará los siguientes permisos para utilizar completamente las funciones de Journey Agent:
>
>**Ver Recorridos**: este permiso le permite ver información sobre el recorrido directamente en el Ayudante de IA.
>
>**Administrar Recorridos**: El permiso Para permite crear nuevos recorridos directamente en el Asistente de IA.
>
>**Ver segmentos**: Este permiso le permite ver información de las audiencias directamente en el Asistente de IA.
>
>**Administrar segmentos**: El permiso Para permite crear nuevas audiencias directamente en el Asistente de IA.

![Muestra para el agente de AJO](./images/ajo-agent/ajo-agent-sample.png)

## Casos de uso

### Principales casos de uso de análisis de Journey Agent

La capacidad de análisis de Journey Agent ofrece una serie de funcionalidades que pueden aprovecharse para optimizar los esfuerzos de marketing:

1. **Análisis del abandono del recorrido**

   - Identifique dónde y por qué abandonan los clientes durante un recorrido.
   - Detecte patrones de comportamiento del cliente que conducen a la desvinculación.
   - Utilice la información para perfeccionar el diseño del recorrido y mejorar la retención.

1. **Análisis de solapamiento de público en los recorridos**

   - Analice el solapamiento de público en múltiples recorridos.
   - Evite la fatiga del público causada por una segmentación excesiva.
   - Optimice la segmentación para garantizar una participación equilibrada.

1. **Análisis del solapamiento de la programación en los recorridos**

   - Detecte conflictos de horarios entre recorridos programados dirigidos al mismo público.
   - Evite el exceso de comunicación y mejore la eficacia de la programación.
   - Maximice el impacto en el público asegurándose de que los viajes se realizan en los momentos óptimos.

1. **Datos operativos**

   - Perspectivas de Recorrido basadas en mensajes - Perspectivas operativas de la superficie sobre recorridos , es decir, &quot;muéstreme todos los recorridos en directo&quot;.

Para cada uno de estos análisis, el agente no solo detecta problemas, sino que también proporciona **recomendaciones procesables para resolverlos**.


## Competencias incluidas y excluidas del ámbito de aplicación

### **Ámbito de aplicación**

Las siguientes funcionalidades son compatibles con el análisis de Journey Agent:

- **Consultas reactivas**: permite a los usuarios hacer preguntas específicas sobre el rendimiento del recorrido, el uso del público y los conflictos de programación.
- **Integración con otros agentes**: colabora con Audience Agent y Data Insights Agent para un análisis más profundo.
- **Estructura de la respuesta del agente**: razonamiento (explicar la lógica), resumen del análisis (resaltar puntos clave), detalles del problema (describir el problema) y recomendación (proponer pasos siguientes).

### **Fuera del ámbito de aplicación**

Actualmente no se admiten las siguientes funcionalidades:

- **Creación automática de recorridos**
- **Detección de anomalías en tiempo real**
- **Los canales se solapan**
- **Análisis de entrada del recorrido**
- **Análisis de problemas técnicos**
- **Análisis de fatiga**

## Muestras de solicitudes/Ejemplos de solicitudes

### Solicitudes habituales para el análisis del recorrido

A continuación, presentamos ejemplos de solicitudes valiosas que los usuarios pueden aprovechar para explorar, monitorizar y solucionar problemas en sus recorridos.

### Preguntas sobre el ciclo de vida del recorrido

- &quot;¿Cuándo se publicó [Nombre de Recorrido]?&quot;
- &quot;¿Cuándo se detuvo [Nombre de Recorrido]?&quot;
- &quot;Enumerar todos los recorridos que están actualmente en modo de prueba&quot;

### Preguntas sobre los recursos del recorrido

- &quot;¿Cuántos recorridos de vida tengo?&quot;
- &quot;Dame una lista de todos los recorridos recurrentes programados y sus tiempos de ejecución esperados&quot;.

### Información sobre el público y el recorrido

- &quot;¿Qué audiencias se utilizan en más de X recorridos?&quot;
- &quot;Enumerar todos los recorridos con la audiencia [audience name]&quot;.

### Análisis de abandonos

- &quot;Quiero analizar las visitas en el orden previsto por nodo para la campaña del 4 de julio de recorrido&quot;.
- &quot;Realizar un análisis de abandonos para la campaña del 4 de julio de recorrido&quot;.
- &quot;¿Qué es la pérdida de perfil en el transcurso de la campaña del 4 de julio de recorrido?&quot;
- &quot;Mostrar dónde caen los usuarios en la campaña del 4 de julio de recorrido&quot;.

### Solicitudes de análisis de conflictos

Utilice estas solicitudes para analizar los posibles conflictos entre recorridos, incluidos los solapamientos de horarios y públicos:

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

### Prácticas recomendadas en materia de solicitudes

Para maximizar la eficacia de análisis de Journey Agent, siga estas prácticas recomendadas:

1. **Sea específico**: utilice preguntas claras y concisas para obtener información específica. Por ejemplo, en lugar de preguntar &quot;¿Cuáles son mis recorridos?&quot;, especifique &quot;Enumerar todos los recorridos creados en el último mes&quot;.
1. **Combine información**: integre la información de Audience Agent y Data Insights Agent para obtener una visión integral del rendimiento del recorrido.
1. **Perfeccionamiento iterativo**: utilice el análisis de abandonos y solapamientos para perfeccionar de forma iterativa el diseño y la programación de los recorridos.

### Prácticas recomendadas para la configuración

- **Defina objetivos claros**: antes de analizar los recorridos, establezca objetivos claros (por ejemplo, mejorar la retención, aumentar las conversiones).
- **Monitorice de forma periódica**: programe revisiones periódicas del rendimiento de los recorridos para identificar las tendencias y las anomalías.
- **Optimice la segmentación**: asegúrese de que la segmentación del público está equilibrada para evitar la fatiga y maximizar la participación.

