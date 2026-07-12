---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Upper function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/upper.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Upper function

Converts the input string to all uppercase characters.

## Syntax

`Upper(expression)`

## Parameters

*expression*: The text to convert to uppercase. Note: This parameter accepts an expression,
meaning you can provide a literal value, a column reference, or the result of another
function. Required

## Behavior

- Takes a string input and converts all alphabetical characters to their uppercase
  equivalents.
- Non-alphabetic characters (e.g., numbers, symbols) are returned unchanged.
- If the input is already uppercase, the original string is returned.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Upper("HWbudget" ) | HWBUDGET |
| =Upper("hwBudget") | HWBUDGET |

Note: Useful for standardizing text inputs for case-insensitive comparisons or consistent
formatting.
