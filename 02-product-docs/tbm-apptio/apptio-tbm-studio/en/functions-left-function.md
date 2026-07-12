---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Left function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Left function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/left.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Left function

*Returns a specified number of characters from a string (including white spaces), starting from the left.*

## Syntax

Left(string, count)

## Parameters

string : The string to extract characters from. You can also use a column reference. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

count : The number of characters to return from the left. If the value is a string, it will be converted to a number. If conversion fails, the value defaults to 0. Optional (default: 1)

## Behavior

Extracts characters from the beginning of the input string based on the count. If count is not specified, 1 character is returned.

## Return type

String

## Examples

- Left("Seattle", 3): Returns 'Sea'.
- Left(Name, 1): Returns the first character from the 'Name' column.
- Left("Location"): Returns 'L' since no count is provided and the default is 1.

| Example function | Return value |
| --- | --- |
| =Left("123456",3) | 123 |
| =Left("123456",1) | 1 |
| =Left("123456") | 1 |
| =Left("I like pie.",6) | I like |
| =Left("I like pie.") | I |
