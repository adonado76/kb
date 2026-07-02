---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "RowCount_EditableTable() function"
breadcrumb: []
source_path: "formulas-and-functions/functions/rowcount-editabletable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RowCount_EditableTable() function

Applies to: TBM Studio 12.11.3 and later

Returns a count of the total number of rows in an editable table.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables

## Syntax

`RowCount([editabletable])`

## Arguments

*table*

> Indicates which editable table to count. If you do not specify an editable table, it returns the
> count for the current editable table. You cannot enter the current editable table name as an
> argument.

## Return type

Number

## Example

In the following example, if the editable table Servers has 180 rows, the function returns
180.

> `=RowCount(Servers)`

See also: [UniqueCount](uniquecount.htm "(Opens in a new tab or window)")
