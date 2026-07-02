---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Value function"
breadcrumb: []
source_path: "formulas-and-functions/functions/value.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Value function

Applies to: TBM Studio 12.0 and later

Converts numeric-looking strings to numbers.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables

## Syntax

`Value(value[,pattern])`

## Arguments

*value*

> An expression that evaluates to the string to be converted.

*pattern*

> A pattern used for matching. The pattern can be either:
>
> - A suffix indicating that parsing should take the number up to the first non-numeric
>   character.
> - A full numeric pattern recognizable by [NumberFormat](numberformat.htm "(Opens in a new tab or window)").
>
> If *pattern* is not specified, the function makes a best guess and attempts to parse the
> *value* using one of the default number formats.

## Return type

Number

## Example

The following example evaluates the string in the column Storage and returns the numeric portion
of the string up to the characters GB. If Storage contains the string 57GB, this example returns
57.

> `=Value(Storage,"#GB")`
