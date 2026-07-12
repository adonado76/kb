---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "EditRows función"
breadcrumb: []
source_path: "studio/apptioscript/editrows_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# EditRows función

Utilice EditRows( ) para modificar una fila de tabla existente y establecer valores en las columnas de dicha tabla.

Nota:

- Si ejecuta este script en una vista filtrada de una tabla, sólo las filas filtradas se verán afectadas por la ejecución del script de edición de filas.
- La función de búsqueda en otra tabla editable sólo funcionará para tablas editables.
- No funcionará para tablas editables enriquecidas, ni para tablas de consulta múltiple.

## Sintaxis 1

```
EditRows( date, tableName[optional filters], columName="value", columName2=value,...)
```

## Sintaxis 2

```
EditRows( date, tableName[columnName1={lookupTable.columnX} AND columnName2={lookupTable.columnY} AND ...], columName="{lookupTable.columnP}", columName2=value,...)
```

## fecha

Determina la fecha para modificar el conjunto de datos.

## filtros opcionales

¡Los filtros utilizan el!Función FILTRO.

## tableName

El nombre del conjunto de datos, indicado por el nombre de una tabla.

## columnName

El nombre de una columna de la tabla identificada en el argumento tableName. El nombre de la columna puede pertenecer a la tabla de consulta o a la tabla de origen.

## valor

El valor a insertar en la celda de la columna.

## Ejemplos

Ejemplo 1
:   ```
    EditRows( "<%=BuList.Date%>", BuList[BU="Sales" AND Date="<%=BuList.Date%>"], status="ACCEPTED", comment="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
    ```

Ejemplo 2
:   ```
    EditRows( "Jan 2010", BuList[BU="Sales" AND Date="Jan 2010"], status="ACCEPTED", comment="Accepted by Bob on May 15, 2010")EditRows( "<%=BuList.Date%>", BuList[BU="Sales" AND Date="<%=BuList.Date%>"], status="ACCEPTED", comment="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
    ```

Ejemplo 3
:   ```
    EditRows("January:2022", Plan Volume[Service Provider GOC={Service Provider GOC.Original}], Service Provider GOC={Service Provider GOC.New}, Comment={Service Provider GOC.Comment})
    ```

Ejemplo 4
:   ```
    EditRows("January:2015", ET3[Name = {ET4.Name}], ID = {ET4.ID}, Seq = ({ET3.Seq}*2))
    ```

## Mensajes de error

- Los tipos de columna Lookup deben ser los mismos para la columna [ ET3 ]

  ```
  EditRows("January:2015", ET3[Seq={ET4.Seq}], ID = 2+"ABCV")
  ```
- Dos tablas de consulta [ ET4 ], [ ET4 ] no están permitidas

  ```
  EditRows("January:2015", ET3[Seq={ET4.Seq}], ID = {ET5.ID})
  ```
