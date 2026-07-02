---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "API de estado de planes"
breadcrumb:
  - "Planning"
  - "Las API"
  - "Descripción general de la planificación de API REST"
source_path: "it-planning/planning/pln-status-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de estado de planes

**Las API de estado** de los planes te permiten exportar información sobre la aprobación y el estado de los planes. Estas API se utilizan habitualmente con fines de gobernanza, auditoría y elaboración de informes para conocer el ciclo de vida y el estado de aprobación de los planes.

Los datos sobre el estado del plan se exportan como un archivo « CSV » y pueden utilizarse para realizar un seguimiento del progreso, identificar cuellos de botella o respaldar los procesos de supervisión a lo largo de los ciclos de planificación.

## PUBLICACIÓN /planning/api/v1/plans/<planId>/status/export

**Descripción**

Datos sobre el estado de aprobación de los planes de exportación. La exportación se genera como un archivo ` CSV ` según los parámetros proporcionados.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/status/export
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ). Utiliza la API GET de planes para obtener el ID del plan que deseas exportar.

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| basePercentage | ONE CIEN | FALSE | Formato en el que debe mostrarse el porcentaje. Valor predeterminado: UNO |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Codificación del archivo de entrada Por defecto: UTF\_8 |
| columnDelimiter | COMA PUNTO Y COMA  TAB | FALSE | CSV delimitador Valor predeterminado: COMMA |
| dateFormat | *Formatos de fecha admitidos:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-mm-aa*  *yy/M/d*  *yy.M.d*  *dd-mm-aaaa*  *dd/mm/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *MM/dd/aa*  *MM.dd.yy*  *d-m-aaaa*  *d/m/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *d/m/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | FALSE | Formato de los campos de fecha en el archivo de importación. Predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO  ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO | FALSE | Número de decimales que se aplican a los valores numéricos Valor predeterminado: OCHO |
| decimalSymbol | PERÍODO COMA | FALSE | Separador de decimales Valor predeterminado: PERIOD |

**Respuesta**

Un archivo « CSV » descargable que contiene los detalles del estado del plan seleccionado.

**Tema principal:** [Descripción general de la planificación de API REST](../../it-planning/planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.")
