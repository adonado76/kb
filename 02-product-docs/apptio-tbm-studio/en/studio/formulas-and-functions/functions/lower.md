---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Lower function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/lower.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lower function

Converts the input string to all lowercase. characters

## Syntax

`Lower(expression)`

## Parameters

*expression*: The text to convert to lowercase. Note: This parameter accepts an expression,
meaning you can provide a literal value, a column reference, or the result of another
function. Required

## Behavior

- Takes a string input and converts all alphabetical characters to their lowercase
  equivalents.
- Non-alphabetic characters (e.g., numbers, symbols) are returned unchanged.
- If the input is already lowercase, the original string is returned.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Lower("HWbudget" ) | hwbudget |
| =Lower("hwBudget") | hwbudget |
| Lower("Finance") | finance |
| Lower({Department Name}) | Converts all values in the {Department Name} column to lowercase. |

Note: Useful for standardizing text inputs for case-insensitive comparisons or consistent
formatting.
