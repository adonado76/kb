---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: Cómo utilizar patrones de script habituales"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Programación"
source_path: "studio/new-uc/howtoguides/integrate-extend/htg-use-common-pattern.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: Cómo utilizar patrones de script habituales

**Objetivo:** Aprender patrones de « ApptioScript » de eficacia probada para situaciones empresariales habituales.

**Tiempo estimado:** 45 minutos para revisar todos los patrones

**Requisitos previos:** Haber completado la primera guía práctica o tener conocimientos equivalentes de « ApptioScript »

Esta guía presenta ocho patrones habituales que puedes adaptar a tus implementaciones. Cada patrón incluye el caso de uso empresarial, un ejemplo de código completo y notas de implementación.

## Patrón 1: Consultar valores de otra tabla

**Caso de uso empresarial**

Tienes una tabla de asignación de personal en la que los usuarios seleccionan a un empleado. Quieres que el departamento del empleado se rellene automáticamente a partir de una tabla maestra de empleados, de forma similar a la función BUSCARV de Excel.

**El guion**

```
' Lookup department from employee master table
' When user selects Employee ID, fetch their department
 
row.Department = lookup(EmployeeID, Department, EmployeeID, EmployeeMaster)
```

**Cómo funciona**

La función lookup() admite cuatro parámetros: el valor que se va a buscar ( EmployeeID de la fila actual), la columna que se va a devolver (Departamento), la columna con la que se va a realizar la búsqueda ( EmployeeID en la tabla de búsqueda) y el nombre de la tabla de búsqueda ( EmployeeMaster ).

**Alternativa mediante la sintaxis de referencia a tablas**

```
' Alternative lookup syntax using table reference
{row.Unit of Measure} = All Business Services:Unit of Measure[Service ID=Service
        ID]
```

Nota: La función de búsqueda solo funciona con tablas editables. Para realizar búsquedas en otros tipos de tablas, utiliza la sintaxis de referencia a tablas que se muestra arriba.

## Patrón 2: Lógica condicional (SI/ENTONCES)

**Caso de uso empresarial**

Cuando un usuario selecciona un estado, quieres que el campo «Ciudad» sea obligatorio para algunos estados (como California), pero opcional para otros, y que los nombres de las ciudades se conviertan automáticamente a minúsculas para mantener la coherencia.

**El guion**

```
' Make City required for California, optional for others
' Also standardize city name to lowercase
 
If State = "CA"
 row.City.isRequired = "true"
 ' Standardize to lowercase
 row.City = LOWER(City)
Else
 row.City.isRequired = "false"
End If
```

**Ejemplo con múltiples condiciones**

```
' Different validation based on expense type
If ExpenseType = "Capital"
    row.DepreciationPeriod.isRequired =
        "true"
    row.DepreciationPeriod.isEditable =
        "true"
ElseIf ExpenseType = "Operating"
    row.DepreciationPeriod.isRequired =
        "false"
    row.DepreciationPeriod.isEditable =
        "false"
 row.DepreciationPeriod = ""
End If
```

Consejo: Puedes anidar sentencias «if» dentro de otras sentencias «if» para crear lógicas complejas, pero procura que el anidamiento no sea demasiado profundo (2 o 3 niveles como máximo) para facilitar el mantenimiento.

## Patrón 3: Control de acceso a las celdas basado en roles

**Caso de uso empresarial**

Quieres que solo los administradores puedan editar los importes financieros, mientras que los usuarios normales puedan verlos pero no modificarlos. Esto proporciona un nivel adicional de control más allá de la seguridad a nivel de fila.

**El guion**

```
' Only Apptio Admins can edit the Amount column
If "<%=$CurrentUser:Users.Role%>" = "Apptio Admin"
 row.Amount.isEditable = "true"
Else
    row.Amount.isEditable =
        "false"
End If
```

**Notas de implementación**

- Este script se ejecuta al cargarse la página, por lo que la posibilidad de editar las celdas se establece cuando se muestra la tabla
- La comprobación de roles utiliza el nombre exacto del rol tal y como se define en la administración de TBM Studio
- Combínelo con la seguridad a nivel de fila (RLS) para lograr un control de acceso integral

## Patrón 4: Manipulación de fechas

**Caso de uso empresarial**

Es necesario trabajar con fechas en distintos formatos para diversos fines: registrar marcas de tiempo para registros de auditoría, especificar ejercicios fiscales para operaciones con datos o calcular el inicio del ejercicio fiscal.

