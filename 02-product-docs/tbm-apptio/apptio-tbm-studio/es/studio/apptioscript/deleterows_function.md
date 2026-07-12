---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "DeleteRows función"
breadcrumb: []
source_path: "studio/apptioscript/deleterows_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DeleteRows función

Utilice la función DeleteRows( ) para eliminar una fila de tabla existente basándose en los valores de las columnas designadas.

## Sintaxis

Nota: Si ejecuta este script en una vista filtrada de una tabla, sólo las filas filtradas se verán afectadas por la ejecución del script de eliminación de filas.

```
DeleteRows( date, tableName[columName1="value" OPERAND columName2="value" ...])
```

## fecha

Determina la fecha para modificar el conjunto de datos. Para obtener una lista de formatos de fecha válidos, consulte [DateFormat function](../formulas-and-functions/functions/dateformat.htm "(se abre en una pestaña o una ventana nueva)")

## tableName

El nombre del conjunto de datos, indicado por el nombre de una tabla.

## columnName

El nombre de una columna de la tabla anotada en tableName.

## valor

El valor de la fila a eliminar.

## operando

Los operandos válidos son AND y OR.

## Ejemplo 1

Este ejemplo elimina todas las filas del conjunto de datos BuList para la fecha actual en las que la columna BU es igual a "Ventas" o la columna Other es igual a "Foo"

```
DeleteRows( CurrentDate(), BuList[BU="Sales" OR Other="Foo"])
```

## Ejemplo 2

Este ejemplo elimina todas las filas del conjunto de datos BuList de enero de 2010 donde la columna BU es igual a "Ventas" y la columna Fecha = "Ene 2010".

```
DeleteRows( "January 2010", BuList[BU="Sales" AND Date="Jan 2010"])
```
