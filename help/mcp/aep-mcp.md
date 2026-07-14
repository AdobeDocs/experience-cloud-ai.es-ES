---
title: Herramientas Adobe Experience Platform en CX Coworker Gateway
description: Descubra qué herramientas de Adobe Experience Platform están disponibles a través de CX Coworker Gateway.
source-git-commit: adb72f43865bee5b2b151a5a75994c5f3939c2d9
workflow-type: tm+mt
source-wordcount: '1372'
ht-degree: 8%

---


# Herramientas de Adobe Experience Platform en Adobe CX Coworker Gateway {#aep-mcp}

Puede utilizar las herramientas de producto de Adobe Experience Platform para inspeccionar esquemas, conjuntos de datos, configuración de control de datos, recursos del servicio de consultas y eventos de auditoría desde un cliente compatible con MCP. Estas herramientas están disponibles a través de [Adobe CX Coworker Gateway](overview.md) cuando su organización está habilitada y su cuenta de usuario tiene los permisos de Experience Platform requeridos.

>[!AVAILABILITY]
>
>La herramienta de producto de Experience Platform se encuentra en Beta. El acceso se realiza únicamente por invitación y requiere la habilitación de la organización de Adobe. Consulte [Herramientas de Access CX Coworker Gateway](access.md).

## Resumen

| Herramienta | Descripción | Recurso | Competencias | Estado |
| --- | --- | --- | --- | --- |
| `search_allowed_ip_ranges` | Recuperar restricciones de acceso IP del servicio de consultas | Autenticación de Distiller de datos · Intervalos de IP | list | Activo |
| `search_audit` | Enumerar eventos de auditoría de actividades de usuario en Experience Platform | Consulta de auditoría · eventos de auditoría | lista, filtrar por tipo de recurso, acción, estado, intervalo de tiempo | Activo |
| `search_datasets` | Metadatos de ingesta por lotes y conjuntos de datos de consulta | API de catálogo · dataSets, lotes | lista, obtener, filtrar, enumerar los últimos, enumerar los archivos | Activo |
| `search_class_relations` | Buscar relaciones de clase empresarial de Experience Platform | Relaciones de clase · índice YAML estático | buscar por token, término múltiple, coincidencia parcial | Activo |
| `search_data_access` | Enumerar archivos de lotes de ingesta con errores | API de acceso a datos · lotes con errores | enumerar archivos con errores | Activo |
| `search_data_lake` | Inspeccionar metadatos de conjuntos de datos y estado de lotes | API de Data Lake · conjuntos de datos, lotes | obtener, obtener tamaño, enumerar lotes con errores | Activo |
| `search_dule` | Etiquetas, políticas y acciones de gobernanza de datos de consulta | Administración de datos · etiquetas, políticas, marketing_actions | list, get, list enabled, evaluate | Activo |
| `search_query_service` | Consultas, consultas SQL, plantillas, programaciones, alertas | Servicio de consultas: consultas, plantillas, programaciones y alertas | list, get, filter, get connection params | Activo |
| `search_schema_registry` | Esquemas, grupos de campos, clases y tipos de XDM de consulta | Registro de esquemas: esquemas, grupos de campos, clases, data_types, descriptores | lista, obtener, filtrar por contenedor | Activo |

## Referencia de herramienta

### search_allowed_ip_range

**Recurso:** Autenticación de Distiller de datos · Intervalos de IP
**Estado:** activo

Recupere todas las restricciones de acceso IP configuradas para el servicio de consulta en la zona protegida actual. Devuelve el ID de organización y la lista de intervalos de IP permitidos. Solo está disponible para los clientes con el complemento Data Distiller.

**Capacidades:** enumera los intervalos de IP permitidos para el servicio de consultas

No hay parámetros.

### search_audit

**Recurso:** Consulta de auditoría · eventos de auditoría
**Estado:** activo