**Formatos habituales de fecha**

```
' Capture current timestamp with custom format
row.Timestamp = "<%=DateFormat(NOW(),"MM-dd-yyyy hh:mm:ss a")%>"
 
' Get current fiscal period (for use in data operations)
' Returns format like "January:2025"
AddRow(CurrentDate("MMMM:yyyy"), MyTable, Name="NewRecord")
 
' Add row for start of fiscal year
AddRow("!START_OF_YEAR(February:2025)", BudgetTable, Category="Annual")
 
' Add row for most recently edited period
AddRow(".MostRecent", AdjustmentsTable, Type="Correction")
```

**Referencia sobre el formato de fecha**

|  |  |  |
| --- | --- | --- |
| **Cadena de formato** | **Ejemplo de resultado** | **Caso de uso** |
| dd-mm-aaaa | 15 de enero de 2025 | Formato de fecha de EE. UU |
| MMMM:aaaa | January:2025 | Ejercicio fiscal (obligatorio para las operaciones con datos) |
| MMMM:AFyyyy | January:FY2025 | Formato del ejercicio fiscal |
| h:mm a | 14:30 | Hora con AM/PM |
| h:m:s a | 14:30:45 | La hora con los segundos |

Advertencia: Para operaciones con datos como AddRow( ) y EditRows( ), las fechas deben indicarse con el nombre completo del mes (enero, no «ene») en el formato MMMM:aaaa.

## Patrón 5: Operaciones con cadenas

**Caso de uso empresarial**

Es necesario estandarizar la introducción de datos, combinar valores para su visualización o crear mensajes dinámicos. Las funciones de cadena ayudan a garantizar la coherencia de los datos y a generar mensajes informativos para el usuario.

**Patrones comunes en cadenas de caracteres**

```
' Standardize text to uppercase
row.VendorCode = UPPER(VendorCode)
 
' Standardize text to lowercase
row.Email = LOWER(Email)
 
' Concatenate values for a composite field
row.AcceptedBy = "Accepted by <%=$CurrentUser:Users.Full Name%> on
        <%=CurrentDate()%>"
 
' Build a detailed comment
row.Comment = "Approved: " & Description & " (" & Amount & ")"
```

**Concatenación de cadenas**

Utiliza el operador «&» para concatenar cadenas. Puedes combinar texto literal (entre comillas), valores de columna y texto dinámico en una sola expresión.

## Patrón 6: Cambios en el estado del flujo de trabajo (acciones de los botones)

**Caso de uso empresarial**

Tenéis un proceso de planificación de la demanda en el que los responsables de los centros de coste presentan sus planes y el departamento de finanzas los aprueba o los rechaza. Necesitas botones que actualicen el estado del flujo de trabajo (por ejemplo, «Enviar», «Aprobar», «Rechazar»).

**Script del botón «Enviar»**

```
' Submit Plan - changes CSM Status to "Submitted"
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 CSM Status="Submitted")
```

**Script del botón «Aprobar»**

```
' Approve Plan - Finance approves the submission
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 Finance Status="Approved")
```

**Script del botón «Rechazar»**

```
' Reject Plan - Finance rejects the submission
EditRows("Jun 2019", Demand Plan Status[Cost Center="CC-123"], 
 Finance Status="Rejected")
```

**Script del botón «Restablecer todo» (solo para administradores)**

```
' Reset All - Returns all records to initial state
' Note: Empty filter [] applies to all rows
EditRows("Jun 2019", Demand Plan Status[], 
 CSM Status="Not Submitted", 
 Finance Status="Pending", 
 CopyTable="No")
```

**Cómo asignar scripts a botones**

1. En Report Studio, cambia al modo de edición
2. Haz clic con el botón derecho del ratón en el botón y selecciona **«Propiedades»**
3. Selecciona la pestaña **«Acciones»**
4. Introduce tu script en el campo **«Acción del servidor»**
5. Haz clic **en Aceptar**

## Patrón 7: Notificaciones por correo electrónico sobre eventos

**Caso de uso empresarial**

Cuando el responsable de un centro de costes envía un plan de demanda, se desea notificar automáticamente por correo electrónico al responsable de la aprobación designado, indicándole los detalles del envío.

**El guion**

