---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Substitute function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Substitute function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/substitute.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Substitute function

Searches a specified target string for the presence of a specified search string. If the search string is found, it replaces it with a specified replacement string.

## Syntax

Substitute(target_string, search_string, replacement_string)

## Parameters

target_string : The string in which to search and perform the replacement. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

search_string : The substring to search for within the target string. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

replacement_string : The string to use as a replacement for each occurrence of the search string. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

## Behavior

- Replaces all occurrences of the search string within the target string with the replacement string.
- Matching is case-sensitive.
- If the search string is not found, the original string is returned unchanged.

## Return type

String

## Example

The following example searches all occurrences of virtual server and replaces virtual with physical .

=Substitute("virtual server", "virtual", "physical")

The following example searches for single quotes and replaces them with nothing, essentially removing the single quotes from the string. This can be useful if you are importing data from Excel and some, but not all, of the entries have a leading single quote.

=Substitute(Billing ID,"'","")

Substitute({Server Type}, "legacy", "modern") : Replaces 'legacy' with 'modern' in all values of the {Server Type} column.
