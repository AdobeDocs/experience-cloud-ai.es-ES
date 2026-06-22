---
title: Validar los datos en el asistente de IA
description: Aprenda a utilizar la validación de datos con tecnología de Agent Orchestrator en el Asistente de IA para realizar validaciones estadísticas y semánticas en los conjuntos de datos.
source-git-commit: 97140003d4a03d83260cf42e026c2e068f517a09
workflow-type: tm+mt
source-wordcount: '1585'
ht-degree: 0%

---

# Validación de los datos en el asistente de IA

Puede utilizar el Asistente de IA para validar la calidad de los datos de los conjuntos de datos de Adobe Experience Platform. Con la tecnología de Agent Orchestrator, la capacidad de validación de datos puede realizar validaciones estadísticas y semánticas de conjuntos de datos, analizar campos de conjuntos de datos, identificar problemas de calidad de datos y devolver resúmenes de lenguajes naturales con perspectivas procesables. Los ingenieros de datos, analistas y administradores de datos pueden utilizar esta capacidad a través del asistente de IA para ejecutar evaluaciones de calidad de datos rápidas sin escribir consultas SQL ni navegar por jerarquías de esquema complejas.

Con la validación de datos con tecnología de Agent Orchestrator en el asistente de IA, puede:

- Rellene los vacíos esenciales tanto en el proceso de incorporación como en los diagnósticos diarios.
- Reduzca el control de calidad manual de sus conjuntos de datos.
- Acelere la obtención de valor para sus clientes.

Lea esta documentación para aprender a validar los datos en el asistente de IA.

>[!NOTE]
>
>El asistente de IA es la interfaz conversacional para este flujo de trabajo. Agent Orchestrator realiza el razonamiento y coordina los pasos de validación entre bastidores.

## Casos de uso

| Ejemplo de uso | Descripción |
| --- | --- |
| Nueva implementación | En estos casos, puede validar la identidad clave y los campos de evento para confirmar los formatos y las tasas nulas tienen un aspecto saludable. |
| Problema de asignación sospechoso | En estos casos, puede validar un campo e inspeccionar los valores principales y los valores no válidos para confirmar que coincide con la semántica deseada. |
| Administración de datos continua | En estos casos, puede ejecutar la validación de conjuntos de datos en conjuntos de datos críticos semanalmente para detectar regresiones de forma temprana. |

## Guía de IU

Utilice **AI Assistant** en Adobe CX Enterprise para validar sus datos. El asistente de IA es la interfaz conversacional, mientras que Agent Orchestrator coordina el flujo de trabajo de validación entre bastidores. Los pasos siguientes siguen las pantallas principales que verá.

### Iniciar validación

![Inicio del asistente de IA con el campo de solicitud que muestra una solicitud de validación del conjunto de datos, un selector de entorno de Experience Platform y un control de envío.](./images/validation/home.png)

En el panel de navegación izquierdo, seleccione **[!UICONTROL Asistente de IA]**. A continuación, utilice el selector de entorno y elija la organización de Experience Platform o zona protegida donde reside el conjunto de datos (por ejemplo, **[!UICONTROL Experience Platform - Prod]**). En el campo de solicitud, escriba una solicitud de validación (por ejemplo, pida validar un conjunto de datos por su nombre). Seleccione **[!UICONTROL Enviar]** para enviar la solicitud.

>[!TIP]
>
>Se recomienda anteponer los nombres de los conjuntos de datos con la palabra &quot;conjunto de datos&quot; al enviar una consulta al Asistente de IA. Por ejemplo, la consulta debe ser &quot;Validar el conjunto de datos Ejemplo de electrónica 1000&quot; en lugar de &quot;Validar muestra de electrónica 1000&quot;.

### Lea el resumen del conjunto de datos y la tabla de campos

![Respuesta del Asistente de IA con Razonamiento completado, un resumen de validación y una tabla de resúmenes de campos que enumera rutas de campo, tipos y valores válidos.](./images/validation/answer.png)

Espere un momento para que Agent Orchestrator complete la ejecución (**Razonamiento completado**). Cuando finalice la ejecución, lea el resumen del nombre del conjunto de datos, cuántos campos se validaron y el tamaño de muestra (normalmente, hasta unas 1000 filas).

Use **[!UICONTROL Resúmenes de campo]** para revisar la ruta, el tipo y los valores válidos de cada campo (incluido el indicador de validez). Además, puede utilizar los iconos de tabla, gráfico o documento de la tarjeta para cambiar el modo en que se muestran los resultados, si están disponibles.

Seleccione **[!UICONTROL Mostrar todos los resultados]** cuando necesite columnas o filas adicionales más allá de la primera vista.

