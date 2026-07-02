---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "CapFirstLetter function"
breadcrumb: []
source_path: "formulas-and-functions/functions/capfirstletter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CapFirstLetter function

Applies to: TBM Studio 12.0 and later

Capitalizes the first letter of each word in the string argument, and makes all other letters
lowercase.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`CapFirstLetter(string)`

## Arguments

*string*

> One or more words.

## Return type

String

## Example

The following would return "Data Center Budget."

`=CapFirstLetter(DATA CENTER BUDGET)`

## See also

- [Lower](lower.htm "(Opens in a new tab or window)")
- [Upper](upper.htm "(Opens in a new tab or window)")
