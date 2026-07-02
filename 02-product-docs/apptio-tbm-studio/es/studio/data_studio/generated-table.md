---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Generar una tabla"
breadcrumb: []
source_path: "studio/data_studio/generated-table.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu604.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Generar una tabla

**Se aplica a** : TBM Studio 12.0 y posteriores

Para crear una nueva tabla a partir de una tabla existente en el proyecto actual, utilice la opción Tabla generada. La nueva tabla se vinculará a la tabla de origen.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu604.png)

## Conjunto de datos de origen

Seleccione un conjunto de datos de la lista.

## Columna de clave primaria

Seleccione la columna que servirá como clave primaria. La aplicación filtrará automáticamente las entradas de esta columna a entradas únicas. Por ejemplo, si hay dos filas para Smith en la tabla de origen, sólo habrá una fila en la tabla generada. Para mantener la integridad entre la tabla de origen y la tabla generada, seleccione una columna cuyos valores no cambiarán.

Si desea conservar las entradas duplicadas, cree una nueva columna en la tabla de origen que combine la columna de clave primaria con una segunda columna. Utilice la nueva columna como clave primaria en la tabla generada.

## Columnas a incluir

Marque las columnas que desea incluir en la tabla generada.

## Permitir la edición de columnas incluidas

Por lo general, las columnas incluidas en la tabla de origen son estáticas en la tabla generada. Si desea que los usuarios puedan editar las columnas incluidas en la tabla de origen, seleccione esta opción. Las columnas que serán editables normalmente se añaden a la tabla generada después de que ésta haya sido generada.
