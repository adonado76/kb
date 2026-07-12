---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Sustituir función"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Fórmulas y funciones"
source_path: "studio/formulas-and-functions/functions/replace.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sustituir función

Sustituye los valores de una tabla basándose en las correspondencias de otra tabla de consulta. La función coincide en las columnas clave y asigna nuevos valores de las columnas especificadas en la tabla de sustitución. Todos los valores se tratan como cadenas.

La función Reemplazar se utiliza para reemplazar valores de una columna de una tabla de transformación por valores de una tabla de búsqueda y reemplazo. La función se introduce en el campo **Anulación de valor** de una columna de una tabla de transformación. Los valores de sustitución se introducen en una tabla search\_and\_replace (conjunto de datos). Las entradas de la tabla search\_and\_replace se ejecutan secuencialmente desde la parte superior de la tabla hasta la parte inferior. Las sustituciones basadas en las primeras filas de la tabla pueden sobrescribirse con sustituciones en las últimas filas. Todos los valores se tratan como cadenas.

## Sintaxis

`=Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)`

## Argumentos

*transform\_table\_column1, 2,...*

Los nombres de las columnas de la tabla que se utilizarán para identificar de forma exclusiva cada fila de la tabla. También deben incluirse las columnas con valores que serán sustituidos.

*tabla search\_and\_replace*

El nombre de la tabla que suministrará los valores de sustitución.

*match\_column1, 2,...*

Las columnas de la tabla de búsqueda y sustitución que coinciden con las columnas de la tabla de transformación. Pueden tener nombres diferentes, pero para cada columna de la tabla de transformación debe haber una columna coincidente en la tabla de búsqueda y sustitución.

*new\_column1, 2,...*

Los nombres de las columnas de la tabla search\_and\_replace que se utilizarán para proporcionar los nuevos valores.

*reemplazar\_tabla\_columna*

La columna de la tabla search\_and\_replace que proporcionará el nuevo valor.

## Ejemplo

Suponga que tiene la siguiente tabla de transformación:

| Departamento | Ubicación | Nº Propuesta |
| --- | --- | --- |
| Ventas | Seattle | 001 |
| Marketing | Seattle | 002 |
| Investigación | Chicago | 003 |
| Desarrollo | Chicago | 004 |
| Distribución | Denver | 005 |

Desea cambiar los ID añadiendo una D delante de cada ID. Para garantizar un identificador único, cree una nueva tabla (conjunto de datos) denominada **Tabla de búsqueda y sustitución** (véase el ejemplo a continuación):

| Departamento | Nº Propuesta | Nuevo\_Departamento | Nuevo\_ID |
| --- | --- | --- | --- |
| Ventas | 001 | Ventas | D001 |
| Marketing | 002 | Marketing | D002 |
| Investigación | 003 | Investigación | D003 |
| Desarrollo | 004 | Desarrollo | D004 |
| Distribución | 005 | Distribución | D005 |

Abra la tabla de transformación en la aplicación e introduzca lo siguiente en el campo **Anulación de valor** para la columna ID:

```
=Replace((Dept,ID),Search_and_Replace_Table,(Dept,ID),(New_Dept,
New_ID),New_ID)
```
