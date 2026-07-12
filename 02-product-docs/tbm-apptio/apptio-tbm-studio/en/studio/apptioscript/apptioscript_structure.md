---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "ApptioScript structure"
breadcrumb: []
source_path: "studio/apptioscript/apptioscript_structure.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ApptioScript structure

ApptioScript structure consists of statements, editable tables, variables, and dynamic
text.

The top level structure of an ApptioScript consists of one or more of the following:

- Defining a subprocedure
- Definitions
- Calling subprocedures
- Statements

## Statements

Simple statements
:   Simple statements are method calls, such as the following two
    examples:

    `Return("Foo")`

    `EditRow(...)`

Assignment statements
:   You can assign the value of an expression to a variable in an Apptio scriptable object. Currently
    this is only used in editable tables in the onCellValueChanged script. To accomplish this, insert
    the scriptable row object in the procedure. The row object has cell values that are accessible via
    the columnName. The cell has the following attributes that can be set:

    - isRequired = value
    - isEditable = value

      When assigning a value to a cell you may use any of the Apptio functions
      that have valid context.

      [Learn more about formulas and
      functions](../formulas-and-functions/introduction-to-formulas-and-functions.htm "(Opens in a new tab or window)")

      Example:

      ```
      Sub MyProcedure(row)
      row.columnA.isRequired = "true"
      row.columnB.isEditable = "false"
      row.columnB = UPPER(columnC)
      row.columnC = "foo"
      End Sub
      ```

Columns with spaces
:   When working with columns containing spaces, you must wrap the entire identifier in curly
    braces.

    Example:

    ```
    If {Vendor ID} != ""
    {row.Purchase Description.isRequired} = "true"
    End If
    ```

If statements
:   The syntax of a If statements is:

    ```
    If condition
    [statements]
    ElseIf condition
    [statements]
    End If
    ```

    You may nest If statements inside If statements. The ElseIf condition is
    optional. You may have more than one ElsIf. The condition follows the same syntax and semantics as
    the If function filter expressions.

    [Learn more about the If function](../formulas-and-functions/functions/if.htm "(Opens in a new tab or window)")

Sub Procedure
:   A subprocedure is a series of ApptioScript statements enclosed by the Sub statement and the End
    Sub statement. A subprocedure may be called multiple times. Each time a subprocedure is called, the
    enclosed statements are executed, starting with the first executable statement after the Sub
    statement and ending with the End Sub statement.

    A subprocedure can declare an optional list of arguments that are passed into it when it is
    called. The arguments are declared in the Sub statement.

    Example:

    ```
    Sub Test(arg1, arg2)
    Return(arg1)
    End Sub
    ```

    To call a procedure use the procedure name and pass it the correct number of arguments. To call
    the procedure Test in the above example, use the following statement.

    `Test("foo", "bar")`

Comments
:   Comments must be on their own line. A comment cannot be added to a line containing non-comments.
    The comment line starts with the tick ' character. Everything after the tick to the end of a line is
    ignored by the parser. Multi-line comments require their own ' at the beginning of each line.

    `' This line is a comment and is ignored by the parser.`

## Editable Table

You can attach a script to an editable table that executes in one of following conditions:

- When leaving an edited cell
- When you add a new row
- On the initial load or refresh of the data set in the report component.

## Variables

Two variables exist that you can use in your scripts.

Row
:   Row is the current row that the script is executing against. A row has cells, and a cell has
    three scriptable attributes: isRequired, isEditable and the value.

    The following script shows usage of them:

    ```
    if columnB = "bar"
    row.columnA = "foo"
    row.columnA.isRequired = "true"
    row.columnA.isEditable = "true"
    end if
    ```

eventType
:   eventType can be used to perform specific logic when a user edits a cell, for example to update a
    timestamp.

    eventType can have the following values: 'onload', 'cellEdit', or 'addRow'.

    Here is an example:

    ```
    if eventType = "cellEdit" OR eventType = "addRow"
    row.name = "<%=$CurrentUser:Users.Id%>"
    end if
    ```

## Dynamic Text

ApptioScript supports dynamic <%=%> text.

Tip: Before any line of ApptioScript is
executed, all dynamic text is evaluated and replaced in the script.
