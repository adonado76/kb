---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "CapFirstLetter function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/capfirstletter.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CapFirstLetter function

Capitalizes the first letter of each word in the string argument, and makes all other
letters lowercase.

## Syntax

`CapFirstLetter(text)`

## Parameters

*text*: A string value or an expression that evaluates to a string. This can include static
text, column references, or other string-producing formulas. Optional

## Behavior

- Each word in the input string will have its first character converted to
  uppercase.
- All other characters in each word will be converted to lowercase.
- Words are typically separated by spaces or punctuation.

## Return type

String

## Example

- `CapFirstLetter("hello world")`: Returns "Hello World"
- `CapFirstLetter(User Name)`: Capitalizes the first letter of each word in
  the UserName field.
- `CapFirstLetter("tHiS is a tEsT")`: Returns "This Is A Test".

Note: Useful for formatting names, titles, or other text fields to follow proper
capitalization conventions. If the input already follows the desired capitalization, the
result remains unchanged.
