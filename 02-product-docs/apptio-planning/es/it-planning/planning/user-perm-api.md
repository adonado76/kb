---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "API de permisos de usuario"
breadcrumb:
  - "Planning"
  - "Las API"
  - "Descripción general de la planificación de API REST"
source_path: "it-planning/planning/user-perm-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de permisos de usuario

**Las API de permisos de usuario** permiten exportar e importar datos de permisos a nivel de plan y globales. Estas API permiten la gestión automatizada del acceso y la validación de los permisos de los usuarios en « Apptio Planning».

Mediante estas API, puede gestionar permisos de forma masiva a través de archivos « CSV », revisar las configuraciones de acceso existentes y resolver problemas relacionados con los permisos utilizando los archivos de ayuda detallados que se generan durante las operaciones de importación.

## PUBLICACIÓN planning/api/v1/userpermissions/export

**Descripción**

Exporta los datos de permisos de usuario a nivel de plan. La exportación se genera como un archivo ` CSV ` según los parámetros proporcionados.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/userpermissions/export
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ). Utiliza la API GET de planes para obtener el ID del plan que deseas exportar.

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| planId | planID de la respuesta de la API de GET Plans | FALSE | El ID del plan cuyos permisos de usuario deben exportarse. Si no se especifica lo contrario, la exportación incluirá los permisos de datos de referencia globales. |
| basePercentage | ONE CIEN | FALSE | Formato en el que debe mostrarse el porcentaje. Valor predeterminado: UNO |
| characterEncoding | UTF\_8 SHIFT\_JIS | FALSE | Codificación del archivo de entrada Por defecto: UTF\_8 |
| columnDelimiter | COMA PUNTO Y COMA  TAB | FALSE | CSV delimitador Valor predeterminado: COMMA |
| dateFormat | *Formatos de fecha admitidos:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-mm-aa*  *yy/M/d*  *yy.M.d*  *dd-mm-aaaa*  *dd/mm/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *MM/dd/aa*  *MM.dd.yy*  *d-m-aaaa*  *d/m/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *d/m/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | FALSE | Formato de los campos de fecha en el archivo de importación. Predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO | FALSE | Número de decimales que se aplican a los valores numéricos Valor predeterminado: OCHO |
| decimalSymbol | PERÍODO COMA | FALSE | Separador de decimales Valor predeterminado: PERIOD |

**Respuesta**

Un archivo « CSV » descargable que contiene los detalles del análisis de variaciones del plan seleccionado.

## PUBLICACIÓN /planning/api/v1/userpermissions/import

**Descripción**