```
' Send notification when plan is submitted
If eventType = "cellEdit(Submission_Status)"
    If {row.Submission Status} =
        "Submitted"
        ' Send email to the designated
        approver
 SendEmail(row.Approver, 
            "Demand Plan submitted for
        review and approval", 
            "Demand Plan submitted by
        " & row.Submitter & 
            " for the " &
        row.Organization Name & " department. " &
            "Special comment from
        submitter: " & row.Submission Comment)
 End If
End If
```

**SendEmail Sintaxis**

`SendEmail("recipient@company.com", "Subject Line", "Email Body
Content")`

**Notas de implementación**

- El uso de « cellEdit(ColumnName » evita que el correo electrónico se vuelva a enviar cuando se modifican otras columnas
- El destinatario puede ser un valor de celda (como row.Approver ) o una dirección de correo electrónico fija
- Utiliza «&» para concatenar cadenas de caracteres y crear contenido dinámico en los correos electrónicos

Advertencia: Prueba minuciosamente los scripts de correo electrónico en un entorno de desarrollo. Los scripts incorrectos pueden enviar correos electrónicos no deseados a destinatarios reales.

## Patrón 8: Copiar datos entre tablas

**Caso de uso empresarial**

Una vez que el departamento financiero apruebe un plan de demanda, conviene copiar los volúmenes previstos a una tabla de «aprobados» que sirva de base para los informes posteriores. Esto crea una instantánea del estado aprobado.

**CopyTable Ejemplo**

```
' Copy approved forecast to snapshot table
CopyTable(
   
        "reference.apptio.com:<%=ProjectName()%>/Reports/<%=CurrentDate("MMMM:yyyy")%>/CostModels/Default/.TableTransform:Volume
        Forecasts Transform/.Summary/",
   
        "reference.apptio.com:<%=ProjectName()%>",
 "Volume Forecasts Approved",
   
        "<%=CurrentDate("MMMM:yyyy")%>"
)
```

**CopyEditableTable Ejemplo**

```
' Copy editable table with auto check-in
CopyEditableTable(
   
        "tests.apptio.net:MyProject/Data/January:FY2015/Source Data",
 "tests.apptio.net:MyProject",
 "Archived Data",
 "overwrite",
 autocheckin="true"
)
```

## Diferencias clave

|  |  |  |
| --- | --- | --- |
| **Función** | **Usar para** | **Facturación automática** |
| CopyTable() | Tablas de informes, conjuntos de datos sin procesar | No (espacios en el entorno de desarrollo) |
| CopyEditableTable() | Tablas editables con control de modo | Opcional (parámetro autocheckin) |

Nota: « CopyTable » guarda los datos en el espacio de trabajo de desarrollo del usuario actual y NO registra los cambios automáticamente. Considera la posibilidad de limitar esta función a los administradores.

## Patrones adicionales

## Recorrido por los datos

Utiliza la función «Loop» para recorrer las filas de un conjunto de datos y realizar operaciones en cada una de ellas.

```
' Process each row in a data set
Loop mydatasetname
 Debug("Cost=" & Cost)
 ' Add additional operations here
End Loop
```

## Eliminación condicional de filas

Utiliza ` DeleteRows( )` para eliminar de una tabla editable las filas que cumplan criterios específicos.

```
' Delete all rows where BU is "Sales" OR Other is "Foo"
DeleteRows(CurrentDate(), BuList[BU="Sales" OR Other="Foo"])
 
' Delete rows matching multiple conditions (AND)
DeleteRows("January 2010", BuList[BU="Sales" AND Date="Jan 2010"])
```

## Añadir filas mediante programación

Utiliza « AddRow( » para crear nuevos registros en tablas editables con valores iniciales.

```
' Add a new project record for the current period
AddRow(CurrentDate("MMMM:yyyy"), All Projects, 
 Project Name="unnamed", 
 Status="Pending")
 
' Add a server record for a specific period
AddRow("February:2008", MyServers, 
 servername="server001", 
 ram="128", 
 os=UPPER("windows"))
```

## ¿Qué viene ahora?

- Sección 5.6: ApptioScript Referencia: documentación completa de la función con todos los parámetros y opciones
- [Configurar la seguridad de los datos](../work-with-data/data-security.html) : infórmate sobre la seguridad a nivel de fila, que complementa el control de acceso basado en scripts
- [Conéctate a través de API](api-integration.html) : para integraciones avanzadas más allá de ApptioScript

**Tema principal:** [Programación](../../../../studio/new-uc/howtoguides/integrate-extend/scripting.html)
