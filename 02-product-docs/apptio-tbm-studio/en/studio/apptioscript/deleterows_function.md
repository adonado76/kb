---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "DeleteRows function"
breadcrumb: []
source_path: "studio/apptioscript/deleterows_function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DeleteRows function

Use the DeleteRows() function to delete an existing table row based on values in
designated columns.

## Syntax

Note: If you run this script on filtered view of a table, only the filtered rows will be impacted by
the execution of delete rows script.

```
DeleteRows( date, tableName[columName1="value" OPERAND columName2="value" ...])
```

## date

Determines the date to modify the data set. For a list of valid date formats, see [DateFormat
function](../formulas-and-functions/functions/dateformat.htm "(Opens in a new tab or window)")

## tableName

The name of the data set, as indicated by the name of a table.

## columnName

The name of a column in the table noted in the tableName.

## value

The value in the row to delete.

## operand

Valid operands are AND and OR.

## Example 1

This example deletes all rows in the BuList dataset for the current date where either the BU
column equals "Sales" or the Other column equals
"Foo"

```
DeleteRows( CurrentDate(), BuList[BU="Sales" OR Other="Foo"])
```

## Example 2

This example deletes all rows from the BuList dataset from January 2010 where the BU column
equals "Sales" and the Date column = "Jan
2010".

```
DeleteRows( "January 2010", BuList[BU="Sales" AND Date="Jan 2010"])
```