Enumere registros con marca de tiempo de actividades de usuario en todos los servicios de Experience Platform. Devuelve el tipo de acción, el correo electrónico del usuario, la información del recurso y el estado del evento. Use `asset_type` y `action` para reducir los resultados. El valor predeterminado son los últimos 7 días cuando no se especifica ningún intervalo de tiempo. Limitado a los últimos 1000 registros y eventos de los últimos 90 días.

**Funciones:** enumerar eventos de auditoría, filtrar por tipo de recurso, acción, estado, intervalo de tiempo, paginación

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `action` | No | Filtrar por tipo de acción. Valores comunes (separados por comas para OR): `Create`, `Delete`, `Update`, `Enable`, `Disable` |
| `asset_type` | No | Filtre por tipo de recurso. Debe ser uno de: `Dataset`, `Schema`, `Segment`, `Destination`, `Source Data Flow`, `Merge Policy`, `Identity Namespace`, `Identity Graph`, `Sandbox`, `Role`, `Query`, `Scheduled Query`, `Datastream`, `Computed Attribute`, `Field Group`, `Class`, `Data Types`, `Account`, `Product Profile`, `Query Template`, `Work Order`, `Audit Logs`, `Access Control Policy` |
| `status` | No | Filtre por estado de evento. Valores: `Success`, `Failure`, `Allow`, `Deny`. Separación por comas para OR |
| `start_time` | No | Marca de hora más temprana. ISO 8601 UTC con ms, p. ej. `2024-01-15T00:00:00.000Z` |
| `end_time` | No | Última marca de tiempo. ISO 8601 UTC con ms |
| `property_filter` | No | Expresión de filtro sin procesar, p. ej. `action==create`. Prefiera los parámetros dedicados anteriores |
| `orderby` | No | Orden: `timestamp` (asc) o `-timestamp` (desc) |
| `limit` | No | Número máximo de resultados (3-1000, predeterminado 50) |
| `start` | No | Desplazamiento de paginación. Incrementar por valor límite para cada página |
| `query_id` | No | ID de consulta de una respuesta anterior para repetir la misma consulta |

### search_datasets

**Recurso:** API de catálogo · dataSets, lotes
**Estado:** activo

Herramienta de envío unificado para el servicio de catálogo de Experience Platform. Metadatos de conjuntos de datos de consulta (referencias de esquema, etiquetas, información de creación) o registros de ingesta por lotes (estado, métricas, listas de archivos). Use `dataset/list` para descubrir conjuntos de datos, `batch/list` para comprobar el estado de la ingesta y `batch/list_files` o `batch/get_meta_files` para inspeccionar el contenido específico del lote. Todas las operaciones son de solo lectura.

**Capacidades:** enumerar conjuntos de datos, obtener conjunto de datos, enumerar lotes, obtener lote, enumerar el último lote por conjunto de datos, enumerar archivos por lotes, obtener archivos meta por lotes (errores de fila, archivos de entrada)

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `dataset` o `batch` |
| `operation` | Sí | `list`, `get`, `list_last`, `list_files`, `get_meta_files`. Combinaciones válidas: conjunto de datos → lista, obtener; lote → los cinco |
| `resource_id` | No | Conjunto de datos o ID de lote. Necesario para `dataset/get`, `batch/get`, `batch/list_files`, `batch/get_meta_files` |
| `query_params.limit` | No | Resultados máximos por página (máximo 100). Se aplica a todas las operaciones de lista |
| `query_params.start` | No | Desplazamiento de paginación. Se aplica a todas las operaciones de lista |
| `query_params.order_by` | No | Dirección del orden, p. ej. `asc:created,updated`. Se aplica a todas las operaciones de lista |
| `query_params.properties` | No | Lista de permitidos de propiedades separadas por comas. Se aplica a dataset/list, dataset/get, batch/list, batch/list_last |
| `query_params.name` | No | Filtrar conjuntos de datos por nombre (solo conjunto de datos/lista) |
| `query_params.tags` | No | Filtrar conjuntos de datos por etiquetas, p. ej. `unifiedProfile:enabled:true` (solo conjunto de datos/lista) |
| `query_params.property_filter` | No | Filtro regex en objetos de respuesta (conjunto de datos/lista y lote/lista) |
| `query_params.status` | No | Filtrar lotes por estado: `success`, `failed`, `loading`, `active` (solo lote/lista) |
| `query_params.dataset_id` | No | Asignar lotes a un conjunto de datos específico (lote/lista y lote/lista_último) |
| `query_params.created_after` | No | Filtrar lotes creados después de la marca de tiempo Unix en ms (solo lote/lista) |
| `query_params.created_before` | No | Filtrar lotes creados antes de la marca de tiempo Unix en ms (solo lote/lista) |
| `query_params.last_batch_status` | No | Filtrar por el último estado del lote (batch/list_last solamente) |
| `query_params.aggregate` | No | Devolver métricas agregadas en el nivel raíz (lote/obtener solo) |
| `query_params.path` | No | Archivo Meta para descargar: `row_errors`, `input_files`, `row_errors_sample.json` (solo batch/get_meta_files) |

