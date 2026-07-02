---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "API de análisis de varianza"
breadcrumb:
  - "Planning"
  - "Las API"
  - "Descripción general de la planificación de API REST"
source_path: "it-planning/planning/variance-analysis-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de análisis de varianza

**Las API** de análisis de desviaciones permiten exportar de forma programática los datos de análisis de desviaciones de un plan concreto.

Las exportaciones se guardan como archivos de formato « CSV » y admiten parámetros opcionales para controlar el formato, el filtrado y la estructura de salida, lo que hace que los datos sean aptos para herramientas de análisis y visualización posteriores.

## PUBLICACIÓN /planning/api/v1/plans/<planId>/varianceanalysis/export

**Descripción**

Exporta los datos del análisis de variaciones de un plan concreto. La exportación se genera como un archivo ` CSV ` según los parámetros proporcionados.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/varianceanalysis/export>
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ). Utiliza la API GET de planes para obtener el ID del plan que deseas exportar.

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| departmentCode | <code> o dejar en blanco | FALSE | El código de departamento para el que se deben exportar los datos del análisis de desviaciones. Predeterminado: déjelo en blanco para exportar los datos a todos los departamentos. |
| basePercentage | ONE CIEN | FALSE | Formato en el que debe mostrarse el porcentaje. Valor predeterminado: UNO |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Codificación del archivo de entrada Por defecto: UTF\_8 |
| columnDelimiter | COMA PUNTO Y COMA  TAB | FALSE | CSV delimitador Valor predeterminado: COMMA |
| dateFormat | *Formatos de fecha admitidos:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-mm-aa*  *yy/M/d*  *yy.M.d*  *dd-mm-aaaa*  *dd/mm/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *MM/dd/aa*  *MM.dd.yy*  *d-m-aaaa*  *d/m/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *d/m/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | FALSE | Formato de los campos de fecha en el archivo de importación. Predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO | FALSE | Número de decimales que se aplican a los valores numéricos Valor predeterminado: OCHO |
| decimalSymbol | PERÍODO COMA | FALSE | Separador de decimales Valor predeterminado: PERIOD |

**Respuesta**

Un archivo « CSV » descargable que contiene los detalles del análisis de variaciones del plan seleccionado.

## Errores

|  |  |
| --- | --- |
| **Código** | **Significado** |
| 400 | Solicitud errónea |
| 403 | No autorizado |

**Tema principal:** [Descripción general de la planificación de API REST](../../it-planning/planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.")
