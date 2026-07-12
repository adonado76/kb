---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Lookup_From_Editable function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Lookup_From_Editable function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/lookup-from-editable.html"
images:
  - "03-media/apptio-tbm-studio/lookupeditable.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Lookup_From_Editable function

This function brings columns from an editable table via a lookup to include it in report tables that are displaying either data from a different editable table, or data from a transform/model.

## Where to use

- Data sets
- Formula columns in editable tables

## Where NOT to use

Transform pipeline, model driver, or advanced allocation formula.

## Syntax

=Lookup_From_Editable(source_column,lookup_table,matching_column,lookup_value_column, [leave_original_value], (replace_nulls], [ignore_case])

Arguments

- source_column is the column in the current data set that will match a column in the other data set.
- lookup_table is the editable name from where you need to translate data from.
- matching_column is the column in the lookup_table that matches the data in the column you specified in source_column.
- lookup_value_column is the column in the lookup_table that you need to translate back to the current data set.
- leave_original_value is boolean which doesn't update the result if the lookup is unsuccessful
- replace_nulls is boolean which replaces null with a defined default value
- ignore_case is boolean to ignore case for other params

## Return type

The type of the lookup column.

- If the LookUp_From_Editable function finds multiple matching rows, it returns {Various} instead of a null.
- If you are using the replace_nulls or ignore_case optional arguments, you also must specify the optional arguments that come before them.
- Use the standard curly braces { } to escape special characters or operators that might appear in column names being referenced. For example, {P&L Rate}.
- Inference linking multiple tables is preferable to doing lookups and can be used anytime the resulting column is not needed in a data set.

## Examples

This formula can be used to create a lookup column in one Editable table from another Editable Table.

Example Syntax

=Lookup_From_Editable(Product Family ID, L1 Product Family, Product Family ID, Product Family)