### search_class_Relations

**Recurso:** relaciones de clase · índice YAML estático
**Estado:** activo

Busque relaciones de clase empresarial de Experience Platform por nombre mediante el índice estático `class_relations_v1.yaml`. No se realizan llamadas a la API de Experience Platform. Acepta un único término o términos separados por comas; cada término se compara con los nombres de clase utilizando la coincidencia de tokens parciales. Devuelve clases coincidentes con relaciones directas (a las que apunta cada clase) y relaciones inversas (a las que las clases apuntan de nuevo). Utilice esto para comprender las relaciones de entidad antes de crear consultas, flujos de datos o composiciones de esquema.

**Capacidades:** búsqueda por token, búsqueda separada por comas de varios términos, coincidencia de token parcial, expansión de sinónimo bidireccional

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `query` | Sí | Nombre de clase empresarial o tipo de objeto que buscar. Admite coincidencias parciales de tokens (`dat` coincide con `dataset`, `data_type`, etc.). Pase varios términos separados por comas para buscar varias clases a la vez (p. ej. `dataset, schema`) |
| `n` | No | Número máximo de resultados coincidentes que se devolverán (predeterminado 5, mínimo 1) |

### search_data_access

**Recurso:** API de acceso a datos · lotes con errores
**Estado:** activo

Acceda a archivos desde lotes de ingesta de datos de Experience Platform con errores. Use `failed_batch/list_failed` para enumerar los archivos que pertenecen a un lote erróneo para el diagnóstico de errores. Requiere un ID de lote para todas las operaciones. Nota: `file/get` y `dataset/preview` están deshabilitados ya que exponen datos de registro reales. Todas las operaciones son de solo lectura.

**Capacidades:** lista archivos de un lote de ingesta fallido

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `failed_batch` — lista de archivos de un lote de ingesta fallido |
| `operation` | Sí | `list_failed`: la única operación compatible |
| `resource_id` | Sí | ID de lote del lote fallido |
| `query_params.start` | No | Índice de inicio de paginación, p. ej. `1` |
| `query_params.limit` | No | Número de resultados por página; p. ej. `10` |
| `query_params.path` | No | Filtro de nombre de archivo completo, p. ej. `profiles.csv` |


### search_data_lake

**Recurso:** API de lago de datos · conjuntos de datos, lotes
**Estado:** activo

Inspeccione los metadatos por lotes y conjuntos de datos de la capa del lago de datos. Use `get` para metadatos completos, `get_size` para métricas de tamaño de ingesta y almacenamiento, y `list_failed` para supervisar errores de ingesta en un período de tiempo. Valores predeterminados de los últimos 7 días cuando no se proporciona ningún intervalo de tiempo para `list_failed`. Todas las operaciones son de solo lectura y requieren un ID de recurso.

