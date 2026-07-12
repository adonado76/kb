---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Mid function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Mid function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/mid.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Mid function

*Returns a specified number of characters from a string, starting at a given position from the left.*

## Syntax

Mid(string,start,count)

## Parameters

- string : The text string from which characters will be extracted. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required
- start : An integer representing the position of the first character to return, starting from the leftmost character (1-based index). Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required
- count : An integer representing the number of characters to return. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

## Behavior

- Extracts a substring from the input text based on the provided start position and length.
- The position is 1-based, meaning Mid("abc", 1, 1) returns "a".
- If count exceeds the number of characters available from the start position, it returns characters up to the end of the string.

## Return type

String

## Examples

| Example function | Return value |
| --- | --- |
| =Mid("123456", 2, 3) | 234 |
| =Mid("123456", 1, 2) | 12 |
| =Mid("123456", 4, 1) | 4 |
| =Mid("I like pie.", 3, 4) | like - starts at position 3 and returns 4 characters, including whitespace. |
