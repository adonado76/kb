---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Find function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/find.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Find function

Returns the position of the first occurrence of a search string within another string,
starting at an optional position. This function is case-sensitive.

Find is the same as [Search](search.html), except
that Find is case sensitive.

## Syntax

`Find(search_string, in_string, [starting_position])`

## Parameters

- *search\_string*: The substring to search for. Note: This parameter accepts an
  expression, meaning you can provide a literal value, a column reference, or the result of
  another function. Required
- *in\_string*: The string to search in. You may also provide the name of a column.
  Note: This parameter accepts an expression, meaning you can provide a literal value, a
  column reference, or the result of another function. Required
- *starting\_position*: The position to start searching from (1-based index). Note:
  This parameter accepts an expression, meaning you can provide a literal value, a column
  reference, or the result of another function. Optional (default: 1)

## Behavior

- Performs a case-sensitive search for a substring inside another string.
- Returns the position (starting at 1) of the first match found.
- Returns 0 if the substring is not found.
- If starting\_position is not provided, the search begins from the start of the string.
- The function behaves like Search, but it is case-sensitive.

## Examples

- Find("Functional", "58762 Functional Actuals"): Returns 7, the position of the substring
  'Functional'.
- Find("c", "58762 Functional Actuals", 12): Returns 19, starting the search after the
  12th character.
- Find("99", "58762 Functional Actuals"): Returns 0, since '99' is not found.
- LEFT(IP, Find(".", IP, Find(".", IP) + 1)): Returns the first two octets of an IP
  address. For example, for '10.10.1.113' the result is '10.10'.

Note: The Find function is case-sensitive. If you need a case-insensitive search, use the
Search function instead. All parameters accept expressions (e.g., literals, columns, or
nested functions).

## Return Type

Number
