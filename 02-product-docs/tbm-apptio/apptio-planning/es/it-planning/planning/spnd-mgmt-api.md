---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "API de gestión de gastos"
breadcrumb:
  - "Planning"
  - "Las API"
  - "Descripción general de la planificación de API REST"
source_path: "it-planning/planning/spnd-mgmt-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de gestión de gastos

**Las API de gestión del** gasto permiten exportar e importar datos reales que se utilizan en la planificación y el análisis financiero.

Puede exportar datos reales correspondientes a períodos y años concretos, o importar actualizaciones de datos reales mediante archivos « CSV » estructurados. Las operaciones de importación incluyen una validación exhaustiva, la notificación de errores y la generación de archivos de ayuda para facilitar la corrección de los problemas relacionados con los datos.

## PUBLICACIÓN planning/api/v1/spendmanagement/export

**Descripción**

Datos reales de exportaciones procedentes de la gestión del gasto. La exportación se genera como un archivo ` CSV ` según los parámetros proporcionados.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/spendmanagement/export
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Parámetros**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| código de departamento |  | FALSE | Código del departamento para el que se van a exportar los datos de gestión del gasto  Por defecto: Todos los departamentos |
| periodo | 1  2  3  4  5  6  7  8  9  10  5  6  13 | TRUE | Mes o período para el que se van a exportar los datos de gestión del gasto |
| año |  | TRUE | Año para el que se van a exportar los datos de gestión del gasto |
| basePercentage | ONE  CIEN | FALSE | Determina cómo se formatean los valores porcentuales:   - 1 – Importa porcentajes como valores decimales. - CIEN – Importa porcentajes como números enteros.   Valor predeterminado: UNO |
| characterEncoding | UTF\_8  SHIFT\_JIS | FALSE | Codificación del archivo de entrada  Por defecto: UTF\_8 |
| columnDelimiter | COMA  PUNTO Y COMA  TAB | FALSE | CSV delimitador  Valor predeterminado: COMMA |
| dateFormat | *Formatos de fecha admitidos:* *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-mm-aa*  *yy/M/d*  *yy.M.d*  *dd-mm-aaaa*  *dd/mm/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *MM/dd/aa*  *MM.dd.yy*  *d-m-aaaa*  *d/m/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *d/m/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | FALSE | Formato de los campos de fecha en el archivo de importación.  Predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO  ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO | FALSE | Número de decimales que se aplican a los valores numéricos  Valor predeterminado: OCHO |
| decimalSymbol | PERÍODO  COMA | FALSE | Separador de decimales  Valor predeterminado: PERIOD |

**Respuesta**

Un archivo « CSV » descargable que contiene los detalles del análisis de variaciones del plan seleccionado.

## PUBLICACIÓN /planning/api/v1/spendmanagement/import

**Descripción**

