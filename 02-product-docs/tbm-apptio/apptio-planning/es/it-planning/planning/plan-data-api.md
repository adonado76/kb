---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "API de planes"
breadcrumb:
  - "Planning"
  - "Las API"
  - "Descripción general de la planificación de API REST"
source_path: "it-planning/planning/plan-data-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de planes

**Las API de** planes te permiten consultar los planes disponibles y gestionar los datos de gastos a nivel de plan mediante operaciones de importación y exportación. Estas API constituyen la base de la mayoría de las integraciones de datos de planificación con « Apptio Planning».

Mediante las API de planes, puedes recuperar identificadores de planes, exportar datos detallados de gastos de distintos tipos de costes e importar datos actualizados de los planes mediante archivos « CSV ». Las opciones flexibles de formato y validación permiten flujos de trabajo repetibles, actualizaciones masivas y la integración con sistemas externos.

## CONSÍGUELO EN /planning/api/v1/plans

**Descripción**

Recupera los nombres y los identificadores de todos los planes a los que tiene acceso el usuario en el entorno indicado.

**Solicitud**

```
GET https://app.apptio.com/planning/api/v1/plans
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeceras**

|  |  |  |
| --- | --- | --- |
| **Cabecera** | **Valor** | **Descripción** |
| apptio-opentoken | <open-token> | Token de autenticación generado en el paso 2 de los requisitos previos |
| apptio-entorno-actual | <identificador-del-entorno> | Contexto de entorno requerido del paso 3 de los requisitos previos |

**Respuesta**

```
[ 
 { 
 "id": "0DD868B85BD445EFBDB9F20066F1C7CA", 
 "name": "FY2025 Budget" 
 }, 
 { 
 "id": "1841D23C513444B19B9F1743C5D90445", 
 "name": "FY2024 Budget Final" 
 }, 
 { 
 "id": "29A92951F2F94A5AB9D9556613A4CA6E", 
 "name": "FY2024 October Forecast" 
 } 
]
```

Devuelve un objeto JSON con las siguientes propiedades:

- ***id*** : Identificador único del plan
- ***nombre*** : Nombre que se muestra del plan

## Publicar /planning/api/v1/plans/< ID del plan >/gastos/exportar

**Descripción**

Exporta los datos de gastos de un plan concreto. La exportación se genera como un archivo ` CSV ` según los parámetros proporcionados.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/export
```

Nota: Utiliza la API GET de planes para obtener el ID del plan que deseas exportar

**Encabezados**

