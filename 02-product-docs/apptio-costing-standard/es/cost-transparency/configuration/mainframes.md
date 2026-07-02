---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Componente CT Apps - Mainframes"
breadcrumb: []
source_path: "cost-transparency/configuration/mainframes.html"
images:
  - "resources/images/ct_images/6863_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Componente CT Apps - Mainframes

l componente Mainframes forma parte del módulo Costing Standard Applications and Services. Se utiliza para comprender el TCO de los mainframes y asignar los costes del mainframe al objeto Aplicaciones.

Se aplica a: Costing Standard en TBM Studio 12.0 y posteriores

Icono de componente:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6863_1.png)

## Requisitos

Debe instalar los siguientes componentes de la aplicación Costing Standard Foundation antes de instalar el componente Mainframes:

- Fuente de costes
- Torres IT

## Cuadros de apoyo

Al instalar el componente CT Apps - Mainframes, se crea un nuevo grupo Dispositivos de usuario final con seis tablas:

- LPAR de Mainframe (tabla de modelos)
- Mainframe LPARs Datos maestros
- Almacenamiento Mainframe (tabla de modelos)
- Datos maestros de almacenamiento de mainframe
- Mainframes (tabla de modelos)
- Mainframes Datos maestros

## Datos maestros

Para obtener una descripción de los campos de las tablas de datos maestros, consulte la información de la página del componente CT Apps - Mainframes del producto. Para visualizar la página:

1. Haga clic en la pestaña **Proyecto** de la cinta de opciones.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **CT Apps - Mainframes**.

## Cargar los datos

Cargue los datos de sus mainframes. Los campos obligatorios y recomendados se enumeran a continuación por tabla maestra.

Mainframe LPARs Datos maestros

- ID de la solicitud (obligatorio)
- Nombre de la aplicación (obligatorio)
- LPAR (obligatorio) (LPAR: partición lógica)
- Mainframe (obligatorio)
- Identificador de objeto (obligatorio)

Datos maestros de almacenamiento de mainframe

- ID de la solicitud (obligatorio)
- Nombre de la aplicación (obligatorio)
- Identificador de objeto (obligatorio)
- ID de almacenamiento (obligatorio)

Mainframes Datos maestros

- Unidades reales (obligatorias)
- Capacidad de la CPU (recomendada)
- MIPS garantizado (recomendado)
- Ubicación (recomendada)

## Mapear los datos

Tras cargar los datos del mainframe, asigne la tabla a las tablas de datos maestros.

Después de asignar los datos, debe haber un valor asignado como se describe a continuación.

- LPARs de Mainframe - De Mainframes a LPARS de Mainframe, y de LPARS de Mainframe a Aplicaciones.
- Almacenamiento en mainframe: de las torres de recursos informáticos al almacenamiento en mainframe, y del almacenamiento en mainframe a las aplicaciones.
- Mainframes - De las torres de recursos informáticos y los centros de datos a los mainframes, y de los mainframes a los LPARS.
