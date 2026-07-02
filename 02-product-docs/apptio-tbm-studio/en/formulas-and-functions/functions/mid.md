---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "***"
breadcrumb: []
source_path: "formulas-and-functions/functions/mid.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ***

## Mid function

Applies to: TBM Studio 12.0 and later

Returns a specified number of characters from a string (including white spaces), starting a
specified number of characters from the left.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

*Mid(string,start,count)*

## Arguments

*string*

> Any string.

*start*

> An integer specifying the starting point of the return string relative to the leftmost character.
> For example, if *start* = 3, the return string begins with the third character from the
> left.

*count*

> An integer specifying the number of characters to be returned.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Mid("123456",2,3) | 234 |
| =Mid("123456",1,2) | 12 |
| =Mid("123456",4,1) | 4 |
| =Mid("I like pie.",3,4) | like |

See also:

- [Left](left.htm "(Opens in a new tab or window)")
- [Right](right.htm "(Opens in a new tab or window)")
