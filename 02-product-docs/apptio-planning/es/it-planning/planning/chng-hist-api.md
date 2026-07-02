---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "API de historial de cambios"
breadcrumb:
  - "Planning"
  - "Las API"
  - "Descripción general de la planificación de API REST"
source_path: "it-planning/planning/chng-hist-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de historial de cambios

**Las API** de historial de cambios le permiten exportar datos del registro de eventos que recogen los cambios realizados en Apptio Planning.Change. Los datos del historial se exportan como un archivo CSV y pueden utilizarse para auditar las modificaciones de un plan específico, incluyendo **qué cambios se realizaron**, **quién los realizó** y **cuándo se produjeron**.

## PUBLICACIÓN /at/api/v1/planning/export

**Descripción**

Exporta los registros de eventos del historial de cambios a un archivo. CSV según los filtros seleccionados, como el intervalo de fechas, el nombre de usuario, el contenedor, etc.

**Solicitud**

```
POST https://app.apptio.com/at/api/v1/planning/export
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com )

**Cabeceras**

|  |  |  |
| --- | --- | --- |
| **Cabecera** | **Valor** | **Descripción** |
| apptio-opentoken | <open-token> | Token de autenticación generado en el paso 2 de los requisitos previos |
| apptio-entorno-actual | <identificador-del-entorno> | UUID del entorno requerido obtenido en el paso 3 de los requisitos previos |

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| startDate | aaaa-MM-dd aaaa/MM/dd  yyyy.MM.dd  yyyy-MM-ddThh:mm:ssZ | TRUE | Fecha de inicio para exportar los registros de eventos. Nota:  - Los valores que solo contienen la fecha se convierten al inicio del día (00:00:00 UTC). - Se rechazan los formatos ambiguos, como MM/dd/aaaa o dd/MM/aaaa, para evitar errores en los datos. |
| endDate | aaaa-MM-dddddd/MM/dd yyyy.MM.dd  yyyy-MM-ddThh:mm:ssZ | TRUE | Fecha de inicio para exportar los registros de eventos. Nota:  - Los valores que solo contienen la fecha se convierten al inicio del día (00:00:00 UTC). - Se rechazan los formatos ambiguos, como MM/dd/aaaa o dd/MM/aaaa, para evitar errores en los datos. |
| eventTypes | Matriz de cadenas | FALSE | Tipos de eventos por los que filtrar |
| userNames | Matriz de cadenas | FALSE | Nombres de usuario por los que filtrar |
| container |  | FALSE | Valor del contenedor por el que filtrar |
| elemento |  | FALSE | Valor del artículo por el que se va a filtrar |
| context |  | FALSE | Valor de contexto por el que filtrar |
| áreas | Matriz de cadenas | FALSE | Tipos de zonas por los que filtrar |
| itemTypes | Matriz de cadenas | FALSE | Tipos de artículos por los que filtrar |
| contextTypes | Matriz de cadenas | FALSE | Tipos de contexto por los que filtrar |

**Respuesta**

Un archivo « CSV » descargable que incluye los datos del registro de eventos correspondientes a los filtros seleccionados.

**Tema principal:** [Descripción general de la planificación de API REST](../../it-planning/planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.")
