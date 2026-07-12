---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Left function"
breadcrumb: []
source_path: "formulas-and-functions/functions/left.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Left function

Applies to: TBM Studio 12.0 and later

Returns a specified number of characters from a string (including white spaces), starting from
the left.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

`Left(string[,count])`

## Arguments

*string*

> Any string. You can use a column name.

*count*

> An integer specifying the number of characters to be returned. If this argument is not specified,
> it defaults to 1. If this argument evaluates to a label or string, the system will try to convert it
> to a number. If it cannot, then the value will be zero.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Left("123456",3) | 123 |
| =Left("123456",1) | 1 |
| =Left("123456") | 1 |
| =Left("I like pie.",6) | I like |
| =Left("I like pie.") | I |

See also:

- [Mid](mid.htm "(Opens in a new tab or window)")
- [Right](right.htm "(Opens in a new tab or window)")