Importa los permisos de usuario a nivel de plan o los permisos globales de objetos de coste.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/userpermissions/import
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ). Utiliza la API GET de planes para obtener el ID del plan que deseas exportar.

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
| planId | planID de la respuesta de la API de GET Plans | FALSE | El ID del plan cuyos permisos de usuario deben importarse. Si no se especifica lo contrario, importar los permisos de los datos de referencia globales. |
| commitWithIssues | TRUE FALSE | FALSE | VERDADERO: carga el archivo « CSV » aunque haya errores. En la respuesta se incluyen los detalles del error. FALSO: impide que el archivo « CSV » se cargue si se detecta algún error.  Valor predeterminado: FALSE |
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
"totalRows": 0, 
"modifiedRows": 0, 
"omittedRows": 0, 
"additionalRows": 0, 
"updatedDepartments": -1, 
"hasChanges": false, 
"helpFileKey": null, 
"status": "CANCELLED", 
"issues": { 
"OMIT": [], 
"ADDITION": [], 
"MODIFY": [ {
"type": "uploadContainsUnknownColumn",
"isIncludedInHelpFile": false, 
"column": "unknownColumn", 
"count": 35, 
"errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
"instances": [ "Account", "Cost Center", "Project Code", "Cost Type", "Location", "Location Name", "Vendor", "Vendor Name", "Description", "Transaction ID"] 
} ], 
"CANCEL": [] }, 
"uploadId": "F74974DEB2974B7E94D3351C73CACD80", 
"totalIssues": 35, 
"_links": [ {
"href":"http://app.apptio.com/planning/api/v1/userpermissionsimportcommitWithIssues=true&planId=D7BAC53A969D49EE836DB41D51EB746&basePercentage=ONE&columnDelimiter=COMMA&dateFormat=yyy-MM-dd", 
"rel": "commitWithIssues", 
"method": "POST", 
"type": "multipart/form-data" 
} ] 
}
```

**Propiedades del objeto JSON de respuesta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propiedad** | **Tipo** | **Valores** | **Descripción** |
| comprometido | BOOLEAN | TRUE FALSE | VERDADERO: la subida del archivo se ha realizado correctamente. FALSO: el usuario puede continuar con la carga a través de commitWithIssue=TRUE o descargar el archivo de ayuda desde los enlaces adjuntos. |
| totalRows | NUMBER |  | Número total de filas del archivo de importación. |
| modifiedRows | NUMBER |  | Número de filas que se modificarán una vez que se haya procesado la carga. Las razones de las modificaciones en las filas se pueden consultar en issues.MODIFY, en la sección de respuestas. |
| omittedRows | NUMBER |  | Número de filas que se omitirán una vez que se haya procesado la carga. Las razones por las que se han omitido algunas filas se pueden consultar en issues.OMIT, en la sección de respuestas. |
| additionalRows | NUMBER |  | Número de filas que se añadirán una vez que se haya procesado la carga. Los motivos por los que se han añadido filas se pueden consultar en issues.ADDITION, en la respuesta. |
| hasChanges | BOOLEAN | TRUE FALSE | VERDADERO: si se producen cambios en las partidas individuales tras la carga.  FALSO en caso contrario. |
| helpFileKey | UUID |  | Identificador único del archivo de ayuda que contiene los problemas de carga |
| estado | SERIE | COMPLETADO CANCELADO | Estado de carga |
| issues.OMIT | MATRIZ | [Problemas](#upapi__upimpli) | Detalles de los problemas que provocaron la omisión de filas. |
| issues.ADDITION | MATRIZ | [Problemas](#upapi__upimpli) | Detalles de los problemas que provocaron la adición de filas. |
| issues.MODIFY | MATRIZ | [Problemas](#upapi__upimpli) | Detalles de los problemas que provocaron la modificación de las filas. |
| issues.CANCEL | MATRIZ | [Problemas](#upapi__upimpli) | Detalles de los problemas que provocaron la cancelación de la subida. |
| uploadId | UUID |  | Identificador único de la acción de importación. |
| totalIssues | NUMBER |  | Número total de números. |
| \_enlaces | MATRIZ | [Enlaces](#upapi__issues) | Se incluye cuando se producen errores de importación, proporcionando solicitudes de API de seguimiento para descargar el archivo de ayuda o volver a intentar la importación ignorando los problemas detectados. |

**Problemas**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Tipo** | **Valores** | **Descripción** |
| Tipo | SERIE | *Ejemplos de temas:* *noMatchingCostObjectCostCenterFound*  *invalidBuildCostType*  *illegalCostCenterCostObjectMappingreferenceNotFound*  *missingEmployee*  *UploadContainsUnknownColumn* | Identificador del tipo de error. |
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

## CONSÍGUELO EN /planning/api/v1/userpermissions/import/helpfile/<helpfileId>

**Descripción**

Descarga un archivo de ayuda con información detallada sobre los problemas que pueden surgir durante la carga de permisos.

Nota: Utiliza el objeto « helpFileId » de la respuesta de la API de importación

**Solicitud**

```
https://app.apptio.com/planning/api/v1/userpermissions/import/helpfile/%3ChelpfileId
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Parámetros**

|  |  |  |
| --- | --- | --- |
| **Nombre** | **Valor** | **Descripción** |
| nombre de archivo | <nombre del archivo de los datos exportados> | Si se configura, el nombre del archivo exportado sería « filename\_HelpFile.csv».  Si no se especifica, el nombre del archivo exportado será « helpfileid\_HelpFile.csv». |

**Respuesta**

Un archivo « CSV » descargable que incluye datos de importación de permisos de usuario y detalles integrados sobre los problemas de carga para cada fila afectada.

**Tema principal:** [Descripción general de la planificación de API REST](../../it-planning/planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.")