|  |  |  |
| --- | --- | --- |
| **Cabecera** | **Valor** | **Descripción** |
| apptio-opentoken | <open-token> | Token de autenticación generado en el paso 2 de los requisitos previos |
| apptio-entorno-actual | <identificador-del-entorno> | Entorno necesario según el paso 3 de los requisitos previos |

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| Tipo | RESUMEN  LABOR\_EXISTENTE  LABOR\_PLANIFICADO  ACTIVIDAD LABORAL  Contrato  ACTIVO\_EXISTENTE  ACTIVO\_PREVISTO  OTROS | TRUE | Tipo de datos del plan que se van a exportar |
| departmentCode | <code> o dejar en blanco | FALSE | Filtra los resultados por un departamento específico; si se deja en blanco, se exportan todos los departamentos |
| basePercentage | ONE  CIEN | FALSE | Determina cómo se formatean los valores porcentuales:  - 1 – Exporta los porcentajes como valores decimales. - CIEN – Expresa los porcentajes de las exportaciones en números enteros.   Valor predeterminado: UNO |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Codificación del archivo de salida Valor predeterminado: UTF\_8 |
| columnDelimiter | COMA PUNTO Y COMA  TAB | FALSE | CSV delimitador Valor predeterminado: COMMA |
| dateFormat | Formatos de fecha admitidos: aaaa-MM-dd  aaaa/MM/dd  yyyy.MM.dd  dd-mm-aa  dd/mm/aa  yy.MM.dd  dd-mm-aa  yy/M/d  yy.M.d  dd-mm-aaaa  dd/mm/aaaa  MM.dd.yyyy  dd-mm-aa  MM/dd/aa  MM.dd.yy  d-m-aaaa  d/m/aaaa  M.d.yyyy  dd-mm-aa  d/m/aa  M.d.yy  dd-MM-aaaa  dd/MM/aaaa  dd.MM.yyyy  dd-MM-aa  dd/MM/aa  dd.MM.yy  d-M-aa  d/M/aa  d.M.yy  d-M-aaaa  d/M/aaaa  d.M.yyyy | FALSE | Formato de los campos de fecha en la salida Valor predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO  QUINCE | FALSE | Número de decimales que se aplican a los valores numéricos Valor predeterminado: QUINCE |
| decimalSymbol | PERÍODO COMA | FALSE | Separador de decimales Valor predeterminado: PERIOD |
| laborDisplayType | equivalente a tiempo completo HOUR | FALSE | Este parámetro solo está disponible si el parámetro «type» es LABOR\_ACTIVITY  Valor predeterminado: HORA |
| isForReimport | TRUE FALSE | FALSE | Exporta los datos en un formato adecuado para volver a importarlos si se establece en TRUE  Valor predeterminado: FALSE |
| layoutId |  | FALSE | ID del diseño que se va a exportar |
| moneda | MONEDA\_ORIGINAL MONEDA\_DE\_LA\_EMPRESA | FALSE | Aplicable únicamente cuando la función «Multidivisa» está activada.  - ORIGINAL\_CURRENCY (por defecto): Exporta los datos financieros en la moneda especificada para cada partida. - COMPANY\_CURRENCY: Exporta los datos financieros en la moneda predeterminada de la empresa, con los valores convertidos automáticamente cuando sea necesario.   Valor por defecto: ORIGINAL\_CURRENCY |

**Respuesta**

Un archivo « CSV » descargable que contiene los detalles de los gastos del plan seleccionado. La exportación incluye el esquema completo del plan para el tipo de plan seleccionado.

Se produce un error de solicitud incorrecta al utilizar tanto **isForReimport** como **layoutId**. Estos dos parámetros no son compatibles entre sí, por lo que no se pueden utilizar al mismo tiempo.

## Publicar /planning/api/v1/plans/< Id del plan >/gastos/importar

**Descripción**

Importa datos de gastos de un plan específico mediante un archivo de entrada de « CSV ». Devuelve una respuesta JSON en la que se detalla si la carga se ha realizado correctamente o ha fallado, el número de departamentos actualizados, las filas añadidas, modificadas u omitidas, y cualquier problema que haya surgido durante la carga. La respuesta también incluye opciones para volver a intentar la carga sin tener en cuenta los problemas o para descargar un archivo de ayuda que permita analizar los problemas.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/import
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Encabezados**

