---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Clasificar"
breadcrumb: []
source_path: "studio/data_studio/sort.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Clasificar

Ordena una tabla en una o más columnas especificadas de la tabla. Puede ordenar una tabla utilizando la cinta de opciones. ¡El!La función SORT puede aplicarse utilizando una, dos o más columnas de una tabla.

## Sintaxis

`!SORT[Column1|asc or desc,Column2|asc or desc]`

## Argumentos

Columna 1
:   El nombre de la primera columna que se utilizará para ordenar la tabla.
:   asc o desc
:   asc = ascendente
:   desc = descendente

Column2
:   El nombre de la segunda columna que se utilizará para ordenar la tabla.

## Ejemplo

Suponga que tiene la siguiente tabla.

![Ejemplo](../../resources/images/it%20planning_images/sort-1.png)

Desea ordenar la tabla por Servicio y, a continuación, por Subservicio. Modifique la ruta de datos como se muestra a continuación.

```
docs.org:ABC Company/
Reports/
.DateGoesHere/
.Summary/
!SORT[{Service}|asc,{SubService}|asc]
```

El resultado se muestra a continuación.

![Resultado](../../resources/images/it%20planning_images/sort-2.png)

## Cinta

Puede ordenar una tabla utilizando la **cinta de opciones** :

1. Seleccione la tabla que desea ordenar
2. Seleccione el icono **Ordenar** de la pestaña **Datos** de la **cinta de opciones**.
3. Rellene los campos y haga clic en **Ordenar**.

Para obtener más información sobre cómo ordenar una tabla desde la **cinta de opciones**, consulte Ordenar filas de una tabla en la Guía del usuario de Apptio Studio.

**Tema principal:** [Tablas editables: Adaptación a las entradas del usuario](../../studio/data_studio/editabletables.html "Se aplica a: TBM Studio 12.6 y posteriores")
