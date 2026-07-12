---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Right function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Right function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/right.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Right function

*Returns the specified number of characters from the end (right side) of a string, including white spaces.*

## Syntax

Right(string[, count])

## Arguments

string : The string from which to extract characters from the right. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

count : The number of characters to return from the left. If the value is a string, it will be converted to a number. If conversion fails, the value defaults to 0. Optional (default: 1). An integer specifying the number of characters to be returned. If this argument is not specified, it defaults to 1. If this argument evaluates to a label or string, the system will try to convert it to a number. If it cannot, then the value will be zero.

## Behavior

- Extracts characters starting from the right side of the input string.
- Returns exactly the number of characters specified by the count parameter.
- If the count is greater than the string length, the entire string is returned.
- If count is omitted, 1 character is returned by default.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Right("123456", 3) | 456 |
| =Right("123456", 1) | 6 |
| =Right("123456") | 6 |
| =Right("I like pie", 3) | pie |
| Right({Hostname}, 5) | Returns the last 5 characters from the value in the {Hostname} column. |
| Right("network") | Returns "k" as the default count is 1. |
| Right("server", 3) | ver |
|  |  |
