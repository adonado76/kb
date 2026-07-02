---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Row function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/row.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Row function

Returns the index of the current row in the table, starting with zero for the first
row.

## Syntax

```
Row()
```

## Parameters

None

## Behavior

Evaluates to the zero-based index of the current row within the table. The first row is
numbered 0, the second is 1, and so on.

## Return type

Number

**Remarks**

This function can reference only the current table, not external tables.

Note that using the Row function as part of a formula that generates a primary Key column in a
table is **not** recommended. If you load new data into the table, the rows, and therefore
primary keys, can change and result in inaccurate allocations based on the key.

## Example

`=Row()`: Returns 0 for the first row, 1 for the second row, and so on.