### Trabajo en vista dividida

![Vista dividida con estadísticas y narrativa de validación a la izquierda y una visualización de gráfico expandida de valores válidos a la derecha.](./images/validation/split-screen.png)

En la vista expandida, utilice el diseño dividido: estadísticas detalladas y narrativa por un lado y el gráfico por el otro.

- En el lado narrativo, revise la validez, los valores distintos, las tasas nulas, los valores distintos principales y cualquier mensaje de valor no válido.
- En el lado de la visualización, utilice el gráfico para realizar una lectura rápida de los valores válidos frente a los no válidos en la muestra.

Use **[!UICONTROL Sugerencias relacionadas]** o el campo de solicitud de la parte inferior para validar otro campo, volver a ejecutar el conjunto de datos o continuar la conversación.

### Utilizar una sugerencia relacionada para un seguimiento

![Fichas de sugerencias relacionadas encima del campo de solicitud, con una sugerencia seleccionada para validar un campo específico en el conjunto de datos.](./images/validation/related-suggestion.png)

Después de una respuesta, encuentra **[!UICONTROL sugerencias relacionadas]** debajo de la conversación. Seleccione una sugerencia (por ejemplo, validar un campo específico en el mismo conjunto de datos) para cargarlo en el campo de solicitud. Ajuste el texto si es necesario, confirme el entorno y, a continuación, seleccione **[!UICONTROL Enviar]** para ejecutar el seguimiento.

### Validar en el nivel de campo

![Tarjeta de resultados de validación para un solo campo en la vista de gráfico, que muestra un gráfico de anillo de validez y la acción Mostrar en vista expandida.](./images/validation/single-field.png)

Abra una tarjeta de **[!UICONTROL resultados de validación]** de nivel de campo (por ejemplo, después de validar un solo campo). Use los controles de vista para cambiar a **Gráfico** (u otra vista) cuando desee un resumen visual en lugar de una tabla. Durante este paso, si lo desea, puede seleccionar **[!UICONTROL Propiedades]** para ver más información sobre el campo.

Seleccione **[!UICONTROL Mostrar en vista expandida]** para abrir una vista más grande y detallada de la validación de ese campo.

![Vista ampliada que muestra estadísticas detalladas de validación en el nivel de campo y visualización de gráficos.](./images/validation/expanded-view.png)

A través de la vista expandida, puede ver una lista desglosada de todo el campo, basada en una muestra de hasta 1000 registros para el campo dado. Puede utilizar esta capacidad para recuperar información sobre los valores válidos, distintos y nulos.

## Funcionamiento de la validación

Cuando se inicia una validación en el asistente de IA, Agent Orchestrator analiza una muestra representativa del conjunto de datos, normalmente las ~1000 filas más recientes, en lugar de procesar todo el historial del conjunto de datos. El proceso es estrictamente de solo lectura, lo que garantiza que los datos, los esquemas y las asignaciones permanezcan sin cambios. Los resultados de validación son coherentes independientemente de cómo entren los datos en Experience Platform, ya sea mediante fuentes, flujo, cargas de archivos, preparación de datos u otros métodos de ingesta. Los resultados sirven como comprobaciones indicativas para ayudarle a identificar rápidamente los patrones de calidad de los datos o los problemas potenciales, lo que le permite realizar más acciones (como explorar con el servicio de consultas) si es necesario. Este enfoque basado en Agent Orchestrator permite realizar evaluaciones rápidas sin interrumpir la ingesta de datos ni afectar a las cargas de trabajo de producción.

## Resultados de validación

Para cada campo validado, el Asistente de IA muestra los resultados generados por el flujo de trabajo de validación, incluidos los siguientes:

**Estadísticas básicas**

- Recuento total de filas utilizadas para la muestra
- nullCount (y opcionalmente % null)
- uniqueCount (donde esté disponible)
- Valores únicos máximos (por ejemplo, los 10 principales) y sus frecuencias

**Validación semántica**

- Lista de **valores sospechosos no válidos**
- Para cada valor no válido, una **explicación** (por ejemplo, &quot;no es un formato de correo electrónico válido&quot;, &quot;marca de tiempo fuera del intervalo esperado&quot;)

**Resumen en lenguaje natural**

- Breve resumen narrativo de la calidad del campo
- Acciones siguientes sugeridas, como &quot;revisar asignación para el campo X&quot;, &quot;considerar la posibilidad de eliminar el campo Y debido a una alta tasa de nulos&quot; o &quot;ajustar la validación del formato del correo electrónico&quot;.

