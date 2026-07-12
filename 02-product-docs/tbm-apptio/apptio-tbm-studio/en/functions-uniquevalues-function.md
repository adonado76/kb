---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "UniqueValues function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "UniqueValues function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/uniquevalues.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# UniqueValues function

Returns a list of unique values in a column.

## Where to use

- Data sets
- Formula columns in report tables
- Dynamic text
- Any place where you can add a condition filtering clause.

## Syntax

UniqueValues(table:column1,true)

UniqueValues(table:column1[column2=columnA],true)

## Arguments

table:column

The table and column to examine for distinct values. The table cannot be the same as current table.

table:column[column2=columnA]

If a match criterion in brackets [] is added after the table:column specification, the return values are limited to values which match between two tables.

column2 is a column in the foreign table

columnA is a column in the current table

true

If this parameter is included, blank and null values will be excluded from the list.

For example, assume you have the following data:

| Col A | Col B |
| --- | --- |
| F1 | A |
| F2 | B |
| F3 |  |

If you specify =UniqueValues(ColB), you will get: “null”,”A”,”B”.

If you specify =UniqueValues(ColB,true), you will get: “A”,”B”.

## Return type

Comma separated list of unique values in the designated column.

## Example

Assume you have the table below:

| Server | Location |
| --- | --- |
| EXCH006 | Seattle |
| EXCH010 | Boston |
| NET207 | Boston |
| STOR124 | Seattle |
| STOR250 | Boston |
| STOR350 | Denver |

The following function, if executed against the Servers table above, returns three values: Seattle, Boston, Denver.

=UniqueValues(Servers:Location)

Another application of this function is to return a list of concatenated email addresses from a column in a table to use with the SendMail Apptio Script API.
