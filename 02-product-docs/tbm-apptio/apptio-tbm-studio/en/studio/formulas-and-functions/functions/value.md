---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Value function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/value.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Value function

Converts a numeric-looking string into a number using an optional formatting pattern.
Useful for extracting numeric values from strings that include text or symbols.

## Syntax

`Value(value, pattern)`

## Parameters

*value*: The string expression to convert into a number. Note: This parameter accepts an
expression, meaning you can provide a literal value, a column reference, or the result of
another function. Required

*pattern*: Optional. A pattern used for matching and parsing the numeric value. It can be a
suffix pattern (e.g., "#GB") or a full numeric pattern as used in NumberFormat. If omitted,
the function will attempt to infer the correct format. Optional

A pattern used for matching. The pattern can be either:

- A suffix indicating that parsing should take the number up to the first non-numeric
  character.
- A full numeric pattern recognizable by [NumberFormat](numberformat.html "Formats a numeric value into a label (string) using custom patterns for positive and negative numbers, durations, or data size formatting. This function is designed for use in Label-type columns.").

If *pattern* is not specified, the function makes a best guess and attempts to parse the
*value* using one of the default number formats.

## Return type

Number

## Example

The following example evaluates the string in the column Storage and returns the numeric portion
of the string up to the characters GB. If Storage contains the string 57GB, this example
returns 57. : `=Value(Storage,"#GB")`

`Value("$1,234.56")`: Parses the string and returns the numeric value
1234.56.

Note: If parsing fails, the function returns null.
