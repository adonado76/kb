---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ApptioScript ejemplos"
breadcrumb: []
source_path: "studio/apptioscript/apptioscript_examples.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioScript ejemplos

Utilice los siguientes ejemplos para repasar los usos de ApptioScript.

## Ejemplo 1

```
' An example script used in OnCellValueChanged
If State = "CA"
row.City.isRequired = "true"
' Any function can be called here
' example: lower case the city cell
row.City = LOWER(City)
' a better way of doing lookup instead of using dynamic text
row.Japanese = lookup(Number,Japanese,Number,Japan)
Else
row.City.isRequired = "false"
End If
```

## Ejemplo 2

```
If State = "WA"
row.City.isEditable = "false"
Else
row.City.isEditable = "true"
End If
```

## Ejemplo 3

```
An example of calling a procedure:
Sub Test()
Test2()
End Sub
Sub Test2()
Return("Foo")
End Sub
```

## Ejemplo 4

```
Test() 'this calls Test() subprocedure defined in Example 3
```

## Ejemplo 5 Tablas editables

Introduzca el código en TBM Studio: **Tabla editable > Script**.

## Seguimiento de auditoría

Editar celda - ejemplo 1

```
If eventType = "cellEdit(Name)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
```

Editar celda - ejemplo 2

```
If eventType = "cellEdit(Name)" OR eventType = "cellEdit(ID)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
```

Editar celda - ejemplo de error

```
If eventType = "cellEdit(wrong column name)"
if row.Name="X"
SendEmail("email Id", "subject", "content")
end if
end if
could not evaluate [wrong column name] in cellEdit command
```

Nivel de fila - captura Editado por y Fecha de edición (formato de fecha = MM-dd-aaaa hh:mm a)

```
if eventType = "cellEdit" OR eventType = "addRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm a")%>"
end if
```

Nivel de fila - captura Editado por y Fecha de edición (formato de fecha = MM-dd-aaaa hh:mm a)

```
if eventType = "cellEdit" OR eventType = "duplicateRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm a")%>"
end if
```

## Controlar la editabilidad de una columna

```
row.FIELDNAME.isEditable = "false"
```

## Celdas editables basadas en roles

```
If "<%=$CurrentUser:Users.Role%>" = "Apptio Admin"
row.Amount.isEditable="false"
Else
row.Amount.isEditable="true"
End If
```

## Rellenar el valor de una celda a partir de otra consulta

```
{row.Unit of Measure}=All Business Services:Unit of Measure[Service ID=Service ID]
```

## Ejemplo 6 Botón de apoyo al flujo de procesos

Introduzca el código en Propiedades del botón: **Acciones > Acciones del servidor**.

## Presentar plan (cambio de estatus del consumidor)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status="Submitted")
```

## Anular la presentación del plan (cambio de estado del consumidor)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status="Not Submitted")
```

## Rechazar plan (Cambio de estado de las finanzas)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], Finance Status="Rejected")
```

## Anular la presentación del plan (cambio de estado de las finanzas)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], Finance Status="Approved")
```

## Reinicio (cambio de estado de las finanzas)

```
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CSM Status = "Not Submitted", Finance Status = "Pending", CopyTable="No")
```

## Restablecer todo (procesar el cambio de estado del propietario)

```
EditRows("Jun 2019", Demand Plan Status[], CSM Status = "Not Submitted", Finance Status = "Pending", CopyTable="No")
```

## CopyTable

```
copytable("reference.apptio.com:<%=ProjectName()%>/Reports/<%=CurrentDate("MMMM:yyyy")%>/CostModels/Default/.TableTransform:Volume Forecasts Transform/.Summary/","reference.apptio.com:<%=ProjectName()%>","Volume Forecasts Approved","<%=CurrentDate("MMMM:yyyy")%>")
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], CopyTable="Copied")
```

Nota: CopyTable colocará la tabla en el espacio de trabajo de desarrollo del usuario actual y NO registrará los cambios. Por esta razón, es posible que desee que esta funcionalidad sea controlada por un administrador en lugar de un usuario.

## Ejemplo 7 ApptioScript de ApptioOne Demanda

Tabla editable de entradas del Plan de Volumen

```
row.Service ID.isEditable = "false"
row.Service Offering.isEditable = "false"
row.Application Name.isEditable = "false"
row.Unit of Measure.isEditable = "false"
row.Rate.isEditable = "false"
row.Baseline Volume.isEditable = "false"
if eventType = "cellEdit" OR eventType = "addRow"
{row.Edited By}="<%=$CurrentUser:Users.Id%>"
{row.Edit Date}="<%=Dateformat(NOW(),"MM-dd-yyyy hh:mm:ss a")%>"
end if
```
