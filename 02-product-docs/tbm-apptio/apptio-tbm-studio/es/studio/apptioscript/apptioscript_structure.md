---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ApptioScript estructura"
breadcrumb: []
source_path: "studio/apptioscript/apptioscript_structure.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioScript estructura

ApptioScript consta de sentencias, tablas editables, variables y texto dinámico.

La estructura de nivel superior de un sitio ApptioScript consta de uno o varios de los siguientes elementos:

- Definición de un subprocedimiento
- Definiciones
- Llamada a subprocedimientos
- Sentencias

## Sentencias

Declaraciones sencillas
:   Las sentencias simples son llamadas a métodos, como los dos ejemplos siguientes:

    `Return("Foo")`

    `EditRow(...)`

Declaraciones de asignación
:   Puede asignar el valor de una expresión a una variable de un objeto scriptable Apptio. Actualmente sólo se utiliza en tablas editables en el script onCellValueChanged. Para ello, inserte el objeto de fila programable en el procedimiento. El objeto fila tiene valores de celda accesibles a través de columnName. La celda tiene los siguientes atributos que se pueden establecer:

    - isRequired = valor
    - isEditable = valor

      Al asignar un valor a una celda puede utilizar cualquiera de las funciones de Apptio que tengan un contexto válido.

      [Más información sobre fórmulas y funciones](../formulas-and-functions/introduction-to-formulas-and-functions.htm "(se abre en una pestaña o una ventana nueva)")

      Ejemplo:

      ```
      Sub MyProcedure(row)
      row.columnA.isRequired = "true"
      row.columnB.isEditable = "false"
      row.columnB = UPPER(columnC)
      row.columnC = "foo"
      End Sub
      ```

Columnas con espacios
:   Cuando trabaje con columnas que contengan espacios, deberá encerrar todo el identificador entre llaves.

    Ejemplo:

    ```
    If {Vendor ID} != ""
    {row.Purchase Description.isRequired} = "true"
    End If
    ```

Si las declaraciones
:   La sintaxis de una sentencia If es:

    ```
    If condition
    [statements]
    ElseIf condition
    [statements]
    End If
    ```

    Puede anidar sentencias If dentro de sentencias If. La condición ElseIf es opcional. Puede tener más de un ElsIf. La condición sigue la misma sintaxis y semántica que las expresiones de filtro de la función If.

    [Más información sobre la función If](../formulas-and-functions/functions/if.htm "(se abre en una pestaña o una ventana nueva)")

Subprocedimiento
:   Un subprocedimiento es una serie de sentencias ApptioScript encerradas por la sentencia Sub y la sentencia End Sub. Un subprocedimiento puede ser llamado varias veces. Cada vez que se llama a un subprocedimiento, se ejecutan las sentencias adjuntas, empezando por la primera sentencia ejecutable después de la sentencia Sub y terminando con la sentencia End Sub.

    Un subprocedimiento puede declarar una lista opcional de argumentos que se le pasan cuando es llamado. Los argumentos se declaran en la sentencia Sub.

    Ejemplo:

    ```
    Sub Test(arg1, arg2)
    Return(arg1)
    End Sub
    ```

    Para llamar a un procedimiento, utilice el nombre del procedimiento y pásele el número correcto de argumentos. Para llamar al procedimiento Test en el ejemplo anterior, utilice la siguiente sentencia.

    `Test("foo", "bar")`

Comentarios
:   Los comentarios deben ir en su propia línea. No se puede añadir un comentario a una línea que no contenga comentarios. La línea de comentario comienza con el carácter de tilde '. Todo lo que va desde la marca hasta el final de una línea es ignorado por el analizador sintáctico. Los comentarios multilínea requieren su propio ' al principio de cada línea.

    `' This line is a comment and is ignored by the parser.`

## Tabla editable

Puede adjuntar un script a una tabla editable que se ejecute en una de las siguientes condiciones:

- Al salir de una celda editada
- Al añadir una nueva fila
- En la carga o actualización inicial del conjunto de datos en el componente de informe.

## Variables

Existen dos variables que puedes utilizar en tus scripts.

Fila
:   Fila es la fila actual contra la que se está ejecutando el script. Una fila tiene celdas, y una celda tiene tres atributos scriptables: isRequired, isEditable y el valor.

    El siguiente script muestra su uso:

    ```
    if columnB = "bar"
    row.columnA = "foo"
    row.columnA.isRequired = "true"
    row.columnA.isEditable = "true"
    end if
    ```

eventType
:   eventType puede utilizarse para ejecutar una lógica específica cuando un usuario edita una celda, por ejemplo para actualizar una marca de tiempo.

    eventType puede tener los siguientes valores: 'onload', 'cellEdit', o 'addRow'.

    He aquí un ejemplo:

    ```
    if eventType = "cellEdit" OR eventType = "addRow"
    row.name = "<%=$CurrentUser:Users.Id%>"
    end if
    ```

## Texto dinámico

ApptioScript admite texto dinámico <%=%>.

Consejo: Antes de que se ejecute cualquier línea de ApptioScript, todo el texto dinámico se evalúa y se sustituye en el script.
