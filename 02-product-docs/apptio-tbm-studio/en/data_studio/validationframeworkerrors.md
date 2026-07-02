---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Validation Framework error messages: Explanations and workarounds"
breadcrumb: []
source_path: "data_studio/validationframeworkerrors.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Validation Framework error messages: Explanations and workarounds

Applies to: TBM Studio 12.0 and later

This article describes common pipeline errors that can occur in Table documents in Apptio TBM
Studio. These errors highlight configuration issues that will cause your project to behave
differently than you expect. Apptio strongly advises customers to resolve errors.

What does an error look like?

![](../../resources/images/studio_images/studioimages/studio_import_error.png)

Note: This article describes common errors and is not all-inclusive. Also, new errors are added
frequently. If you receive an error not discussed here and you want more information about it,
please add a comment below, and we will investigate it.

The information below is sorted by pipeline step. Within each step, we list the errors, when
available, that are applicable to that step.

## All steps

Recursion errors
:   *Message* - "<information> Err: Recursion detected for <information>" or "Recursion
    when trying to access table"

    *Description* - This error is like the Cycle Detected message, except that in this case the
    table is reference to itself, and thus that portion of the configuration will not be calculated.

Cycle detected
:   *Message* - "Cycle Detected. This step will not be calculated as it is involved in a
    circular reference. <table> references <table> (pipeline step in the other table)."

    *Description* - The Cycle Detected error indicates this pipeline step
    is being ignored entirely. This is because calculating it would result in a circular reference, and
    thus your model could not be calculated. To resolve this issue, you must decide which side of the
    circular reference you wish to keep, and delete, or change the other side of the circular reference
    to remove the circularity.

    ![](../../resources/images/studio_images/studioimages/studio_append_cycle%20detected.png)

    Note: This error message was introduced in TBM Studio v12.3.4. Prior to that, other error messages
    that were step specific occurred in some steps, and some circularities were not detected that are
    now found.

## Source error message

Double-string conversion
:   *Message* - The table triggering this will typically have an error such as the
    following:

    "Mismatched lookup from column “<table.Column>” of type “<Type>”
    (“<varies>”) to column “<Column2>” of type “<Type>”
    (”<varies>”)"

    *Description* - This error means that another table is referencing the
    specified column with the expectation that it is of type Label, but it is either a numeric column or
    has had numeric values in it.

    To resolve this error, either:

    - Change the column type in the local table or remote table so that the columns match; or
    - Do explicit-type conversion.

    Other errors in tables with a source of Existing Table - For a table
    that is based off another table, errors in the other table will be surfaced in the source step in
    some situations. Examine the source table for more information in this situation.

## Existing table error message

Error Getting Backing Table ‘<table name>'
:   *Message* - "Error Getting Backing Table ‘<table name>'"

    *Description* - This error typically means the source table has been deleted. To resolve
    this, create a table of the specific table name.

## Import error messages

Mismatched Type label
:   *Message* - "Expected Type Label but Found Numeric"

    *Description* - This error will occur if the incoming type specified for the column is
    Label, but every value in the column can be parsed as a number. If this column is expected to have
    numeric values OR label values, but you want it stored as a label, do the following:

    1. Leave Type Override set to Label.
    2. Change Incoming Type to Any.![](../../resources/images/studio_images/studioimages/studio_import%20error_mismatched%20type%20label.png)

Column does not exist
:   *Message* - "Column Does not Exist"

    *Description* - This error means that the data validation rules have been configured to
    expect a column, but it does not exist in the most recent upload. If you do not want this column in
    the table, delete it from the validation rule. Otherwise, add it to your table, and re-upload
    it.

    ![](../../resources/images/studio_images/studioimages/studio_validation%20framework_remove%20column.png)

Added column
:   *Message* - "Column Was Added"

    *Description* - This means the data validation rules have been configured to not expect a
    column, but it exists in the most recent upload. If you want this column in the table, add it from
    the validation rule. Otherwise, delete it in your table and re-upload the table.

    ![](../../resources/images/studio_images/studioimages/studio_columns_add.png)

Unknown type label
:   *Message* - "Expected Type Label but Found Unknown"

    *Description* - This error will occur if the Incoming type is set to 'Label', and the column
    does not contain any values. To resolve this, add values to the column, or change the ‘Incoming
    Type’ to ‘Any’.

    ![](../../resources/images/studio_images/studioimages/studio_columns_pick.png)

