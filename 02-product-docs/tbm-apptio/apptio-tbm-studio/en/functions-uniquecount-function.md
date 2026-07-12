---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "UniqueCount function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "UniqueCount function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/uniquecount.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# UniqueCount function

*Applies to : TBM Studio 12.0 and later*

Returns a count of distinct values in a column.

## Where to use

- Data sets
- Formula columns in report tables

## Syntax

UniqueCount(table name:column)

## Arguments

table name

The table to examine for distinct values.

column

The column to examine for distinct values. Note a colon is used between the table name and the column name. For example: Servers:Location.

## Return type

Number

## Example

Assume you have the following table:

| Server | Location |
| --- | --- |
| EXCH006 | Seattle |
| EXCH010 | Boston |
| NET207 | Boston |
| STOR124 | Seattle |
| STOR250 | Boston |
| STOR350 | Denver |

The following function, if executed against the Servers table above, returns 3, because the table contains 3 distinct locations.

See also : RowCount
