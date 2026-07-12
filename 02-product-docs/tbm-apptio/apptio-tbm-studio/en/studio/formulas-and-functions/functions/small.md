---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Small function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/small.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu014.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Small function

Returns the smallest value in a specified column.

## Syntax

`Small([rollup_operator]column)`

## Parameters

*rollup\_operator*

@, SOURCE, ~, or TARGET. This argument is optional and used only with metrics. See [Rollup Operators](../operators.html "Applies to: TBM Studio 12.0 and later").

*column*: The column to search for the smallest value. You may specify a table prefix using
TableName:ColumnName. Required

## Behavior

Scans the specified column and returns the smallest (minimum) value.

## Return type

Number

## Examples

![image of small function](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu014.png)

`=Small(@Desktop)`

`=Small(Desktop)`

`Small(Budget)`: Returns the smallest value from the 'Budget' column.

`Small(Financials:Cost)`: Returns the smallest value from the 'Cost' column
in the 'Financials' table.
