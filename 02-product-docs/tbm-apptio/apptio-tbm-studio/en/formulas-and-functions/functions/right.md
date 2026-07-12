---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Right function"
breadcrumb: []
source_path: "formulas-and-functions/functions/right.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Right function

Applies to: TBM Studio 12.0 and later

Returns a specified number of characters from a string (including white spaces), starting from
the right.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Right(string[,count])`

## Arguments

*string*

> Any string.

*count*

> An integer specifying the number of characters to be returned. If this argument is not specified,
> it defaults to 1. If this argument evaluates to a label or string, the system will try to convert it
> to a number. If it cannot, then the value will be zero.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Right("123456", 3) | 456 |
| =Right("123456", 1) | 6 |
| =Right("123456") | 6 |
| =Right("I like pie", 3) | pie |

See also:

- [Left](left.htm "(Opens in a new tab or window)")
- [Mid](mid.htm "(Opens in a new tab or window)")
