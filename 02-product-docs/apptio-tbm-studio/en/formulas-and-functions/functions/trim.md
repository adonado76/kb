---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Trim function"
breadcrumb: []
source_path: "formulas-and-functions/functions/trim.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Trim function

Applies to: TBM Studio 12.0 and later

Removes leading and trailing spaces from a specified string. It does not remove spaces within a
string.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Trim(expression)`

## Arguments

*expression*

> Evaluates to the string to be trimmed.

## Return type

String

## Examples

| Example Function | Return Value |
| --- | --- |
| =Trim(" server" ) | server (no leading spaces) |
| =Trim("server ") | server (no trailing spaces) |
| =Trim("server xyz") | server xyz |

Note in the last example that the spaces are not removed between the text within the string.