**Capacidades:** obtiene metadatos por lotes/conjunto de datos, obtiene métricas de tamaño de almacenamiento y enumera lotes con errores en un intervalo de tiempo

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `dataset` o `batch` |
| `operation` | Sí | `get`, `get_size`, `list_failed`. `list_failed` solo admite `batch` tipo de entidad |
| `resource_id` | Sí | ID de conjunto de datos o ID de lote. Para `list_failed`: el ID del conjunto de datos para el ámbito falla al |
| `query_params.created_after` | No | Inicio de la ventana de tiempo. Marca de tiempo Unix en ms |
| `query_params.created_before` | No | Fin de la ventana de tiempo. Marca de tiempo Unix en ms |
| `query_params.limit` | No | Resultados máximos por página (máximo 100) |
| `query_params.order_by` | No | Dirección del orden, p. ej. `desc:created` |

### search_dule

**Recurso:** Control de datos · etiquetas, políticas, marketing_actions
**Estado:** activo

Consulte la API del servicio de directivas para ver las etiquetas de uso de datos, las directivas y las acciones de marketing. Use `marketing_action/evaluate` para comprobar si una acción de marketing en datos con etiquetas específicas infringe alguna directiva de gobernanza. Todas las operaciones son de solo lectura.

**Funciones:** enumerar/obtener etiquetas de uso de datos, enumerar/obtener directivas, enumerar directivas habilitadas, enumerar/obtener acciones de marketing, evaluar acciones de marketing contra etiquetas

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `label`, `policy` o `marketing_action` |
| `operation` | Sí | `list`, `get`, `list_enabled` (solo directiva), `evaluate` (solo marketing_action). `list_enabled` no requiere ámbito |
| `scope` | No | `core` (definido por Adobe) o `custom` (definido por org). Necesario para `list`, `get`, `evaluate`; no se usa para `list_enabled` |
| `resource_id` | No | Nombre de etiqueta, ID de política o nombre de acción de marketing. Necesario para `get` y `evaluate` |
| `query_params.dule_labels` | No | Etiquetas separadas por comas (p. ej. `C1,C3`). Necesario para `marketing_action/evaluate`; filtro opcional para `policy/list` |
| `query_params.limit` | No | Resultados máximos |
| `query_params.start` | No | Cursor de paginación a partir del valor `_page.next` de una respuesta anterior |
| `query_params.orderby` | No | Campos de ordenación separados por comas |
| `query_params.property_filter` | No | Expresión de filtro, p. ej. `name==C1` |
| `query_params.marketing_action` | No | Restringir la lista de directivas a las directivas que hacen referencia a esta acción de marketing (solo directiva/lista) |
| `query_params.include_draft` | No | Incluir directivas de BORRADOR en `marketing_action/evaluate` (predeterminado: solo directivas HABILITADAS) |

### search_query_service

**Recurso:** Servicio de consultas · consultas, plantillas, programaciones, ejecuciones de programación, conexiones, suscripciones de alerta
**Estado:** activo

Herramienta unificada para recursos del servicio de consultas. Mostrar y recuperar consultas Ad hoc, plantillas SQL guardadas, consultas programadas y sus ejecuciones, parámetros de conexión interactivos (para clientes psql/JDBC) y suscripciones de alertas. Para las listas de consulta, el valor predeterminado es `isService==false,isParentLevel==true` para filtrar el tráfico interno. Todas las operaciones son de solo lectura.

**Capacidades:** consultas list/get, plantillas list/get, programaciones list/get, ejecuciones list/get de programación, obtener parámetros de conexión, enumerar suscripciones de alerta

**Parámetros:**

| Parámetro | Requerido | Descripción |
| --- | --- | --- |
| `entity_type` | Sí | `query`, `query_template`, `schedule`, `schedule_run`, `connection`, `alert_subscription` |
| `operation` | Sí | `list`, `get`, `get_connection_params`, `list_by_u...` |