Unknown Type
:   *Message* - "Expected Type <Numeric/Label> but Found Unknown"

    *Description* - This error will occur if the Incoming type is set to Numeric or Label, and
    the column does not contain any values. To resolve this, add values to the column, or change the
    Incoming Type to Any.

    ![](../../resources/images/studio_images/studioimages/studio_columns_numeric.png)

Cardinality
:   *Message* - "Expected Cardinality <MANY/ONE> but Found <Many/ONE)"

    *Description* - This error will occur if your Import step has been
    configured to validate cardinality, and the cardinality changes. If you do not wish to validate
    cardinality, select the Enable cardinality validation checkbox. Otherwise,
    fix the cardinality in your uploaded file:

    ![](../../resources/images/studio_images/studioimages/studio_validation%20framework_%20column%20does%20not%20exist.png)

## Append error messages

Multiple value types
:   *Message* - Example full message: “Delivery: Multiple value types for column Delivery:
    [LABEL in Business Services Transform], [UNKNOWN in All Business Services]”

    *Description* - Your Append step is mapping together columns of a different type.

    How to fix it:

    Ensure that all data sets have a type defined on the column and ensure that this type is
    identical across the data sets. Type can be defined on an Import step or the
    Formulas step. For editable tables, you can add a
    Formulas step, add the editable columns to it, and define a type for
    them.

    If you cannot make the type identical, then in the *Append* step, you can convert type
    between Numeric and Label by using the following
    formulas:

    - To convert a numeric to a label: = NumberFormat(column,”#,###”)
    - To convert a label to a numeric: =Value(column)

## Other errors

*Message* - Varies.

*Description* - Check for the error in the ‘Formula Step’ section of this document. Since
you can type an arbitrary formula in an Append step, these can throw the same
errors as they would in a Formulas step.

## Group error messages

Missing column
:   *Message* - "Cannot find Column 'column'"

    *Description* - You will receive this error if the grouping operation is configured to group
    on a column that no longer exists. To resolve this, update the grouping step to group on a column
    that exists.

Unspecified column
:   *Message* - "No Column Specified"

    *Description* - You need to specify a column to group on in the Group step. You can safely
    ignore this error.

## Hide and rename error message

Cannot find column
:   *Message* - "Cannot find column"

    *Description* - The hide and rename step is referencing a column that does not exist.

    To resolve this:

    - remove the reference to that column from hide and rename
    - or, add it to a prior pipeline step

      ![](../../resources/images/studio_images/studioimages/studio_hide%20and%20rename_column%20to%20replace.png)

## Formula error messages

Cannot find column
:   *Message* - "Cannot find column named '<column>' in table '<table>'"

    *Description* - The formula is referencing the specified column name in the specified table.
    However, the column does not exist in that table.

    To resolve this, either:

    - add the column to that table
    - or, fix your formula to not reference a nonexistent column.

Cannot find column
:   *Message* - "Cannot find column named '<column>'"

    *Description* - The formula is referencing the specified column name in the current table.
    However, the column does not exist.

    To resolve this, either:

    - add the column to that table in an earlier pipeline step
    - or, fix your formula to not reference a nonexistent column

Cannot find column
:   *Message* - "Cannot find column named '<column>' in prior step for table
    '<table>'"

    *Description* - The formula is referencing the specified column name in the current table.
    However, the column does not exist. This error will be given by formulas that can only leverage
    columns from the prior step (not the current Formulas step).

    To resolve this, either:

    - add the column to that table in an earlier pipeline step
    - or, fix your formula to not reference a nonexistent column

Mismatched lookup
:   *Message* - "Mismatched lookup from column '<table.Column>' of type '<Type>'
    ('<varies>') to column '<Column2>' of type '<Type>' ('<varies>')"

    *Description* - The two columns either:

    1. Have different types. In this case, either:
       1. Change the type of one of the columns so that they match
       2. Or, explicitly convert the type:
          - To convert a numeric to a label: = NumberFormat(column,”#,###”)
          - To convert a label to a numeric: =Value(column)
    2. Values made it into a column that do not map that column's type. In this case:
       - If the error states <LABEL> (“long”), this means that the specified column is of type Label,
         but it contains Numeric values. If you get this error, go back to the referenced table and
         explicitly fix the values in that column to ensure they have the correct type.
       - If the error states <Numeric> (“BoxedStringOffset”), this means that the specified column is
         of type Numeric, but it contains Label values. If you get this error, go back to the referenced
         table, and explicitly fix the values in that column to ensure they have the correct type.

Cannot find table
:   *Message* - "Cannot find table"

    *Description* - This means that the formula references a table that does not exist. This
    error may also be observed if the target table is a model object upgraded from TBM Studio v11, as
    these lack a Table step. To resolve this, update the formula to reference a
    table that has a Table step.

Numberformat format
:   *Message* - "Can't format NaN from {}: <a string>"

    *Description* - This error will be called by the Numberformat function when passed a value
    of type Label. If you pass a label to the number format function, it will attempt to convert it to a
    number using the default number format. If it can be processed, you will get no error message. If it
    cannot be processed, then you will receive this error.

    To resolve this, update your configuration to call the NumberFormat function only on columns of
    type Numeric, which only contain numeric values.

    Errors involving columns using IF statements - In many cases, IF
    statements attempt to evaluate the conditional, and both possible outcomes in parallel, to improve
    customer performance. As a result, if a formula throws an error for either the true or false branch,
    the error will be displayed even if that branch is not taken for any row that would trigger the
    error.

## Date partition error message

Cannot find column

*Message* - "<Column Name>: Cannot find Column"

*Description* - This error typically indicates that the Date Partition step was configured
to use a time column that has since been deleted from the table. To resolve this, add that column
back into the backing table.

## Unpivot error message

Column does not exist
:   *Message* - "<Column Name>: Column does not exist"

    *Description* - The Unpivot step references a column that does not exist. Either remove it
    from the Unpivot configuration or add the column back to the table.

## Model step error messages

Allocation to object
:   *Message* - "Allocation to object <objectName>:USE\_MAP\_TABLE formula cannot be used with
    filters of from object <object>"

    *Description* - There are two situations where you may get this error:

    1. You are using a Weighted Value rule, and the Data Relationship is an Automatic Relationship with
       Automatic Many to Many enabled. There is also a filter specified in the From step. The legacy
       Automatic many-to-many allocation capability does not support filters in the From step. This
       capability exists for backwards compatibility for TBM Studio v11 customers and behaves the same way
       it did in R11 and earlier. To eliminate this error, either:
       - Remove the filter from the From step. This will not change your numbers
         since the filter is currently being ignored.
       - Or, turn off the automatic relationship, and use explicit keys instead.

         Note: This will change
         your numbers, as the filter will now be used.
    2. You are using an advanced allocation formula that leverages the USE\_MAP\_TABLE function. There is
       also a filter specified in the From step. The legacy USE\_MAP\_TABLE function does not support filters
       in the From step.To eliminate this error, remove the filter from the ‘From’ step. This will not
       change your numbers since the filter is currently being ignored. If you want the filter to be
       applied, filter the table you are passing into the USE\_MAP\_TABLE function in its transform
       pipeline.

Column linkages not found
:   *Message* - "Column Linkages not found from <table> to <table> <table.column> has
    been grouped and is not usable for rolling up values. <table.column> has been grouped and is not
    usable for rolling up values. (Automatic Many->Many detection is disabled)."

    *Description* - If this error occurs, this modeling step has an allocation to another listed
    table that is using the legacy Automatic allocation capability. To resolve this, switch to using
    explicit keys in your allocations data relationship.

    What it means:

    In the source object, the target object’s identifier column is null or various (as brought in by
    the Join step), and in the target object, the source object’s identifier column is null or various
    (as brought in by the Join step). Legacy Automatic allocations rely on one of these being
    non-various non-null for allocations that are not an automatic many to many. It is recommended to
    switch off the legacy automatic key allocations to resolve this.

    Note: The individual allocation causing this issue may not be flagged as broken.

Linked keys not found
:   *Message* - "Unable to Find Linked Keys for <Source Table> to <Target Table>"

    *Description* - This error will occur if the source object doesn't exist:

    - From the Prior step of the pipeline is not able to compute its table.
      This error can also occur sometimes if the table does not contain any rows.
    - Allocation columns were directly specified, and either one of them doesn't exist in the
      respective table;
    - Allocation is using the 'Automatic' allocations that exist for backward compatibility with R11,
      and the target table does not contain the source table's identifier column.

    To resolve this, add the missing column, or update the data relationship to use columns that
    exist.

Model key not found
:   *Message* - "Unable to find required model key on fully-linked table:
    <table>.<Column>"

    *Description* - This error will occur if the Model step is configured to use an identifier
    column, and the configured identifier column does not exist. To resolve this, either add back in the
    named column, or pick a different identifier.