Importa los datos reales a Spend Management mediante un archivo de entrada de formato « CSV ». Devuelve una respuesta JSON que indica si la carga se ha realizado correctamente o ha fallado. La respuesta también incluye opciones para descargar un archivo de ayuda para el análisis del problema.

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/spendmanagement/import
```

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
| periodo | 1  2  3  4  5  6  7  8  9  10  5  6  13 | TRUE | Mes o período para el que se van a exportar los datos de gestión del gasto |
| año |  | TRUE | Año para el que se van a exportar los datos de gestión del gasto |
| commitWithIssues | TRUE  FALSE | FALSE | VERDADERO: carga el archivo « CSV » aunque haya errores. Los detalles del error se incluyen en la respuesta.  FALSO: impide que el archivo « CSV » se cargue si se detecta algún error.  Valor predeterminado: FALSE |
| uploadOperationType | SUSTITUIR\_TODAS\_LAS\_LÍNEAS\_DE\_PEDIDO  UPDATE | TRUE | Tipo de carga que se va a realizar |
| basePercentage | ONE  CIEN | FALSE | Determina cómo se formatean los valores porcentuales:   - 1 – Importa porcentajes como valores decimales. - CIEN – Importa porcentajes como números enteros.   Valor predeterminado: UNO |
| characterEncoding | UTF\_8  SHIFT\_JIS | FALSE | Codificación del archivo de entrada  Por defecto: UTF\_8 |
| columnDelimiter | COMA  PUNTO Y COMA  TAB | FALSE | CSV delimitador  Valor predeterminado: COMMA |
| dateFormat | *Formatos de fecha admitidos:*  *aaaa-MM-dd*  *aaaa/MM/dd*  *yyyy.MM.dd*  *dd-mm-aa*  *dd/mm/aa*  *yy.MM.dd*  *dd-mm-aa*  *yy/M/d*  *yy.M.d*  *dd-mm-aaaa*  *dd/mm/aaaa*  *MM.dd.yyyy*  *dd-mm-aa*  *MM/dd/aa*  *MM.dd.yy*  *d-m-aaaa*  *d/m/aaaa*  *M.d.yyyy*  *dd-mm-aa*  *d/m/aa*  *M.d.yy*  *dd-MM-aaaa*  *dd/MM/aaaa*  *dd.MM.yyyy*  *dd-MM-aa*  *dd/MM/aa*  *dd.MM.yy*  *d-M-aa*  *d/M/aa*  *d.M.yy*  *d-M-aaaa*  *d/M/aaaa*  *d.M.yyyy* | FALSE | Formato de los campos de fecha en el archivo de importación.  Predeterminado: aaaa-MM-dd |
| decimalPrecision | CERO  ONE  TWO  THREE  FOUR  Cinco  SEIS  SIETE  OCHO | FALSE | Número de decimales que se aplican a los valores numéricos  Valor predeterminado: OCHO |
| decimalSymbol | PERÍODO  COMA | FALSE | Separador de decimales  Valor predeterminado: PERIOD |

**Cuerpo**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Valores permitidos** | **Obligatorio** | **Descripción** |
| Archivo |  | TRUE | Archivo que se va a subir |

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
			  "MODIFY": [ 	
				  { "type": "uploadContainsUnknownColumn",
 				   "isIncludedInHelpFile": false, 
				    "column": "unknownColumn", 
				    "count": 35, "errorMessage": "Uploaded file contains one or more unknown columns which will be ignored: unknown column", 
				    "instances": [ 
						"Account", 
						"Cost Center", 
						"Project Code", 
						"Cost Type", 
						"Location", 
						"Location Name", 
						"Vendor", 
						"Vendor Name", 
						"Description", 
						"Transaction ID" 
						] 
				   } 
			   ], 
			    "CANCEL": [] 
}, 
"uploadId": "F74974DEB2974B7E94D3351C73CACD80", 
"totalIssues": 35, 
"_links": [ 
		 { 
		 "href":"http://app.apptio.com/planning/api/v1/spendmanagement/importcommitWithIssues=true&planId=D7BAC53A969D49EE836DB41D51FEB746&basePercentage=ONE&columnDelimiter=COMMA&dateFormat=yyyy-MM-dd", 	
		 "rel": "commitWithIssues", "method": "POST", "type": "multipart/form-data" 
		 } 
	    ] 
}
```

Devuelve un objeto JSON con las siguientes propiedades:

**Propiedades del objeto JSON de respuesta**

