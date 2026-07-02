---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Lower function"
breadcrumb: []
source_path: "formulas-and-functions/functions/lower.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lower function

Applies to: TBM Studio 12.0 and later

Converts a specified string to lowercase.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Lower(expression)`

## Arguments

*expression*

> Evaluates to the string to be converted. The expression can reference a column.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Lower("HWbudget" ) | hwbudget |
| =Lower("hwBudget") | hwbudget |

See also:

- [Upper](upper.htm "(Opens in a new tab or window)")
- [CapFirstLetter](capfirstletter.htm "(Opens in a new tab or window)")
