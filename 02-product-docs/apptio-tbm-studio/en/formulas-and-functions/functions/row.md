---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Row function"
breadcrumb: []
source_path: "formulas-and-functions/functions/row.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Row function

Applies to: TBM Studio 12.0 and later

Returns the number of the current row in the current table, starting with zero for the first
row.

Note: For data imported from Excel, the return value for the 125th row is 124, because Excel starts
row numbering at 1.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables

Note: This function cannot be used in a column of a data set that is configured as a Key
column.

When used together, the result is that every time there is a recalculation, such as during data
entry, the Key column changes. This can result in data loss if used as a key for editable data, and
can result in inaccurate math and potential data loss when used as in a model object identifier.

## Syntax

```
Row(
        )
```

## Arguments

None

## Return type

Number

Remarks

This function can reference only the current table, not external tables.

Note that using the Row function as part of a formula that generates a primary Key column in a
table is not recommended. If you load new data into the table, the rows, and therefore
primary keys, can change and result in inaccurate allocations based on the key.

## Example

If the current row is the 100th row, the following example returns 100.

`=Row()`