| Aspecto | Salida de ejemplo |
| --- | --- |
| Integridad | `nullCount = 9,532 (95.3%)` |
| Singularidad | `uniqueCount = 3` |
| Valores máximos | `"True" (255), "False" (243)` |
| Valores iniciales | `"abc@, reason: "not a valid email address"` |

## Tipos de validación

Existen dos tipos de validación principales que puede realizar con el asistente de IA:

- **Validación de campo**: valide un campo específico en un conjunto de datos.
- **Validación de conjuntos de datos**: Valide hasta cinco (5) campos en un conjunto de datos.

>[!BEGINTABS]

>[!TAB Validación de campo]

Utilice la validación de campos en el Asistente de IA para validar un campo específico en un conjunto de datos determinado. Esta aptitud para la validación proporciona lo siguiente:

- Recuento nulo y recuento de valores únicos.
- Valores únicos máximos y sus frecuencias correspondientes.
- Validación semántica asistida por IA (la capacidad de detectar valores no válidos basados en los metadatos disponibles y los valores reales de los datos).

Ejemplos de solicitudes de validación de campo:

- Valide el campo de correo electrónico en el conjunto de datos Customers_2024.
- Valide el estado del campo para el conjunto de datos customer_events_2024.
- Valide el campo person.address.city para el conjunto de datos de datos de cliente.

>[!TAB Validación de conjunto de datos]

Utilice la validación de conjuntos de datos en el Asistente de IA para validar conjuntos de datos completos, resumiendo la calidad general y los problemas clave. Aunque puede proporcionar estos campos de forma explícita, Agent Orchestrator también puede analizar el conjunto de datos y determinar automáticamente los campos más relevantes. Esta aptitud proporciona el mismo tipo de información que la validación de campos, pero en varios campos de destino. Puede validar hasta cinco campos en un conjunto de datos determinado.

Ejemplos de solicitudes de validación de conjuntos de datos:

- Validar conjunto de datos de datos de cliente 2024.
- Valide los campos de correo electrónico y teléfono para Customers_2024.
- Resuma firstName, lastName, birthDate para los datos del cliente.
- Resumir conjunto de datos 693012a4b8c98b09cea350bc.

>[!ENDTABS]

## Comprobaciones realizadas por la validación de datos

Se realizan los siguientes tipos de validación para cada campo y conjunto de datos:

- **Comprobaciones de integridad**: recuentos y porcentajes nulos/no presentes.
- **Comprobaciones de distribución**: valores únicos principales y sus distribuciones, detección de alta cardinalidad.
- **Comprobaciones semánticas frente a esquema**: utiliza el nombre, el tipo y la descripción del campo XDM para deducir el aspecto &quot;válido&quot; y, a continuación, marca las anomalías.
- **Comprobaciones según el tipo de datos** (donde corresponda):
   - Correo electrónico: formato y verosimilitud de dominio
   - Teléfono: preparación de formato (por ejemplo, E.164)
   - Fechas/marcas de hora: corrección básica del formato (por ejemplo, ISO-8601)
- **Comprobaciones relacionadas con la identidad** (futuras/extendidas): exclusividad de los campos de identidad de los candidatos o claves compuestas.

Estas comprobaciones combinan estadísticas deterministas con una validación semántica asistida por LLM para detectar valores que &quot;tienen un aspecto incorrecto&quot; incluso cuando coinciden técnicamente con el esquema.

## Limitaciones

Antes de validar los datos, es importante tener en cuenta algunas limitaciones clave. Estas restricciones están pensadas para equilibrar el rendimiento con la funcionalidad y ayudarán a establecer expectativas para los tipos de análisis y perspectivas que puede esperar.

- **Solo muestreo**: la validación funciona en una muestra del conjunto de datos (normalmente las últimas ~1000 filas) en lugar de procesar todo el conjunto de datos. Los análisis de conjuntos de datos completos no están disponibles.
- **Límite de recuento de campos**: al validar un conjunto de datos, el agente analiza hasta cinco campos por solicitud. Puede especificar estos campos o permitir que el agente los seleccione automáticamente.
- **Semántica probabilística**: la detección de valores no válidos se basa en parte en la inferencia basada en LLM, que a veces puede omitir errores sutiles o marcar valores límite.
- **Operación de solo lectura**: El agente no realiza ningún cambio en los datos o en su esquema. Proporciona perspectivas y destaca posibles problemas, pero no realiza correcciones automatizadas.

Si sus necesidades de validación son más exhaustivas o requieren la aplicación de una lógica empresarial compleja, considere la posibilidad de complementar los resultados que se muestran en el asistente de IA con herramientas adicionales, como validaciones del servicio de consulta o de la preparación de datos.
