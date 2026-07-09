---
title: Validar datos con su compañero de trabajo al actualizar de Adobe Analytics a Customer Journey Analytics
description: Descubra cómo los administradores de Analytics utilizan la habilidad de validación de datos de CX Enterprise Coworker para comparar los datos de Adobe Analytics y Customer Journey Analytics durante la migración.
hold: true
source-git-commit: 850bfef76e3c3e081f9860b9757e5e5128383f76
workflow-type: tm+mt
source-wordcount: '710'
ht-degree: 0%

---

# Validar datos con su compañero de trabajo al actualizar de Adobe Analytics a Customer Journey Analytics

CX Enterprise Coworker incluye una habilidad de validación que le permite validar datos al actualizar de Adobe Analytics a Customer Journey Analytics. La validación de datos se completa en una sola conversación.

Esta aptitud compara automáticamente:

* Cada dimensión, métrica y tendencia individualmente en las implementaciones.

* Todos los grupos de informes de Adobe Analytics con todas las vistas de datos de Customer Journey Analytics.

Después de realizar estas comparaciones, la aptitud genera perspectivas y recomendaciones impulsadas por IA que puede implementar para facilitar la actualización a Customer Journey Analytics.

## Antes de empezar

Para validar los datos como parte de la actualización, necesita lo siguiente:

* El grupo de informes de Adobe Analytics que desea validar.

* La vista de datos de Customer Journey Analytics que contiene los mismos datos.

No necesita saber cómo se ha creado su implementación con antelación. La aptitud detecta automáticamente si los datos se asignan mediante un conector de origen de Analytics o mediante dos implementaciones en paralelo, por lo que no tiene que proporcionar ese contexto usted mismo.

## Iniciar una sesión de validación

1. Inicie sesión en CX Enterprise Coworker.

1. Seleccione [!UICONTROL **Nuevo chat**].

1. En el campo de texto, solicite al agente que valide la migración de Adobe Analytics a Customer Journey Analytics:

   **Mensaje**

   > Ayúdeme a validar la actualización de mi empresa de Adobe Analytics a Customer Journey Analytics.

   La solicitud se dirige a la aptitud de validación de datos, que inicia un proceso de configuración interactivo.

1. El proceso de configuración incluye las preguntas de la tabla siguiente. Para cada pregunta, selecciona una respuesta y luego selecciona [!UICONTROL **Enviar**].

   | Pregunta | Contexto adicional |
   |---------|----------|
   | [!UICONTROL **Seleccione su empresa de Analytics**] | Esta es su compañía de inicio de sesión de Adobe Analytics. |
   | [!UICONTROL **Seleccione su grupo de informes**] <!--In the UI, recommend change to "Select your Adobe Analytics report suite"--> | Este es el grupo de informes de Adobe Analytics que contiene los datos que desea validar con los datos de Customer Journey Analytics. |
   | [!UICONTROL **Seleccione su vista de datos de Customer Journey Analytics**] | Es la vista de datos de Customer Journey Analytics que contiene los mismos datos que el grupo de informes de Adobe Analytics que ha seleccionado. |

1. Revise el resumen de la configuración para confirmar que está validando los datos correctos antes de continuar. El resumen incluye la empresa, el grupo de informes y la vista de datos seleccionados, así como una vista previa de las métricas y dimensiones principales de cada sistema.

1. Continúe con la siguiente sección: [Elija los datos que desea validar](#choose-the-data-to-validate).

## Elija los datos que desea validar

Puede validar métricas o dimensiones individuales, o bien puede validar todas las métricas y dimensiones que se incluyen en el grupo de informes y en la vista de datos.

1. Seleccione entre las siguientes opciones:

   | Opción de validación | Descripción |
   |---------|----------|
   | [!UICONTROL **Comparación de métrica única**] | Comparar la tendencia de una métrica entre Adobe Analytics y Customer Journey Analytics. Utilícelo cuando desee realizar una comprobación rápida de una métrica específica, como vistas de página o visitas. |
   | [!UICONTROL **Comparación de dimensión única**] | Compare el desglose de una sola dimensión entre Adobe Analytics y Customer Journey Analytics. Utilícelo cuando sospeche una diferencia de asignación o clasificación para una dimensión específica. |
   | [!UICONTROL **Auditoría completa de grupos de informes y vistas de datos**] | Compare hasta 20 métricas y dimensiones en una sola ejecución. Utilícelo cuando desee obtener una vista completa del estado general de la migración. |

1. Continúe con la siguiente sección [Revisar el análisis](#review-the-analysis).

## Revisión del análisis

1. Seleccione cada una de las siguientes pestañas para revisar el análisis:

   | Pestaña Revisión de análisis | Descripción |
   |---------|----------|
   | [!UICONTROL **Tasa global de coincidencia**] | Porcentaje que indica en qué medida coinciden los datos del grupo de informes de Adobe Analytics con los de la vista de datos de Customer Journey Analytics. |
   | [!UICONTROL **Información clave**] | Información clave descubierta durante el análisis. |
   | [!UICONTROL **Resumen**] | totales de Adobe Analytics, totales de Customer Journey Analytics, variación total, días que pasan y días críticos. <!--what are these?--> |
   | [!UICONTROL **Tendencia diaria**] | Gráfico que muestra una comparación paralela de los datos de Adobe Analytics y los datos de Customer Journey Analytics. |
   | [!UICONTROL **Detalles diarios**] | <!--what goes here?--> |

1. Desplácese hacia abajo en el análisis para ver los patrones adicionales que se descubrieron durante el análisis, las causas probables de dichos patrones y las acciones sugeridas que puede realizar para resolver cualquier discrepancia en los datos.

1. Compruebe que las acciones sugeridas son válidas y, a continuación, resuelva el problema en Adobe Experience Platform o Adobe Analytics.

1. (Opcional) Continúe con el análisis analizando otra métrica, analizando otra dimensión o ejecutando otro informe de hasta 20 métricas y dimensiones, como se describe en [Elija los datos que desea validar](#choose-the-data-to-validate).

