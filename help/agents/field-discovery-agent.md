---
title: Agente de detección de campos
description: Busque, evalúe y seleccione campos XDM en Adobe Experience Platform utilizando el lenguaje natural en el asistente de IA, con resultados de clasificación, valores de muestra y contexto de uso para flujos de trabajo de segmentación, consulta y datos.
keywords: detección de campos, XDM, asistente de IA, agentes de Experience Platform, vinculación de entidades, recomendaciones de campos, creación de audiencias, segmentación
solution: Experience Platform
role: User, Admin, Developer
source-git-commit: b4d8c83cca73a19e1fe229c8cec03caee16bcd8c
workflow-type: tm+mt
source-wordcount: '3525'
ht-degree: 0%

---

# Agente de detección de campos

Al crear audiencias o incorporar datos en Adobe Experience Platform, la identificación del campo XDM correcto para un concepto empresarial suele requerir la exploración manual de esquemas o saber de antemano exactamente cómo se denomina un campo. Los distintos campos pueden representar el mismo concepto con nombres diferentes (por ejemplo, estado, región y ubicación) y elegir el incorrecto introduce errores en los flujos de trabajo descendentes.

El agente de detección de campos es un agente con tecnología de IA en Adobe Experience Platform que le ayuda a encontrar, evaluar y seleccionar campos XDM mediante consultas en lenguaje natural en el asistente de IA. Describe lo que busca en lenguaje sencillo: un concepto empresarial, un objetivo de flujo de trabajo o un nombre de campo específico, y el agente devuelve sugerencias de campos clasificados con contexto de soporte.

El agente de detección de campos se invoca automáticamente en segundo plano en el asistente de IA cuando otros agentes de Experience Platform necesitan resolver referencias de campos o entidades. En estos casos, funciona en segundo plano para mejorar la precisión del agente con el que está trabajando. Cuando necesite la detección de campos para su propio trabajo, escriba un mensaje explícito de búsqueda de campos en el Asistente de IA. El agente de detección de campos solo muestra información de campo. No modifica esquemas, conjuntos de datos ni audiencias y respeta los controles de acceso y el contexto de la zona protegida existentes.

## Cuándo usar esto {#when-to-use-this}

Utilice Field Discovery Agent explícitamente en el asistente de IA cuando necesite sugerencias de campos clasificados, valores de muestra y contexto de uso para una asignación, segmentación o consulta. Se utiliza implícitamente cuando otro agente de Experience Platform lo invoca en segundo plano para resolver referencias de campos o entidades. En estos casos, permanecerá en el flujo de trabajo de ese agente y no emitirá un mensaje de búsqueda de campos independiente.

## Requisitos previos {#prerequisites}

Para utilizar el agente de detección de campos, asegúrese de que dispone de lo siguiente:

- Acceso a Adobe Experience Platform y al asistente de IA
- La organización y zona protegida correctas
- Acceso a los esquemas y conjuntos de datos que desea consultar

La familiaridad básica con los esquemas XDM y cómo se utilizan los campos en la segmentación o en los flujos de trabajo de datos puede ayudarle a interpretar los resultados de forma más eficaz. Para obtener más información, consulte la [descripción general de XDM](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/home) y la [documentación del Editor de esquemas](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/tutorials/create-schema-ui).