|  |  |  |  |
| --- | --- | --- | --- |
| **Propiedad** | **Tipo** | **Valores** | **Descripción** |
| comprometido | BOOLEAN | TRUE  FALSE | VERDADERO: la subida del archivo se ha realizado correctamente.  FALSO: el usuario puede continuar con la subida a través de commitWithIssue=TRUE o descargar el archivo de ayuda desde la sección «[Enlaces](#spdmgmapi__link) ». |
| totalRows | NUMBER |  | Número total de filas del archivo de importación. |
| modifiedRows | NUMBER |  | Número de filas que se modificarán una vez que se haya procesado la carga.  Las razones de las modificaciones en las filas se pueden consultar en issues.MODIFY, en la sección de respuestas. |
| omittedRows | NUMBER |  | Número de filas que se omitirán una vez que se haya procesado la carga.  Las razones por las que se han omitido algunas filas se pueden consultar en issues.OMIT, en la respuesta. |
| additionalRows | NUMBER |  | Número de filas que se añadirán una vez que se haya procesado la carga.  Los motivos por los que se han añadido filas se pueden consultar en issues.ADDITION, en la respuesta. |
| hasChanges | BOOLEAN | TRUE  FALSE | VERDADERO: si se producen cambios en las partidas individuales tras la carga.  FALSO en caso contrario. |
| helpFileKey | UUID |  | Identificador único del archivo de ayuda que contiene los problemas de carga |
| estado | SERIE | COMPLETADO  CANCELADO | Estado de carga |
| issues.OMIT | MATRIZ | [Problemas](#spdmgmapi__is) | Detalles de los problemas que provocaron la omisión de filas. |
| issues.ADDITION | MATRIZ | [Problemas](#spdmgmapi__is) | Detalles de los problemas que provocaron la adición de filas. |
| issues.MODIFY | MATRIZ | [Problemas](#spdmgmapi__is) | Detalles de los problemas que provocaron la modificación de las filas. |
| issues.CANCEL | MATRIZ | [Problemas](#spdmgmapi__is) | Detalles de los problemas que provocaron la cancelación de la subida. |
| uploadId | UUID |  | Identificador único de la acción de importación. |
| totalIssues | NUMBER |  | Número total de números. |
| \_enlaces | MATRIZ | [Enlaces](#spdmgmapi__link) | Se incluye cuando se producen errores de importación, proporcionando solicitudes de API de seguimiento para descargar el archivo de ayuda o volver a intentar la importación ignorando los problemas detectados. |

**Problemas**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Tipo** | **Valores** | **Descripción** |
| Tipo | SERIE | Ejemplos de temas: noMatchingCostObjectCostCenterFound  invalidBuildCostType  illegalCostCenterCostObjectMapping  referenceNotFound  missingEmployee  uploadContainsUnknownColumn | Identificador del tipo de error. |
| isIncludedInHelpFile | BOOLEAN | TRUE  FALSE | VERDADERO: los detalles del problema se incluyen en el archivo de ayuda  FALSO: los detalles del problema no se incluyen en el archivo de ayuda |
| columna | SERIE |  | El nombre de la columna en la que se detectó el problema |
| errorMessage | SERIE |  | Detalles del asunto. |
| instancias | MATRIZ |  | Todas las apariciones del tipo de error especificado en el archivo de importación.    Ejemplo: Si el **tipo** de incidencia es **«uploadContainsUnknownColumn»**, las **instancias** mostrarán todas las columnas desconocidas encontradas en el archivo de importación.  ``` "instances": [ "Project: Invest Type",  "Project: Sponsor BU",  "Project: Initiative", "Project: Priority", "Project: Project Owner",  "Project: Project Group",  "Project: Code", "Project Cost Center",  "Project Cost Center: Cost Center Owner", "Project Cost Center: Cost Center Owner Title"  ] ``` |

**Enlaces**

|  |  |  |  |
| --- | --- | --- | --- |
| **Nombre** | **Tipo** | **Valores** | **Descripción** |
| href | SERIE |  | Punto final del recurso vinculado |
| rel | SERIE | commitWithIssues downloadHelpFile | commitWithIssue - Enlace para procesar la carga e ignorar los problemas detectados  downloadHelpFile – enlace para descargar el archivo de ayuda con los detalles de los problemas |
| método | SERIE | GET  POST  PUT  PATCH  SUPRIMIR | HTTP método que se debe utilizar para el enlace |
| Tipo | SERIE |  | Se espera un encabezado «Content-Type» en la solicitud |

## CONSÍGUELO EN /planning/api/v1/plans/expenses/import/helpfile/<helpfileid>

**Descripción**

Descarga un archivo de ayuda con información detallada sobre los problemas que se han producido durante la subida.

Nota: Utiliza el objeto « helpFileId » de la respuesta de la API de importación

**Solicitud**

```
GET https://app.apptio.com/planning/api/v1/spendmanagement/import/helpfile/%3Chelpfileid%3E>
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

**Parámetros**

|  |  |  |
| --- | --- | --- |
| **Nombre** | **Valor** | **Descripción** |
| nombre de archivo | <nombre del archivo de los datos exportados> | Si se configura, el nombre del archivo exportado sería « filename\_HelpFile.csv».  Si no se especifica, el nombre del archivo exportado será « helpfileid\_HelpFile.csv». |

**Respuesta**

Un archivo « CSV » descargable que incluye datos de importación de permisos de usuario y detalles integrados sobre los problemas de carga para cada fila afectada.

**Tema principal:** [Descripción general de la planificación de las API REST](../../it-planning/planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.")
