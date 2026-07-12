---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Len function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Len function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/len.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Len function

*Returns the number of characters in a given string, including spaces.*

## Syntax

Len(string_expression)

## Parameters

string_expression : The value to evaluate. Can be a literal string, a column reference, or a concatenated expression. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

## Behavior

- Evaluates the given expression and returns the total number of characters in the result.
- Counts all characters, including white spaces and punctuation.

## Return type

Number

## Examples

- In the following example, if the column Ticket Description for the current row contains the string Hardware, the function returns 8, which is the number of characters in the string Hardware. =Len({Ticket Description})
- In the following example, the string Support is added to the expression. So, if the column Ticket Description for the current row contains the string Hardware, the function returns 15, which is the number of characters in the string Hardware (8) plus the number of characters in the string Support (7). =Len("Support"+Ticket Description)