Para obtener instrucciones sobre cómo habilitar el acceso al Asistente de IA y conceder los permisos necesarios, consulte la [guía de acceso de Agent Orchestrator](./agent-orchestrator.md#access).

## Funciones del agente de detección de campos {#field-discovery-agent-functions}

El agente de detección de campos procesa la consulta y devuelve uno de los tres tipos de salida según la intención. Estas funciones reflejan cómo el agente interpreta la consulta; no las selecciona. El agente determina automáticamente el tipo de respuesta adecuado en función de lo que describa.

| Función | Descripción | Resultado esperado |
| --- | --- | --- |
| **Identificación** | Identifica campos XDM que coinciden semánticamente con un concepto o atributo empresarial que describa en lenguaje natural. | Una lista clasificada de campos candidatos con etiquetas de relevancia, rutas de campo y vínculos de contextos de uso. |
| **Recomendación** | Recomienda campos XDM basados en un objetivo de flujo de trabajo o en un caso de uso que describa, como crear un segmento de audiencia o modelar un atributo de comportamiento. | Una lista priorizada de campos relevantes para el objetivo declarado, con contexto de relevancia para cada uno. |
| **Enriquecimiento** | Devuelve el contexto detallado de un campo específico, incluidos los valores de ejemplo, la ubicación del esquema y dónde se utiliza el campo en los conjuntos de datos, las audiencias y los destinos. | Detalles del campo, incluidos los valores de muestra, la ruta de esquema, los conjuntos de datos asociados y el uso de audiencia o destino. |

## Cómo funciona el agente de detección de campos {#how-field-discovery-agent-works}

En un nivel superior, el agente interpreta su intención, busca los datos disponibles y clasifica los resultados por relevancia. La forma en que expresa la consulta afecta directamente a cada fase, lo que a su vez afecta a la calidad de los resultados.

Al enviar una consulta en el Asistente de IA, el agente de detección de campos procesa la solicitud en tres fases:

| Prueba | Descripción |
|------|-------------|
| **Interpretación por intención** | El agente lee los datos introducidos en su lenguaje natural e identifica el concepto u objetivo subyacente. Por ejemplo, una consulta sobre &quot;personas en California&quot; se interpreta como una solicitud de atributo geográfico, no como una coincidencia de cadena literal. El agente asigna el fraseo a conceptos semánticamente equivalentes que pueden aparecer con nombres diferentes en los esquemas. |
| **Ámbito de búsqueda** | El agente busca en los esquemas XDM, conjuntos de datos y metadatos de campo disponibles en la organización IMS y zona protegida actuales. Considera los nombres de los campos, los nombres para mostrar, las descripciones y las asociaciones de uso para encontrar candidatos que se alineen con la intención. |
| **Clasificación** | El agente clasifica los resultados por relevancia semántica (la proximidad de un campo a la intención declarada), complementada por señales como la integridad de los metadatos y el uso del campo en el ecosistema de datos. Los campos con nombres descriptivos, metadatos rellenados y uso confirmado en conjuntos de datos activos se clasifican por encima de los campos que solo existen en una definición de esquema. El agente no expone los pesos específicos asignados a señales individuales. |

## Comprender los resultados {#understand-your-results}

Field Discovery Agent devuelve un conjunto de resultados estructurado para cada consulta. Comprender los componentes de un resultado le ayuda a evaluar los campos candidatos y actuar en consecuencia con confianza, sin pruebas ni errores adicionales.

Trate un campo como listo para usarlo cuando su etiqueta **[!UICONTROL Relevancia]** sea **[!UICONTROL Muy relevante]**, sus valores de muestra coincidan con los datos que espera (cuando estén disponibles) y sus **[!UICONTROL Contextos de uso]** se alineen con la forma en que planea usarlo. Si los resultados son solo **[!UICONTROL Relevantes moderadamente]** o **[!UICONTROL Relevantes]**, los valores de muestra no coinciden con las expectativas o el contexto de uso es limitado, refina la consulta y revisa un nuevo conjunto de resultados antes de continuar.

### Etiquetas de relevancia

El agente de detección de campos asigna una etiqueta de relevancia en la columna **[!UICONTROL Relevancia]** del panel **[!UICONTROL Campos identificados]** para cada resultado de campo, lo que indica la proximidad del campo a la consulta.

- **[!UICONTROL Muy relevante]**: el campo coincide totalmente con el concepto indicado en función de su nombre, metadatos y señales de uso. Confirme la ruta de campo y revise sus valores de muestra para comprobar que contiene los datos esperados.
- **[!UICONTROL Moderadamente relevante]**: el campo tiene superposición semántica parcial con la consulta, pero puede diferir en ámbito, tipo de datos o especificidad. Revise los valores de muestra y el contexto de uso para determinar si satisfacen sus necesidades antes de seleccionarlos.
- **[!UICONTROL Relevante]**: el campo coincide parcialmente con la consulta. Puede compartir superposición semántica, pero difiere en ámbito, especificidad o tipo de datos. Revise los valores de muestra y el contexto de uso antes de decidir si desea utilizarlo.

Si todos los resultados están etiquetados como **[!UICONTROL Moderadamente relevante]** o **[!UICONTROL Relevante]** en lugar de **[!UICONTROL Altamente relevante]**, es posible que la consulta sea demasiado amplia o que utilice una terminología que no coincida con los metadatos del esquema. Refine la solicitud con términos de dominio o idioma más específicos que reflejen el nombre de los campos.

### Valores de muestra

Junto a cada sugerencia de campo, el agente de detección de campos muestra valores de muestra extraídos de los datos del campo en la zona protegida. Los valores de muestra ayudan a comprobar que un campo contiene el tipo de datos esperado antes de seleccionarlo.

>[!IMPORTANT]
>
>Los valores de muestra pueden contener PII. No los comparta fuera de flujos de trabajo internos seguros.

Los valores de muestra solo son visibles para los campos dentro de los permisos de acceso del conjunto de datos. Para obtener información sobre el control de datos y las restricciones de uso en Experience Platform, consulte la [Información general sobre el control de datos](https://experienceleague.adobe.com/es/docs/experience-platform/data-governance/home).

Si no aparecen valores de muestra para un campo, es posible que el campo esté vacío en la zona protegida actual o que los permisos no incluyan el acceso a su conjunto de datos subyacente. Los campos con alta cardinalidad (como los campos de identificador o UUID) también pueden no devolver valores de muestra representativos. Los valores de muestra se agregan y se basan en la frecuencia y no se pueden rastrear en perfiles individuales.

### Contexto de uso

Cada resultado de campo incluye un contexto de uso que muestra dónde aparece el campo en el ecosistema de datos:

**Conjunto de datos de Audience → → Esquema de → de destino**

Un campo que se utiliza en una audiencia publicada, aparece en un conjunto de datos activo, está asignado a un destino activo y se define en un esquema que ha demostrado un uso real en su entorno. Esto distingue los campos en los que se confía activamente de los campos que existen solo en una definición de esquema, pero que no se han utilizado en la práctica. Utilice esta señal junto con la etiqueta de relevancia y los valores de muestra para realizar una selección de campo más informada.

### Resultados en el asistente de IA

El agente de detección de campos devuelve resultados en un panel de **[!UICONTROL Campos identificados]** dentro de la respuesta del asistente de IA. El panel muestra una tabla con tres columnas:

- **[!UICONTROL Nombre de campo]**: la ruta XDM del campo candidato.
- **[!UICONTROL Relevancia]**: la etiqueta de relevancia asignada al campo (**[!UICONTROL Muy relevante]**, **[!UICONTROL Moderadamente relevante]** o **[!UICONTROL Relevante]**)
- **[!UICONTROL Contextos de uso]**: vínculos que muestran dónde aparece el campo en el ecosistema de datos. Seleccione **[!UICONTROL audience]**, **[!UICONTROL dataset]**, **[!UICONTROL destination]** o **[!UICONTROL schema]** para abrir un panel lateral que muestre dónde se utiliza el campo.

![El panel Campos identificados en el Ayudante de IA muestra filas de campos candidatos con vínculos Etiquetas de relevancia y Contextos de uso.](./images/field-discovery/fields-identified-panel-in-chat.png)

Aparece una sección **[!UICONTROL Resultados explicados]** debajo de la tabla **[!UICONTROL Campos identificados]** y proporciona contexto de nivel de campo adicional, incluidas explicaciones y detalles de compatibilidad para cada resultado. Para obtener instrucciones sobre cómo navegar por la interfaz del Asistente de IA, consulte la [guía de la interfaz de usuario del Asistente de IA](../ai-assistant/ai-assistant-ui.md).

## Usar agente de detección de campos {#use-field-discovery-agent}

Interactúa con el agente de detección de campos a través del asistente de IA mediante lenguaje natural. El agente requiere una declaración de intención clara: una consulta vaga o excesivamente breve produce resultados de baja calidad o puede que no invoque el agente de detección de campos en absoluto.

Para la detección explícita de campos, siga este flujo de trabajo: identifique el atributo o el problema de asignación, envíe una consulta de búsqueda de campos, revise los resultados de clasificación y el contexto de uso en el panel **[!UICONTROL Campos identificados]**, seleccione la ruta de **[!UICONTROL Nombre de campo]** que se ajuste a sus intenciones y aplique esa ruta XDM en el Generador de segmentos, el Servicio de consulta u otro flujo de trabajo.

Para utilizar el agente de detección de campos:

1. Vaya a **[!UICONTROL Asistente de IA]** desde cualquier aplicación de Experience Platform habilitada. Se muestra el área de trabajo **[!UICONTROL AI Assistant]**.
2. Especifique la intención explícitamente en el campo de entrada. Describa el concepto, el objetivo o la característica de campo que está buscando. Por ejemplo: *&quot;Encuentre campos relacionados con el estado de exclusión de correo electrónico del cliente.&quot;*
3. Revise los resultados de clasificación en el panel **[!UICONTROL Campos identificados]**. Cada fila incluye una etiqueta de relevancia y una ruta de campo XDM en la columna **[!UICONTROL Nombre de campo]**.
4. Seleccione **[!UICONTROL audience]**, **[!UICONTROL dataset]**, **[!UICONTROL destination]** o **[!UICONTROL schema]** en la columna **[!UICONTROL Contextos de uso]** para abrir un panel lateral que muestre dónde se utiliza el campo. Para obtener contexto de nivel de campo adicional, consulte la sección **[!UICONTROL Resultados explicados]** debajo de la tabla de resultados.

   ![Panel lateral del Asistente de IA que muestra los contextos de uso de un campo seleccionado, incluidas las asociaciones de audiencia, conjunto de datos, destino y esquema.](./images/field-discovery/fields-identified-panel-expanded.png)

5. Utilice la ruta **[!UICONTROL Nombre de campo]** en herramientas de flujo descendente como Generador de segmentos, Servicio de consulta o flujos de trabajo de ingesta de datos, según el caso de uso. El agente de detección de campos proporciona la referencia de campo, pero no la inserta en otras herramientas.

Si es necesario, seleccione el menú desplegable **[!UICONTROL Razonamiento completado]** sobre la respuesta para confirmar que el agente de detección de campos gestionó su solicitud. La lista desplegable muestra detalles del razonamiento que indican a qué agente se llamó.

>[!NOTE]
>
>Si el panel de razonamiento no indica un agente de detección de campos, es posible que la consulta no haya incluido una intención clara de detección de campos. Restablezca la consulta con un lenguaje explícito de búsqueda de campos y vuelva a enviarla. Consulte [Solución de problemas](#troubleshooting) para ver problemas comunes de invocación.

Para obtener instrucciones sobre la interfaz del Asistente de IA, consulte la [guía de la interfaz de usuario del Asistente de IA](../ai-assistant/ai-assistant-ui.md).

## Casos de uso admitidos {#supported-use-cases}

Las secciones siguientes describen cada una de las tres funciones del agente de detección de campos con escenarios representativos y mensajes de ejemplo. Los resultados incluyen etiquetas de relevancia y contexto de uso para ayudar a evaluar los campos. Para la interpretación de resultados, vea [Comprender sus resultados](#understand-your-results). El agente de detección de campos devuelve únicamente información de campo; no crea audiencias, ejecuta consultas ni inserta datos en otras herramientas. Después de identificar un campo, lea su ruta XDM de la columna **[!UICONTROL Nombre de campo]** y utilícela en el flujo de trabajo descendente.

### Identificar campos para un concepto empresarial

Al describir un concepto o atributo de datos específico, el agente de detección de campos devuelve una lista clasificada de campos que coinciden semánticamente con la descripción.

> &quot;¿Qué campos representan el estado o la provincia de origen de un cliente?&quot;
> &quot;Buscar campos relacionados con la fecha de transacción de compra.&quot;
> &quot;¿Qué campos contienen información sobre el consentimiento de marketing por correo electrónico?&quot;

La respuesta enumera los campos candidatos con su etiqueta de relevancia y ruta XDM en el panel **[!UICONTROL Campos identificados]**. Los campos etiquetados como **[!UICONTROL Muy relevante]** se asemejan más a su concepto indicado. Si los resultados principales están etiquetados como **[!UICONTROL Moderadamente relevante]** o **[!UICONTROL Relevante]** en lugar de **[!UICONTROL Altamente relevante]**, refina la consulta usando una terminología más específica o un contexto de nivel de campo.

### Obtener recomendaciones de campo para un caso de uso

Cuando describe un objetivo de flujo de trabajo o un caso de uso, como crear un segmento, incorporar un conjunto de datos o preparar una consulta, Field Discovery Agent recomienda campos alineados con ese objetivo, priorizados por la relevancia.

> &quot;Quiero crear una audiencia de clientes de alto valor. ¿Qué campos debo utilizar?&quot;
> &quot;Campos recomendados para modelar la tendencia de compra&quot;.
> &quot;¿Qué campos debo incluir al incorporar un conjunto de datos de transacciones minoristas?&quot;

La respuesta devuelve una lista priorizada de campos con contexto de relevancia. Revise el contexto de uso de cada campo recomendado para confirmar que se utiliza activamente en su entorno.

### Enriquecimiento del contexto de campo

Cuando se pregunta por un campo específico por su nombre o ruta, el agente de detección de campos devuelve un contexto detallado para ese campo, incluidos valores de muestra, ubicación de esquema y uso en conjuntos de datos, audiencias y destinos.

> &quot;Más información acerca del campo `person.name.lastName`&quot;.
> &quot;¿Qué valores de muestra existen para `homeAddress.stateProvince`?&quot;
> &quot;¿Dónde se utiliza el campo `commerce.purchases.value` en mis conjuntos de datos y audiencias?&quot;

La respuesta devuelve los valores de muestra del campo, la ubicación del esquema, los conjuntos de datos asociados y cualquier audiencia o destino en el que aparezca el campo. Revise este contexto para confirmar que el campo contiene los datos esperados.

## Dentro y fuera de ámbito {#in-scope-and-out-of-scope}

Esta sección resume lo que puede y no puede hacer el agente de detección de campos. Para obtener instrucciones detalladas sobre la tarea, consulte [Casos de uso admitidos](#supported-use-cases). Para ver las restricciones de la plataforma, consulte [Protecciones y limitaciones](#guardrails-and-limitations).

### En ámbito

En la siguiente lista se describen las tareas que puede realizar el agente de detección de campos; utilícelo para confirmar si el agente puede satisfacer su solicitud antes de depender de ella en el flujo de trabajo.

- Identificación de campos XDM que coinciden con un concepto empresarial o una descripción en lenguaje natural.
- Campos recomendados para un objetivo de flujo de trabajo establecido o un caso de uso.
- Enriquecimiento de un campo específico con valores de muestra, ubicación de esquema y contexto de uso.
- Devolver resultados clasificados por relevancia semántica, etiquetados como Muy relevante, Moderadamente relevante o Relevante.
- Mostrar valores de muestra dentro de los permisos autorizados del conjunto de datos.

### Fuera de ámbito

La siguiente lista describe las acciones que el agente de detección de campos no realiza; utilícelo para evitar depender del agente para trabajar fuera de su ámbito.

- Modifique esquemas, conjuntos de datos, campos o audiencias.
- Cree o publique audiencias o segmentos.
- Ejecutar consultas o activar datos en destinos.
- Acceda a campos o conjuntos de datos fuera de los permisos autorizados.
- Exponer la lógica de incrustación interna, la arquitectura de base de datos vectorial o los detalles de implementación de vinculación de entidades.
- Garantice una ventana de tiempo específica para las actualizaciones de la base de conocimiento después de cambios del esquema o del conjunto de datos.

## Mecanismos de protección y limitaciones {#guardrails-and-limitations}

Estas protecciones son importantes porque el agente de detección de campos funciona dentro de restricciones de nivel de plataforma que afectan a la disponibilidad y calidad de los resultados. Utilícelos para interpretar los resultados que faltan, los que se retrasan o los que están incompletos, y para solucionar los huecos inesperados con expectativas realistas.

### Base de conocimiento

Field Discovery Agent se basa en una base de conocimiento que se actualiza periódicamente con esquemas y metadatos de su entorno de Experience Platform. Los resultados reflejan el estado de la base de conocimiento en el momento de la consulta, no el estado en tiempo real de los esquemas, y puede haber un retraso entre la ingesta de datos y el momento en que aparece en el agente.

Es posible que los nuevos esquemas, campos o conjuntos de datos agregados al entorno no aparezcan inmediatamente en los resultados de Field Discovery Agent. Los resultados pueden tardar un tiempo en reflejar los cambios recientes.

>[!NOTE]
>
>El intervalo de actualización de la base de conocimiento está sujeto a cambios. Si un campo añadido recientemente no aparece en los resultados, deje tiempo para que la base de conocimiento se actualice y vuelva a enviar la consulta.

### Calidad y cobertura de metadatos

La calidad de los resultados depende de la calidad y la integridad de los metadatos de los campos en el entorno de Experience Platform. El agente utiliza nombres de campo, nombres para mostrar, descripciones y asociaciones de uso para clasificar los resultados. Es posible que los campos con metadatos deficientes o que falten no aparezcan en los resultados o que se clasifiquen por debajo de lo esperado.

Si tiene acceso a la edición de esquemas, puede mejorar la calidad de los resultados mediante lo siguiente:

- Utilizar nombres para mostrar claros y descriptivos para los campos en los esquemas.
- Agregar descripciones de campo siempre que sea posible.
- Asociar campos a conjuntos de datos activos en lugar de dejarlos como definiciones solo de esquema.

Para obtener instrucciones sobre cómo editar nombres para mostrar y descripciones de campos en el Editor de esquemas, consulte [Crear y editar esquemas en la interfaz de usuario](https://experienceleague.adobe.com/es/docs/experience-platform/xdm/ui/resources/schemas).

Si no tiene acceso a la edición de esquemas y los resultados son deficientes de forma consistente, póngase en contacto con el administrador de Experience Platform o con el equipo de ingeniería de datos para revisar los metadatos de los campos de los esquemas con los que trabaja.

### Restricciones de acceso y PII

Field Discovery Agent respeta todos los controles de acceso de Experience Platform existentes y funciona dentro del contexto de la zona protegida actual. Solo se reciben resultados para campos de esquemas y conjuntos de datos a los que está autorizado a acceder.

Los valores de muestra están regidos por los mismos permisos de nivel de conjunto de datos. Los campos de conjuntos de datos con perfil habilitado con restricciones PII devuelven valores de muestra solo si tiene el acceso requerido. Consulte [Valores de muestra](#sample-values) para obtener instrucciones de administración. El agente de detección de campos no omite la seguridad de nivel de campo ni las restricciones de acceso habilitadas para perfiles.

## Prácticas recomendadas {#best-practices}

Siga estas directrices para obtener resultados precisos y procesables de Field Discovery Agent.

- **Sea específico sobre el concepto, no solo sobre el tipo de campo.** Un mensaje como &quot;encontrar un campo de estado&quot; produce resultados de menor calidad que &quot;encontrar el campo que contiene el estado de EE. UU. de un cliente para la segmentación geográfica&quot;. La especificidad le da al agente más señal para comparar con sus metadatos. Consulte [Funcionamiento del agente de detección de campos](#how-field-discovery-agent-works) para saber por qué esto es importante.
- **Use una terminología que coincida con los metadatos del esquema.** Si los esquemas utilizan el término &quot;transacción&quot; en lugar de &quot;compra&quot;, utilice &quot;transacción&quot; en los indicadores. El agente compara nombres de campo y descripciones reales, no solo conceptos generales.
- **Verificar campos antes de confirmar.** Después de buscar campos candidatos, pregunte por un campo específico por nombre o ruta para revisar sus valores de muestra y contexto de uso antes de utilizarlo en un segmento o consulta. Esto reduce el riesgo de seleccionar el campo incorrecto.
- **Iterar cuando los resultados sean Relevantes o Relevantes en lugar de Relevantes.** Reformule la consulta con una terminología diferente o agregue más contexto sobre su caso de uso. Una segunda consulta, más específica, a menudo muestra mejores candidatos.
- **Incluir contexto de ámbito en las indicaciones.** Para la segmentación basada en regiones geográficas, incluya la región de destino. Para consultas basadas en el tiempo, incluya el atributo de tiempo. Cuanto más contexto proporcione, más objetivo será la clasificación de resultados.

## Ejemplos de peticiones {#example-prompts}

Utilice esta sección como biblioteca de mensajes de referencia rápida. Si no tiene experiencia previa con Field Discovery Agent, lea primero [Prácticas recomendadas](#best-practices) y [Casos de uso admitidos](#supported-use-cases) para saber cuándo y por qué se aplica cada función.

### Indicadores de identificación

Utilice estas indicaciones cuando conozca el concepto de datos que necesita, pero no el campo que lo contiene.

> &quot;¿Qué campo contiene el estado o la región de un cliente?&quot;
> &quot;Busque campos relacionados con el estado de suscripción de correo electrónico.&quot;
> &quot;¿Qué campo contiene la fecha de la primera compra de un cliente?&quot;
> &quot;Identifique los campos que representan el valor de duración del cliente&quot;.
> &quot;¿Qué campos del esquema de perfil se relacionan con la pertenencia al programa de fidelidad?&quot;

### Mensajes de recomendación

Utilice estas indicaciones cuando inicie un flujo de trabajo y necesite instrucciones sobre los campos que desea incluir para un objetivo específico.

> &quot;¿Qué campos debo utilizar para crear una audiencia de renovación de la participación?&quot;
> &quot;Campos recomendados para una audiencia dirigida a clientes que no han realizado compras en 90 días&quot;.
> &quot;¿Qué campos son más útiles para modelar el riesgo de pérdida?&quot;
> &quot;Sugerir campos que se deben incluir al crear una segmentación geográfica.&quot;
> &quot;Estoy construyendo un modelo de tendencia a comprar. ¿Con qué campos debo empezar?&quot;

### Mensajes de enriquecimiento

Utilice estos indicadores cuando tenga un campo candidato y desee verificarlo antes de utilizarlo en un segmento, consulta o asignación.

> &quot;Más información sobre `homeAddress.stateProvince`&quot;.
> &quot;Mostrarme valores de muestra para `commerce.purchases.value`&quot;.
> &quot;¿Dónde se utiliza `person.name.lastName` en mis conjuntos de datos y audiencias?&quot;
> &quot;¿Qué conjuntos de datos contienen el campo `web.webPageDetails.URL`?&quot;
> &quot;¿Está `segmentMembership` asignado a algún destino activo?&quot;

## Solución de problemas {#troubleshooting}

Utilice esta sección cuando falten resultados, cuando no estén esperados o cuando no esté seguro de si el agente de detección de campos ha gestionado su solicitud.

- **Un campo agregado recientemente no aparece en los resultados.** Es posible que la base de conocimiento aún no refleje el nuevo esquema o campo. Deje tiempo para que la base de conocimiento se actualice después de agregar esquemas o campos al entorno y, a continuación, vuelva a enviar la consulta. Consulte [Base de conocimiento](#knowledge-base).

- **Todos los resultados están etiquetados como Relevante moderado o Relevante en lugar de Relevante alto.** La consulta puede ser demasiado amplia o la terminología utilizada puede no coincidir con los metadatos del campo. Refine el mensaje con términos o lenguaje más específicos que se alineen con el modo en que se asignan los nombres a los campos en los esquemas. Consulte [Prácticas recomendadas](#best-practices).

- **No se invocó al agente de detección de campos.** Ha enviado una consulta en el Asistente de inteligencia artificial, pero el panel **[!UICONTROL Razonamiento completado]** no indica el agente de detección de campos. Es posible que la consulta no haya incluido una intención de detección de campos clara. Restablezca la consulta explícitamente (por ejemplo, &quot;Busque el campo que contiene el estado de exclusión del correo electrónico del cliente&quot;) y vuelva a enviarla. Consulte [Usar agente de detección de campos](#use-field-discovery-agent).

- **Los valores de muestra no aparecen para un campo.** El campo puede estar vacío en la zona protegida actual, los permisos pueden no incluir el acceso a su conjunto de datos subyacente o el campo puede tener una alta cardinalidad (como un campo de ID) para la que no se muestran valores de muestra. Confirme los permisos de acceso al conjunto de datos y compruebe que el campo se rellena con datos. Consulte [Restricciones de acceso y PII](#access-and-pii-constraints).

- **Los resultados incluyen campos de esquemas que no esperaba.** Field Discovery Agent busca todos los esquemas y conjuntos de datos de su zona protegida actual a los que puede acceder con sus permisos. Si aparecen resultados inesperados, confirme el contexto de la zona protegida activa en el Ayudante de IA y compruebe qué esquemas y conjuntos de datos son accesibles para su función.

Para comprobar qué agente gestionó su solicitud, consulte el paso 6 de [Usar el agente de detección de campos](#use-field-discovery-agent).