|  |  |  |
| --- | --- | --- |
| **Cabecera** | **Valor** | **Descripción** |
| apptio-opentoken | <open-token> | Token de autenticación generado en el paso 2 de los requisitos previos |
| apptio-entorno-actual | <identificador-del-entorno> | Entorno necesario según el paso 3 de los requisitos previos |
| Tipo de contenido | multipart/form-data |  |

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| Tipo | RESUMEN LABOR\_EXISTENTE  LABOR\_PLANIFICADO  ACTIVIDAD LABORAL  Contrato  ACTIVO\_EXISTENTE  ACTIVO\_PREVISTO  OTROS | TRUE | Tipo de datos del plan que se van a importar |
| uploadOperationType | SUSTITUIR\_TODAS\_LAS\_LÍNEAS\_DE\_PEDIDO UPDATE | TRUE | Tipo de carga de datos:  - REPLACE\_ALL\_LINE\_ITEMS elimina todos los datos existentes y los sustituye por los datos del archivo cargado. - La opción «ACTUALIZAR» actualiza los datos existentes únicamente en las líneas cuyo código de partida coincida. |
| departmentCode | <code> o dejar en blanco | FALSE | El código de departamento para el que se deben importar los datos del plan. Valor predeterminado: déjelo en blanco para importar los datos a todos los departamentos. |
| commitWithIssues | TRUE FALSE | FALSE | VERDADERO: carga el archivo « CSV » aunque haya errores. Los detalles del error se incluyen en la respuesta. FALSO: impide que el archivo « CSV » se cargue si se detecta algún error.  Valor predeterminado: FALSE |
| externalItems | TRUE FALSE | FALSE | VERDADERO: se importan como partidas externas. Valor predeterminado: FALSE |
| basePercentage | ONE CIEN | FALSE | Determina cómo se formatean los valores porcentuales:  - 1 – Importa porcentajes como valores decimales. - CIEN – Importa porcentajes como números enteros.   Valor predeterminado: UNO |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Codificación del archivo de entrada Por defecto: UTF\_8 |
| columnDelimiter | COMA PUNTO Y COMA  TAB | FALSE | CSV delimitador Valor predeterminado: COMMA |
| dateFormat | *Formatos de fecha admitidos:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-mm-aa*  *yy/M/d*  *yy.M.d*  *dd-mm-aaaa*  *dd/mm/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *MM/dd/aa*  *MM.dd.yy*  *d-m-aaaa*  *d/m/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *d/m/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | FALSE | Formato de los campos de fecha en el archivo de importación. Predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO | FALSE | Número de decimales que se aplican a los valores numéricos Valor predeterminado: OCHO |
| decimalSymbol | PERÍODO COMA | FALSE | Separador de decimales Valor predeterminado: PERIOD |

**Cuerpo**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valor** | **Obligatorio** | **Descripción** |
| Archivo | <archivo CSV para importar> | TRUE | El archivo « CSV » que se va a importar |

**Respuesta**

```
{ 
  "committed": false, 
  "totalRows": 157, 
  "modifiedRows": 0, 
  "omittedRows": 157, 
  "additionalRows": 0, 
  "updatedCostObjects": 0, 
  "hasChanges": false, 
  "helpFileKey": "BAD29F5238994EFFBA9DB8204A1B4226", 
  "displayName": "Financials", 
  "status": "CANCELLED", 
  "issues": { 
    "OMIT": [ 
      { 
        "type": "noMatchingCostObjectCostCenterFound", 
        "isIncludedInHelpFile": true, 
        "column": "Cost Object", 
	        "count": 157, 
        "errorMessage": "No values found for Cost Object and Cost Center: Cost Object", 
        "instances": [] 
      }, 
      { 
        "type": "invalidBuildCostType", 
        "isIncludedInHelpFile": true, 
        "column": "Cost Type", 
        "count": 155, 
        "errorMessage": "One or more rows in uploaded lines has invalid Cost Type: Build, please include Project Code to consider Build Cost Type: Cost Type", 
        "instances": [] 
      } 
    ], 
    "ADDITION": [], 
    "MODIFY": [ 
      { 
        "type": " 
        ", 
        "isIncludedInHelpFile": false, 
        "column": "unknownColumn", 
        "count": 112, 
        "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
        "instances": [ 
          "Project: Invest Type", 
          "Project: Sponsor BU", 
          "Project: Initiative", 
          "Project: Priority", 
          "Project: Project Owner", 
          "Project: Project Group", 
          "Project: Code", 
          "Project Cost Center", 
          "Project Cost Center: Cost Center Owner", 
          "Project Cost Center: Cost Center Owner Title" 
        ] 
      }, 
      { 
        "type": "invalidPrefix", 
        "isIncludedInHelpFile": true, 
        "column": "Line Item Code", 
        "count": 157, 
        "errorMessage": "Invalid prefix format: Line Item Code", 
        "instances": [ 
          "LAP-156", 
          "LAP-2", 
          "LAP-95", 
          "LAP-133", 
          "LAP-132", 
          "LAP-150", 
          "LAP-115", 
          "LAP-33", 
          "LAP-141", 
          "LAP-6" 
        ] 
      } 
    ], 
    "CANCEL": [] 
  }, 
  "uploadId": "4361C20A391A4DA39AF61DD11655ACC8", 
  "totalIssues": 581, 
  "_links": [ 
    { 
      "href": "https://app.apptio.com/planning/api/v1/plans/C66E072F4E9745D29D541236FD28592A/expenses/import?type=SUMMARY&uploadOperationType=REPLACE_ALL_LINE_ITEMS&commitWithIssues=true&externalItems=false", 
      "rel": "commitWithIssues", 
      "method": "POST", 
      "type": "multipart/form-data" 
    }, 
    { 
      "href": "https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/BAD29F5238994EFFBA9DB8204A1B4226?filename=response-exportall-oas.csv", 
      "rel": "downloadHelpFile", 
      "method": "GET", 
      "type": "text/csv" 
    } 
  ]
```

