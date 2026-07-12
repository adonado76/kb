---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Trim function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/trim.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Trim function

Removes leading and trailing spaces from a specified string. It does not remove spaces
within a string.

## Syntax

`Trim(expression[, trimUnicodeWhitespace][, additionalCharacters])`

## Parameters

- *expression*: The string to trim. Leading and trailing whitespace will be removed.
  Note: This parameter accepts an expression, meaning you can provide a literal value, a
  column reference, or the result of another function. Required
- *trimUnicodeWhitespace*: Optional. A boolean value (true or false) that specifies
  whether to trim all Unicode whitespace characters. If omitted, defaults to false. Optional
  (default: false)
- *additionalCharacters*: Optional. A string of additional characters to remove from
  both ends of the input. This is in addition to whitespace. Must be enclosed in double
  quotes (e.g., "\*"). Optional

## Behavior

- Removes standard or Unicode whitespace from the beginning and end of the input string.
- Does not alter whitespace or characters located within the body of the string.
- If additional characters are specified, those are also removed from both ends of the
  string.

## Return type

String

## Examples

| Example Function | Return Value |
| --- | --- |
| =Trim(" server" ) | server (no leading spaces) |
| =Trim("server ") | server (no trailing spaces) |
| =Trim("server xyz") | server xyz |
| Trim({Description}, true, "\*") | Removes leading/trailing Unicode whitespace and asterisks from values in the {Description} column. |

Note in the 3rd example that the spaces are not removed between the text within the string.
