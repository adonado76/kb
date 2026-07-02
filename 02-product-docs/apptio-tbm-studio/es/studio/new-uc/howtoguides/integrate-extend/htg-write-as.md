---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Guía práctica: Cómo escribir fórmulas en ApptioScript"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Integrar y ampliar"
  - "Programación"
source_path: "studio/new-uc/howtoguides/integrate-extend/htg-write-as.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Guía práctica: Cómo escribir fórmulas en ApptioScript

**Objetivo:** Aprender los fundamentos de « ApptioScript » y escribir tu primer script funcional.

**Tiempo estimado:** 30 minutos

**Requisitos previos:** Acceso a TBM Studio con al menos una tabla editable

## Conceptos básicos de « ApptioScript »

ApptioScript se ejecuta en dos contextos principales: asociado a tablas editables (respondiendo a cambios en las celdas, adiciones de filas o la carga de datos) y asociado a botones (ejecutándose cuando el usuario hace clic). Es fundamental comprender estos contextos antes de escribir cualquier guion.

Se recomienda utilizar algún tipo de editor de texto para facilitar la redacción de scripts más largos. El texto se puede copiar y pegar en el editor.

**Dónde se ejecutan los scripts**

|  |  |  |
| --- | --- | --- |
| **Ubicación** | **Cuando se ejecuta** | **Usos habituales** |
| Script para tabla editable | Al editar una celda, añadir una fila o cargar/actualizar una tabla | Validación, formato de celdas, registros de auditoría, consultas |
| Acción del botón del servidor | Cuando el usuario hace clic en el botón | Transiciones del flujo de trabajo, operaciones con datos, operaciones de copia |

## Estructura del guion

Cada instrucción « ApptioScript » consta de sentencias que se ejecutan de forma secuencial. Los elementos básicos son:

- **Instrucciones** : llamadas a funciones que realizan acciones (por ejemplo, ` EditRows( `, ` AddRow( `)
- **Lógica condicional** — If/ElseIf/End Si bloques para la ramificación
- **Las variables** «row» y « eventType » están disponibles en los scripts de tablas editables
- **Subprocedimientos** : bloques de código reutilizables definidos con Sub/End Sub
- **Comentarios** : las líneas que comienzan con un apóstrofo (') se ignoran
- **Texto dinámico** : sintaxis <%=%> para insertar valores en tiempo de ejecución

## Variables clave en los scripts de tablas editables

**La variable de fila**

La variable «row» representa la fila que se está procesando actualmente. Puedes leer los valores de las celdas, establecer nuevos valores y controlar las propiedades de las celdas:

```
' Read a cell value
If row.Status = "Complete"
 
' Set a cell value
row.LastUpdated = "<%=CurrentDate()%>"
 
' Make a cell required
row.ApproverName.isRequired = "true"
 
' Make a cell read-only
row.SystemID.isEditable = "false"
 
End If
```

**La variable « eventType »**

La variable ` eventType ` indica qué ha activado el script. Esto es esencial para los scripts que deben comportarse de forma diferente según el contexto:

|  |  |
| --- | --- |
| **eventType Valor** | **Cuándo ocurre** |
| «onload» | La tabla se carga o se actualiza inicialmente |
| "cellEdit" | El usuario modifica cualquier celda de la fila |
| "cellEdit(ColumnName)" | El usuario edita una columna concreta (por ejemplo, « cellEdit(Status ») |
| "addRow" | El usuario añade una nueva fila |
| "duplicateRow" | El usuario duplica una fila existente |

## Paso a paso: crea tu primer guion

En este tutorial se crea un sencillo script de registro de auditoría que registra quién editó una fila y cuándo.

## Paso 1: Prepara tu tabla editable

Antes de añadir un script, asegúrate de que tu tabla editable tenga columnas para almacenar la información de auditoría. Para este ejemplo, añade dos columnas:

1. **Editado por** — Tipo de etiqueta, para almacenar el ID de usuario
2. **Fecha de edición** — Tipo de etiqueta, para almacenar la marca de tiempo

Consejo: Si los nombres de las columnas contienen espacios, debes escribir el identificador completo entre llaves en tu script: « {row.Edited By} » en lugar de « row.EditedBy ».

## Paso 2: Accede al Editor de scripts

1. Echa un vistazo a la tabla editable
2. Ve a la tabla editable en el Explorador de proyectos
3. Ve a **Pasos > Script**
4. Se abre el editor de guiones, mostrando cualquier guión existente o un espacio en blanco para crear nuevos guiones

## Paso 3: Escribir el script del registro de auditoría

Introduce el siguiente script. Esto registra el ID de usuario y la marca de tiempo cada vez que alguien edita o añade una fila:

```
' Audit trail: capture who edited and when
' This script runs on every cell edit or new row
 
If eventType = "cellEdit" OR eventType = "addRow"
 ' Store the current user's ID
    {row.Edited By} =
        "<%=$CurrentUser:Users.Id%>"
 
    ' Store the current date and
        time
    {row.Edit Date} =
        "<%=DateFormat(NOW(),"MM-dd-yyyy hh:mm a")%>"
End If
```

## Paso 4: Guardar y probar

1. Haz clic en **«Guardar»** para guardar el script
2. Consulta la tabla editable
3. Abre un informe que contenga esta tabla editable
4. Edita cualquier celda de la tabla
5. Comprueba que las columnas **«Editado por»** y **«Fecha de edición»** se rellenen automáticamente

**Resultado esperado:** Al editar cualquier celda, la columna «Editado por» muestra tu ID de usuario (por ejemplo, «jsmith») y la columna «Fecha de edición» muestra la marca de tiempo (por ejemplo, «15-01-2025 14:30»).

Consejo: Utiliza Debug() para solucionar problemas en los scripts. Añade Debug("Prueba: " & row.Status ) para mostrar los valores en un cuadro de diálogo durante la ejecución.

## Uso de texto dinámico

El texto dinámico (<%=%>) te permite insertar valores que se evalúan en tiempo de ejecución. Todo el texto dinámico se evalúa y se sustituye antes de que se ejecute cualquier línea de « ApptioScript ».

**Patrones de texto dinámico habituales:**

|  |  |
| --- | --- |
| **Expresión** | **Devuelve** |
| <%=$CurrentUser:Users.Id%> | ID del usuario actual |
| <%=$CurrentUser:Users.Full Nombre%> | Nombre completo del usuario actual |
| <%=$CurrentUser:Users.Role%> | Rol del usuario actual |
| <%=CurrentDate()%> | Fecha actual (formato predeterminado) |
| <%=CurrentDate("MMMM:yyyy")%> | Periodo actual en formato Mes:Año |
| <%=DateFormat(NOW( ),"MM-dd-aaaa")%> | La fecha de hoy con formato |
| <%=ProjectName()%> | Nombre del proyecto actual |

## Errores habituales

- **Olvidar las llaves en las columnas con espacios:** utiliza {row.Vendor Name} en lugar de row.Vendor Nombre
- **Comparaciones de cadenas incorrectas:** los valores distinguen entre mayúsculas y minúsculas. «Activo» ≠ «activo»
- **Falta «End If»:** toda instrucción «If» requiere una instrucción «End If» correspondiente
- **Comentarios en las líneas de código:** Los comentarios deben aparecer en una línea aparte. El carácter «'» no puede aparecer al final de una línea de código
- **Valores booleanos como cadenas:** isRequired y isEditable utilizan los valores de cadena «true» o «false», no los valores booleanos true/false

**Tema principal:** [Programación](../../../../studio/new-uc/howtoguides/integrate-extend/scripting.html)