La respuesta devuelve un objeto JSON con las siguientes propiedades:

**Propiedades del objeto JSON de la respuesta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propiedad** | **Tipo** | **Valores** | **Descripción** |
| comprometido | BOOLEAN | TRUE FALSE | VERDADERO: la subida del archivo se ha realizado correctamente. FALSO: el usuario puede continuar con la carga a través de commitWithIssue=TRUE o descargar el archivo de ayuda desde los [enlaces](#plndataapi__links). |
| totalRows | NUMBER |  | Número total de filas del archivo de importación. |
| modifiedRows | NUMBER |  | Número de filas que se modificarán una vez que se haya procesado la carga. Los motivos de las modificaciones en las filas se pueden consultar en issues.MODIFY, en la respuesta. |
| omittedRows | NUMBER |  | Número de filas que se omitirán una vez que se haya procesado la carga. Las razones por las que se han omitido algunas filas se pueden consultar en issues.OMIT, en la respuesta. |
| additionalRows | NUMBER |  | Número de filas que se añadirán una vez que se haya procesado la carga. Los motivos por los que se han añadido filas se pueden consultar en issues.ADDITION, en la respuesta. |
| updatedDepartments | NUMBER |  | Número de departamentos actualizados. |
| hasChanges | BOOLEAN | TRUE FALSE | VERDADERO: si se producen cambios en las partidas individuales tras la carga. FALSO en caso contrario. |
| helpFileKey | UUID |  | Identificador único del archivo de ayuda que contiene los problemas de carga |
| estado | SERIE | COMPLETADO CANCELADO | Estado de carga |
| issues.OMIT | MATRIZ | [Problemas](#plndataapi__issues) | Detalles de los problemas que provocaron la omisión de filas. |
| issues.ADDITION | MATRIZ | [Problemas](#plndataapi__issues) | Detalles de los problemas que provocaron la adición de filas. |
| issues.MODIFY | MATRIZ | [Problemas](#plndataapi__issues) | Detalles de los problemas que provocaron la modificación de las filas. |
| issues.CANCEL | MATRIZ | [Problemas](#plndataapi__issues) | Detalles de los problemas que provocaron la cancelación de la subida. |
| uploadId | UUID |  | Identificador único de la acción de importación. |
| totalIssues | NUMBER |  | Número total de números. |
| \_enlaces | MATRIZ | [Enlaces](#plndataapi__links) | Se incluye cuando se producen errores de importación, proporcionando solicitudes de API de seguimiento para descargar el archivo de ayuda o volver a intentar la importación ignorando los problemas detectados. |

**Problemas**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Tipo** | **Valores** | **Descripción** |
| Tipo | SERIE | Ejemplos de temas: noMatchingCostObjectCostCenterFound  invalidBuildCostType  illegalCostCenterCostObjectMapping  referenceNotFound  missingEmployee  uploadContainsUnknownColumn | Identificador del tipo de error. |
| isIncludedInHelpFile | BOOLEAN | TRUE FALSE | VERDADERO: los detalles del problema se incluyen en el archivo de ayuda FALSO: los detalles del problema no se incluyen en el archivo de ayuda |
| columna | SERIE |  | El nombre de la columna en la que se detectó el problema |
| errorMessage | SERIE |  | Detalles del asunto. |
| instancias | MATRIZ |  | Todas las apariciones del tipo de error especificado en el archivo de importación. Ejemplo: Si el tipo de problema es « uploadContainsUnknownColumn, », las instancias mostrarán todas las columnas desconocidas que se hayan encontrado en el archivo de importación. |

**Enlaces**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Tipo** | **Valores** | **Descripción** |
| href | SERIE |  | Punto final del recurso vinculado |
| rel | SERIE | commitWithIssues downloadHelpFile | commitWithIssue - Enlace para procesar la carga e ignorar los problemas detectados downloadHelpFile – enlace para descargar el archivo de ayuda con los detalles de los problemas |
| método | SERIE | GET POST  PUT  PATCH  SUPRIMIR | HTTP método que se debe utilizar para el enlace |
| Tipo | SERIE |  | Se espera un encabezado «Content-Type» en la solicitud |

## CONSÍGUELO EN /planning/api/v1/plans/expenses/import/helpfile/<helpfileid>

**Descripción**

Descarga un archivo de ayuda con información detallada sobre los problemas que se han producido durante la subida.

Nota: Utiliza el objeto « helpFileId » de la respuesta de la API de importación

**Solicitud**

```
GET https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/<helpfileid>
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Parámetros**

|  |  |  |
| --- | --- | --- |
| **Nombre** | **Valor** | **Descripción** |
| nombre de archivo | <nombre del archivo de los datos exportados> | Si se configura, el nombre del archivo exportado sería « filename\_HelpFile.csv». Si no se especifica, el nombre del archivo exportado será « helpfileid\_HelpFile.csv». |

**Respuesta**

Un archivo « CSV » descargable que incluye los datos de importación del plan y detalles integrados sobre los problemas de carga para cada fila afectada.

## PUBLICACIÓN /planning/api/v1/plans/<planId>/expenses/import/async

**Descripción**

Inicia una importación asíncrona de datos de gastos para un plan determinado mediante un archivo « CSV ». Devuelve una respuesta JSON que contiene un UUID único de la solicitud de importación y un enlace para consultar el estado y los resultados de la importación.

**Solicitud**

PUBLICACIÓN [https://app.apptio.com/planning/api/v1/plans/<planId>/expenses/import/async](https://app.apptio.com/planning/api/v1/plans/%3cplanId%3e/expenses/import/async "(se abre en una pestaña o una ventana nueva)")

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeceras**

|  |  |  |
| --- | --- | --- |
| **Cabecera** | **Valor** | **Descripción** |
| apptio-opentoken | <open-token> | Token de autenticación generado en el paso 2 de los requisitos previos |
| apptio-entorno-actual | <identificador-del-entorno> | Entorno necesario según el paso 3 de los requisitos previos |
| Tipo de contenido | multipart/form-data |  |

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| Tipo | RESUMEN LABOR\_EXISTENTE  LABOR\_PLANIFICADO  ACTIVIDAD LABORAL  Contrato  ACTIVO\_EXISTENTE  ACTIVO\_PREVISTO  OTROS | TRUE | Tipo de datos del plan que se van a importar |
| uploadOperationType | SUSTITUIR\_TODAS\_LAS\_LÍNEAS\_DE\_PEDIDO UPDATE | TRUE | Tipo de carga de datos:  - REPLACE\_ALL\_LINE\_ITEMS elimina todos los datos existentes y los sustituye por los datos del archivo cargado. - La opción «ACTUALIZAR» actualiza los datos existentes únicamente en las líneas cuyo código de partida coincida. |
| departmentCode | <code> o dejar en blanco | FALSE | El código de departamento para el que se deben importar los datos del plan. Valor predeterminado: déjelo en blanco para importar los datos a todos los departamentos. |
| commitWithIssues | TRUE FALSE | FALSE | VERDADERO: carga el archivo « CSV » aunque haya errores. Los detalles del error se incluyen en la respuesta. FALSO: impide que el archivo « CSV » se cargue si se detecta algún error.  Valor predeterminado: FALSE |
| externalItems | TRUE FALSE | FALSE | VERDADERO: se importan como partidas externas. Valor predeterminado: FALSE |
| basePercentage | ONE CIEN | FALSE | Determina cómo se formatean los valores porcentuales:  - 1 – Importa porcentajes como valores decimales. - CIEN – Importa porcentajes como números enteros.   Valor predeterminado: UNO |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Codificación del archivo de entrada Por defecto: UTF\_8 |
| columnDelimiter | COMA PUNTO Y COMA  TAB | FALSE | CSV delimitador Valor predeterminado: COMMA |
| dateFormat | *Formatos de fecha admitidos:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-mm-aa*  *yy/M/d*  *yy.M.d*  *dd-mm-aaaa*  *dd/mm/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *MM/dd/aa*  *MM.dd.yy*  *d-m-aaaa*  *d/m/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *d/m/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | FALSE | Formato de los campos de fecha en el archivo de importación. Predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO  ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO | FALSE | Número de decimales que se aplican a los valores numéricos Valor predeterminado: OCHO |
| decimalSymbol | PERÍODO COMA | FALSE | Separador de decimales Valor predeterminado: PERIOD |

**Cuerpo**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valor** | **Obligatorio** | **Descripción** |
| Archivo | <archivo CSV para importar> | TRUE | El archivo « CSV » que se va a importar |

**Respuesta**

```
{ 
      "importId": "11F160D23B68D2A697BDD658E768322C", 
      "_link": 
      { 
            "href":"https://app.apptio.com/planning/api/v1/plans/expenses/import/async/11F160D23B68D2A697BDD658E768322C", 
            "rel": "getStatus", "method": "GET", "type": "application/json"
      } 
}
```

**Propiedades del objeto JSON de la respuesta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propiedad** | **Tipo** | **Valores** | **Descripción** |
| importId | UUID |  | Identificador único generado para la solicitud de importación. |
| \_enlace |  | [enlace](#plndataapi__asynclink) | URL para consultar el estado y el resultado de la solicitud de importación. |

**Enlaces**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Tipo** | **Valores** | **Descripción** |
| href | SERIE |  | URL del recurso enlazado. del recurso enlazado |
| rel | SERIE | getStatus | Define la relación del enlace. Indica que este enlace se utiliza para consultar el estado y el resultado de la importación. |
| método | SERIE | GET POST  PUT  PATCH  SUPRIMIR | HTTP método que se debe utilizar al llamar al enlace. |
| Tipo | SERIE |  | Encabezado «Content-Type» esperado para la solicitud. |

**Errores**

|  |  |  |
| --- | --- | --- |
| 400 | Solicitud errónea | Falta un parámetro obligatorio, o ya se está realizando una importación para el plan especificado. |
| 403 | No autorizado | El usuario no está autorizado a realizar esta operación. |
| 404 | No encontrado | No se ha encontrado ningún plan ni departamento con el ID de plan facilitado. |

## CONSÍGUELO EN /planning/api/v1/plans/expenses/import/async/<importId>

**Descripción**

Recupera el estado actual de una solicitud de importación. Si la importación ha alcanzado un estado final ( **ÉXITO**, **ADVERTENCIA** o **FALLO** ), la respuesta también incluye los resultados de la importación y cualquier detalle relacionado.

**Solicitud**

[https://app.apptio.com/planning/api/v1/plans/expenses/import/async/%3CimportId%3E](https://app.apptio.com/planning/api/v1/plans/expenses/import/async/%3CimportId%3E "(se abre en una pestaña o una ventana nueva)")

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Cabeceras**

|  |  |  |
| --- | --- | --- |
| **Cabecera** | **Valor** | **Descripción** |
| apptio-opentoken | <open-token> | Token de autenticación generado en el paso 2 de los requisitos previos |
| apptio-entorno-actual | <identificador-del-entorno> | Entorno necesario según el paso 3 de los requisitos previos |
| Tipo de contenido | multipart/form-data |  |

**Respuesta**

```
{
  "importId": "11F160D23B68D2A697BDD658E768322C",
  "status": "FAIL",
  "result": {
    "committed": false,
    "totalRows": 2,
    "modifiedRows": 0,
    "omittedRows": 2,
    "additionalRows": 0,
    "updatedDepartments": 0,
    "hasChanges": false,
    "helpFileKey": "E7915BDAF037483994D6FABD7564E174",
    "status": "CANCELLED",
    "issues": {
      "OMIT": [
        {
          "type": "noMatchingCostObjectCostCenterFound",
          "isIncludedInHelpFile": true,
          "column": "Cost Object",
          "count": 2,
          "errorMessage": "No values found for Cost Object and Cost Center: Cost Object",
          "instances": []
        }
      ],
      "ADDITION": [],
      "MODIFY": [
        {
          "type": "uploadContainsUnknownColumn",
          "isIncludedInHelpFile": false,
          "column": "unknownColumn",
          "count": 16,
          "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column",
          "instances": [
            "Event ID",
            "Timestamp",
            "User ID",
            "Event Type",
            "Container ID",
            "Area",
            "Container",
            "Item ID",
            "Item Type",
            "Item"
          ]
        }
      ],
      "CANCEL": []
    },
    "uploadId": "14B68FF8F91E412185D04B1CD52BA323",
    "totalIssues": 18
    "_links": [ { "href": "https://app.apptio.com/planning/api/v1/plans/E581EDF2752C434AAF62A63DF4F4B777/expenses/import/async?commitWithIssues=true&basePercentage=ONE&characterEncoding=UTF_8&columnDelimiter=COMMA&dateFormat=yyyy-MM-dd&decimalPrecision=EIGHT&decimalSymbol=PERIOD&type=SUMMARY&departmentCode=AllDept_6DC740A85A9C11E69E6CCC52AF3F6215&externalItems=false&uploadOperationType=UPDATE", 
    "rel": "commitWithIssues", 
    "method": "POST", 
    "type": "multipart/form-data" 
    }, 
    { 
        "href":"https://app.apptio.com/planning/api/v1/plans/expenses/import/helpfile/E7915BDAF037483994D6FABD7564E174?filename=response-export-filter.csv", 
        "rel": "downloadHelpFile", 
        "method": "GET", 
        "type": "text/csv" 
        } 
     ] 
  } 
}
```

**Propiedades del objeto JSON de la respuesta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propiedad** | **Tipo** | **Valores** | **Descripción** |
| importId | UUID |  | Identificador único generado para la solicitud de importación. |
| estado | SERIE | EN COLA EN EJECUCIÓN  CORRECTO  AVISO  ERROR | Estado actual de la solicitud de importación. |
| Resultado | Objeto JSON | [Respuesta de la API del plan](#plndataapi__importjson) | Contiene el resultado de la importación cuando la solicitud alcanza un estado definitivo (ÉXITO, ADVERTENCIA o FALLO). Devuelve «null» mientras la solicitud aún está en curso (QUEUED o RUNNING). |

**Errores**

|  |  |  |
| --- | --- | --- |
| 403 | No autorizado | El usuario no está autorizado a acceder a la importación solicitada. |
| 404 | No encontrado | No se ha encontrado ninguna solicitud de importación con el ID « <importId> » para el usuario <user>. |

**Tema principal:** [Descripción general de la planificación de las API REST](../../it-planning/planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.")
