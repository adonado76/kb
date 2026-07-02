---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "API de diseño de tablas"
breadcrumb:
  - "Planning"
  - "Las API"
  - "Descripción general de la planificación de API REST"
source_path: "it-planning/planning/tab-lay-api.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# API de diseño de tablas

**La API de diseños de tablas** permite acceder a los metadatos de diseño que se utilizan para mostrar y organizar los datos de gastos en la planificación de « Apptio ». Los esquemas definen cómo se estructuran y presentan los datos del plan en los distintos tipos de gastos.

Esta API permite recuperar tanto los diseños públicos como los privados visibles para el usuario autenticado, lo que facilita integraciones que se basan en definiciones de esquema coherentes o en exportaciones e importaciones que tienen en cuenta los diseños.

## CONSÍGUELO EN /planning/api/v1/layouts

**Descripción**

Obtiene todas las plantillas (públicas y privadas) visibles para cada usuario para un tipo de gasto específico

**Solicitud**

```
POST https://app.apptio.com/planning/api/v1/layouts
```

Nota: Asegúrate de que la dirección URL coincida con tu región (por ejemplo, app-eu.apptio.com, app-au.apptio.com ).

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
| Tipo | RESUMEN  LABOR\_EXISTENTE  LABOR\_PLANIFICADO  ACTIVIDAD LABORAL  Contrato  ACTIVO\_EXISTENTE  ACTIVO\_PREVISTO  OTROS | TRUE | Tipo de gasto para obtener diseños |

**Respuesta**

```
[ 
		{ 
			"id": "_DEFAULT_VIEW_", 	
			"name": "Default Layout", 
			"isShared": true 	 
		}, 
		{ 	"id": "MyLayout", 
			  "name": "My Layout", 	
			  "isShared": false 
		}
	]
```

Devuelve un objeto JSON con las siguientes propiedades:

- ***id*** : Identificador único del diseño
- ***nombre*** : Nombre que se muestra del diseño
- **isShared** : true si el diseño es público, false si es privado

**Tema principal:** [Descripción general de la planificación de API REST](../../it-planning/planning/plan-api.html "Las API REST de planificación de « Apptio » proporcionan un acceso seguro y programático a los planes, los datos de planificación, los metadatos y los elementos relacionados dentro de « Apptio Planning». Estas API están diseñadas para facilitar la automatización y las integraciones de sistemas en casos de uso relacionados con la planificación, la previsión, el análisis, la gobernanza y el intercambio de datos.")
