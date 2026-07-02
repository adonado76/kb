---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "AddRow función"
breadcrumb: []
source_path: "studio/apptioscript/addrow_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# AddRow función

Utilice AddRow( ) para añadir una fila a una tabla y establecer valores en las columnas de dicha tabla.

## Sintaxis

```
AddRow(date, tableName, columnName=value, columnName2=value, ...)
```

## fecha

Determina la fecha de modificación de los conjuntos de datos. El argumento de fecha puede utilizar uno de los siguientes formatos:

| Formato de los argumentos | Descripción |
| --- | --- |
| "February:2008" | Añadir una línea en febrero 2008 |
| "!INICIO\_DEL\_AÑO( February:2008 )" | Añada una fila para el primer mes del ejercicio fiscal. |
| currentDate("MMMM:yyyy") | Añade una fila para el mes en curso. |
| ".MostRecent" | Añade una fila en el periodo de tiempo editado más recientemente para el proyecto. |

## tableName

El nombre del conjunto de datos, indicado por el nombre de una tabla.

## columnName

El nombre de una columna de la tabla identificada en el argumento tableName.

## valor

El valor a insertar en la celda de la columna en la nueva fila.

## Ejemplo 1

Este ejemplo está actuando sobre una tabla llamada MyServers, que tiene columnas llamadas servername, ram, y os. Tenga en cuenta que la tabla puede tener otras columnas sobre las que el script no actúa. Este ejemplo añade una fila a una tabla llamada MyServers para el primer mes del año fiscal y establece los siguientes valores para las columnas:

- nombre del servidor = server001
- RAM = 128
- os = WINDOWS

```
AddRow( "!START_OF_YEAR(February:2008)", MyServers, servername="server001", ram="128", os=UPPER("windows"))
```

## Ejemplo 2

Este ejemplo es igual que el Ejemplo 1, excepto que añade una fila para el mes actual en lugar del primer mes del año fiscal.

```
AddRow(CurrentDate("MMMM:yyyy"), MyServers, servername="server001", ram="128", os=UPPER("windows"))
```

## Ejemplo 3

Este ejemplo añade una fila a una tabla denominada DeliveryTracking para febrero de 2008. Indica que el valor del campo nombre es Server203, y el campo AcceptedBy contiene un mensaje de aceptación que identifica al usuario, la fecha y la hora de la aprobación.

```
AddRow( "February:2008", DeliveryTracking, name="Server203", AcceptedB="Accepted by <%=$CurrentUser:Users.Full Name%> on <%=CurrentDate()%>")
```

## Ejemplo 4

```
AddRow(CurrentDate("MMMM:yyyy"), All Projects, Project Name="unnamed", Status="Pending")
```

Para navegar posteriormente a esa fila utilice el siguiente comando:

```
[[tab:Demand and Resource/@.TableTransform:All Projects/!FILTER[{Project ID}=%22$ACTION_RESULT%22]/Update Project Definition]]
```
