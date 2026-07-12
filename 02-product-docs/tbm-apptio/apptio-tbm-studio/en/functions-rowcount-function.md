---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "RowCount function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "RowCount function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/rowcount.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# RowCount function

*Returns a count of the total number of rows in a specified table. If no table is specified, it returns the number of rows in the current table context.*

## Syntax

RowCount([table])

## Parameters

table : The name of the table to count rows from. If omitted, counts rows in the current table context. You may not specify the current table name explicitly. Optional (default: current table)

## Behavior

- Counts all rows in the specified table.
- If no table is provided, it defaults to the current table context.
- The current table's name cannot be used explicitly as an argument.

## Return type

Number

## Example

In the following example, if the table Servers has 180 rows, the function returns 180.: =RowCount(Servers)

RowCount() : Returns the number of rows in the current table context.
