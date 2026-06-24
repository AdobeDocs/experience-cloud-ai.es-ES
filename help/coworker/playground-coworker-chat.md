---
title: Introducción Al Chat Con Compañeros En El Patio De Juegos
description: Aprenda a utilizar el chat de compañeros en el patio de recreo para explorar cómo las indicaciones en lenguaje natural pueden ayudarle a aprender, investigar y perfeccionar su trabajo.
hide: true
source-git-commit: ea975ce8a0386f9d340014ab7755761815bcf8ae
workflow-type: tm+mt
source-wordcount: '1671'
ht-degree: 4%

---

# Introducción al chat con compañeros en el patio de recreo

Use el chat de compañeros en el patio de recreo para explorar cómo las indicaciones en lenguaje natural pueden ayudarle a aprender, investigar y perfeccionar su trabajo. Playground proporciona ejemplos de cómo iniciar una conversación para que puedas entender rápidamente lo que Coworker Chat puede hacer.

>[!IMPORTANT]
>
>Utilice lo siguiente para completar este ejercicio:
>
>- Vínculo: [ao.adobe.io](https://ao.adobe.io/)
>- Instancia: AEP GenAI - VA7
>- Espacio aislado: `fsi-box`

## Demostración de AI Coworker: [!DNL weBank] campaña de actualización de tarjeta de crédito

Este ejercicio cubre Real-Time CDP y Adobe Journey Optimizer.

Usted es estratega de CX Enterprise en **[!DNL weBank]**, una compañía de servicios financieros con prioridad digital. Utilice el asistente de IA para pasar de los datos sin procesar a una campaña en directo, completamente a través de la conversación.

## Parte 1: Comprender su negocio

### 1.1 — Obtén la disposición de la tierra

**Mensaje**

> Obtenga información general sobre mi zona protegida: ¿cuántas audiencias, conjuntos de datos y destinos tengo?

**Resultado esperado**

Compañero de trabajo devuelve un inventario de zona protegida completo en segundos:

| Recurso | Count |
| --- | --- |
| Públicos | 21 |
| Conjuntos de datos | 30 |
| Esquemas | 28 |
| Fuentes | 3 |
| Destinos | 1 (Amazon S3) |
| Recorridos | 0 |

### 1.2 — ¿Qué audiencias ya existen?

**Mensaje**

> Mostrar todas mis audiencias ordenadas por tamaño

**Resultado esperado**

Coworker enumera 21 audiencias clasificadas por tamaño, de 8.012 perfiles hasta 0:

| Categoría | Público | Perfiles |
| --- | --- | --- |
| Puntuaciones de tendencia | Actualización de tarjeta de crédito alta | 1,195 |
| Puntuaciones de tendencia | Medio | 4,113 |
| Puntuaciones de tendencia | Bajo | 8,012 |
| Tendencia hipotecaria | Alto | 1,233 |
| Tendencia hipotecaria | Medio | 4,141 |
| Tendencia hipotecaria | Bajo | 7,946 |
| Niveles de valor de cuenta | +500K | 4,377 |
| Niveles de valor de cuenta | 250-500 ºK | 4,537 |
| Niveles de valor de cuenta | 100-250K | 2,666 |
| Niveles de valor de cuenta | 50-100K | 894 |
| Niveles de valor de cuenta | &lt;50K | 846 |
| Demografía | Mujer | 6,719 |
| Demografía | Hombre | 6,601 |
| Geografía | Costa Este | 2,260 |
| Geografía | Costa oeste | 1,740 |
| Inclusión en el canal | Correo electrónico | 6,597 |
| Inclusión en el canal | SMS | 6,675 |
| Cumpleaños | Cumpleaños de este mes | 0 |
| Cumpleaños | En 7 días | 0 |
| Cumpleaños | Hoy | 0 |
| Cumpleaños | Próximos 30 días | 0 |

Actualmente, todas las audiencias de cumpleaños muestran 0 porque dependen del tiempo.

### 1.3 — ¿Qué datos alimentan a estas audiencias?

**Mensaje**

> ¿Qué conjuntos de datos tengo que contienen datos de clientes?

**Resultado esperado**

Coworker identifica dos conjuntos de datos empresariales clave y conjuntos de datos del sistema relacionados:

| Conjunto de datos | Descripción |
| --- | --- |
| **weBank: CRM** | Datos de cuenta/perfil del cliente (perfil + identidad habilitada) |
| **weBank: Acciones del cliente** | Datos de evento de comportamiento (perfil + identidad habilitados) |

Los conjuntos de datos de System Journey Optimizer para señales de participación incluyen el seguimiento de correo electrónico, el seguimiento push, el consentimiento y los comentarios de mensajes.

## Parte 2: Descubra los campos adecuados

### 2.1 — Buscar campos de valor de cuenta

**Mensaje**

> ¿Qué campos están disponibles en relación con el valor o el saldo de la cuenta?

**Resultado esperado**

El compañero muestra el campo principal y los campos relacionados en el conjunto de datos **weBank: CRM**:

| Campo | Notas |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.totalAccountValue` | Campo principal; se utiliza en las 5 audiencias de nivel Valor de la cuenta |
| `numberOfAccounts` | Campo relacionado |
| `accountType` | Campo relacionado |
| `currentStatement` | Campo relacionado |
| `actionAmount` | Campo relacionado |

### 2.2 — Buscar campos de tarjeta de crédito

**Mensaje**

> Buscar campos relacionados con la tarjeta de crédito o el tipo de tarjeta

**Resultado esperado**

El compañero identifica estos campos en el esquema **weBank: CRM**:

| Campo | Descripción |
| --- | --- |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardType` | Tipo de tarjeta de tienda (Visa, Mastercard, Amex) |
| `_aepgenai_va7.fsiBankAccountDetails.creditcardHolder` | Nombre del titular |

### 2.3 — Campos geográficos

**Mensaje**

> ¿Hay algún campo para el estado o la región de origen?

**Resultado esperado**

El compañero identifica los campos geográficos en el conjunto de datos **weBank: CRM**:

| Campo | Notas |
| --- | --- |
| `homeAddress.state` | Abreviatura estatal de EE. UU.; se utiliza en Lives on East Coast y Lives on West Coast |
| `homeAddress.stateProvince` | También se encuentran |
| `homeAddress.region` | También se encuentran |
| `placeContext.geo.stateProvince` | También se encuentran |

## Parte 3: Encontrar la audiencia adecuada para una campaña de reactivación

### 3.1 — Solicite a la AI que le ayude a encontrar la audiencia adecuada

**Mensaje**

> Ayúdeme a encontrar o crear la audiencia adecuada para una campaña de reactivación de tarjetas de crédito. Quiero dirigirme a clientes a los que se les calificó como de alta o media tendencia a una actualización de tarjeta de crédito, pero que aún no han tomado medidas

**Resultado esperado**

Su compañero encuentra dos audiencias candidatas que nunca se han segmentado en un recorrido o destino:

| Público | Perfiles |
| --- | --- |
| Actualización de tarjeta de crédito alta | 1,195 |
| Medium de actualización de tarjeta de crédito | 4,113 |

Opciones recomendadas:

| Opción | Enfoque |
| --- | --- |
| **A** | Utilice ambos directamente con ramificación de recorrido: oferta agresiva para Alta, nutrir para Medium |
| **B** | Crear un segmento de segmentos derivado con lógica de exclusión de actualización para una administración más limpia |

Tamaño combinado: aproximadamente 5.308 perfiles

### 3.2 — Crear la audiencia de precisión

**Mensaje**

> Cree una audiencia de clientes que se encuentren en la audiencia &quot;Tendencias: Actualización de tarjeta de crédito alta&quot; Y que tengan un valor de cuenta superior a 250 000 $ Y que se hayan suscrito al correo electrónico

Asígnele el nombre **Actualización Platinum - Correo electrónico de alto valor elegible** → Seleccionar lote → Aprobar plan

**Resultado esperado**

El compañero clasifica la tendencia de ML, el valor financiero y la idoneidad para el canal en un segmento de precisión: trabajo que normalmente requeriría un ticket de equipo de datos.

### 3.3 — Tamaño estimado y cascada

**Mensaje**

> ¿Cómo de grande es esa audiencia? Muéstrame el desglose de la cascada.

**Resultado esperado**

El compañero de trabajo devuelve una estimación del recuento de perfiles en tiempo real y un gráfico visual de cascada:

| Paso de filtro | Resultado |
| --- | --- |
| Actualización de tarjeta de crédito de alta tendencia | Aproximadamente 1.195 perfiles |
| + Valor de cuenta superior a 250 000 $ | Se estrecha más |
| + Inclusión por correo electrónico | Recuento final direccionable |

Esto muestra exactamente qué condición es el filtro más grande y si se deben aflojar los criterios.

### 3.4 — Comprobar audiencias similares

**Mensaje**

> ¿Hay alguna audiencia similar a la que acabo de crear?

**Resultado esperado**

El compañero confirma que no existe una audiencia combinada única, pero que todos los componentes básicos ya están presentes:

| Bloque de creación | Detalles |
| --- | --- |
| Tendencias: Actualización de tarjeta de crédito Alta | Puntuación ≥ 90 |
| Valor de la cuenta: 250-500 K | Audiencia existente |
| Valor de la cuenta: +500K | Audiencia existente |
| Inclusión de correo electrónico | `consents.marketing.email.val = "y"` |

El compañero confirma que no hay riesgo de duplicación y recomienda continuar.

## Parte 4: Creación del Recorrido

### 4.1: obtenga ideas de recorrido basadas en sus datos

**Mensaje**

> En función de los casos de uso populares en los servicios financieros, sugiero algunos recorridos de ganancia rápida que puedo crear con las audiencias que tengo

**Resultado esperado**

Coworker sugiere cinco ideas concretas de recorrido basadas en audiencias reales:

| idea de recorrido | Públicos |
| --- | --- |
| Cumpleaños de lealtad | Cumpleaños en un plazo de 7 días + Niveles de valor de cuenta |
| Nutrición de actualización de tarjeta de crédito | Alta actualización CC + Inclusión por correo electrónico |
| Alcance regional hipotecario | Hipoteca Alta + Costa Este/Oeste |
| Actualización de nivel aconsejable de patrimonio | Valor de la cuenta: +500K |
| Activación en canales múltiples de inclusión | Inclusión de correo electrónico menos inclusión de SMS |

### 4.2 — Crear el recorrido de actualización de la tarjeta de crédito

**Mensaje**

> Cree un recorrido con la audiencia &quot;Actualización de platino: correo electrónico de alto valor apto&quot;. Envíe una notificación push presentando las ventajas de la tarjeta Platinum Card de WeBank. Espera 3 días. Si el cliente no ha solicitado la transacción, envíe un SMS con una oferta de tiempo limitado del 0% APR durante 12 meses en transferencias de saldo. Espera 5 días más. Si todavía no hay solicitud, envíe una notificación push final con una invitación bancaria personal.

Revisar plan → aprobar plan → conceder permisos

**Resultado esperado**

El compañero crea un recorrido completo de dos canales y tres toques a partir de una sola descripción en lenguaje natural, que incluye temporizadores de espera, comprobaciones de estado y escalado de ofertas.

### 4.3 — Bonificación: crear un recorrido a partir de una imagen

**Mensaje**

> Crear este recorrido a partir de la imagen que he cargado

**Resultado esperado**

Su compañero lee la imagen cargada (incluidos nodos, canales, tiempos de espera y condiciones) y genera el recorrido completo en Journey Optimizer. Esto convierte un artefacto de planificación directamente en un recorrido implementable.

### 4.4 — Comprobar conflictos

**Mensaje**

> ¿Hay algún recorrido activo que pueda entrar en conflicto con el recorrido que acabo de crear?

**Resultado esperado**

El compañero comprueba automáticamente todos los recorridos activos en busca de superposición de audiencias, conflictos de programación y saturación de canal.

## Parte 5: Convertir los abandonos de Recorrido en una nueva audiencia

### 5.1 — Identificación del punto de entrega

**Mensaje**

> Muéstreme el recorrido que acabo de crear e identifique qué paso tiene la mayor caída

**Resultado esperado**

El compañero analiza los eventos de paso del recorrido y muestra el nodo con la tasa de salida más alta. Por ejemplo:

> El 68 % de los perfiles que recibieron el primer correo electrónico nunca lo abrieron y salieron antes del paso de SMS.

### 5.2 — Crear una audiencia desplegable

**Mensaje**

> Convierta esos descensos de recorrido en una nueva audiencia: personas que entraron en el recorrido de actualización de Platino pero que nunca llegaron al paso de SMS

Asígnele el nombre **Actualización Platinum - No respondedores de correo electrónico** → Seleccionar lote → Aprobar plan

**Resultado esperado**

El compañero crea una nueva audiencia neta basada en los datos de comportamiento del recorrido: perfiles que entraron en el recorrido pero que no progresaron al paso de SMS. Esta audiencia se puede utilizar inmediatamente para una campaña de seguimiento.

### 5.3 — Reactivación de los descensos

**Mensaje**

> Cree un recorrido de reactivación para la audiencia &quot;Actualización de Platino: no respondedores de correo electrónico&quot;. Pruebe un enfoque diferente: empiece con una notificación push que destaque una oferta de 75 000 puntos de bonificación por tiempo limitado, espere 2 días y envíe una invitación por correo directo para visitar su sucursal local.

Revisar plan → aprobar plan → conceder permisos

**Resultado esperado**

El colaborador crea un recorrido de recuperación específico utilizando diferentes canales y mensajes para los no respondedores. Ahora ha cerrado el bucle de una fuga de conversión, completamente a través de la conversación.

## Parte 6: Control de calidad y validación automatizados

### 6.1 — Comprobación del estado de la ingesta y de la actualización de datos

**Mensaje**

> ¿Hay algún problema de calidad de datos con los conjuntos de datos que alimentan a mis audiencias? Comprobar el estado de ingesta de weBank: CRM y weBank: Acciones del cliente

**Resultado esperado**

El compañero informa del estado de ingesta para cada conjunto de datos:

| Conjunto de datos | Estado | Detalles |
| --- | --- | --- |
| **weBank: CRM** | Sano | 39 registros ingeridos, 32 del perfil, cero errores |
| **weBank: Acciones del cliente** | Indicador menor | 441 registros ingeridos; 35 tenían marcas de tiempo caducadas; aproximadamente el 8 % se excluyó debido a la ventana de TTL |

Recomendación: revise la configuración de TTL o compruebe si hay registros obsoletos en el sistema de origen.

### 6.2 — Validar el recorrido antes de publicar

**Mensaje**

> Revise el recorrido de actualización de Platinum para ver si hay errores o problemas de calidad. Compruebe si faltan temporizadores de espera, rutas de callejón sin salida, configuraciones de canal que faltan y lagunas de idoneidad de audiencia

**Resultado esperado**

El compañero inspecciona la estructura del recorrido y marca problemas como los siguientes:

| Tipo de problema | Ejemplo |
| --- | --- |
| Rutas de callejones sin salida | Rutas que no terminan con un nodo final |
| Configuración de canal | Acciones que carecen de configuraciones de superficie de canal |
| Temporizadores de espera | Temporizadores que podrían causar problemas con SLA |
| Contenido | Nodos a los que falta contenido |

## Parte 7: Monitoreo y gobernanza

### 7.1 — Seguimiento del estado de la audiencia a lo largo del tiempo

**Mensaje**

> Muéstreme cómo ha cambiado la audiencia &quot;Tendencias: Alta actualización de tarjetas de crédito&quot; en los últimos 30 días

**Resultado esperado**

Coworker devuelve una vista de serie temporal del crecimiento o la caída de la audiencia con análisis de tendencias, lo que le ayuda a identificar si la puntuación del modelo XML está a la deriva o los cambios en los datos de flujo ascendente están afectando a la calificación.

### 7.2 — Diagnóstico de un cambio

**Mensaje**

> ¿Por qué la audiencia &quot;Valor de cuenta: +500 000&quot; ha caído recientemente?

**Resultado esperado**

El colaborador realiza un análisis causal al descomponer el cambio en:

| Factor | Pregunta |
| --- | --- |
| Actualización de datos | ¿Había un hueco en la ingesta? |
| Combinar cambios de política | ¿Cambió la vinculación de perfil? |
| Cambios de origen ascendente | ¿Los datos de CRM dejaron de fluir? |
| Comportamiento real del cliente | ¿Bajaron los valores de la cuenta de verdad? |

Esto sustituye a los 1-2 días de clasificación de analistas.

