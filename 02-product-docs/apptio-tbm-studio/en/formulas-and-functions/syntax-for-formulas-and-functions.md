---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Syntax for formulas and functions"
breadcrumb: []
source_path: "formulas-and-functions/syntax-for-formulas-and-functions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Syntax for formulas and functions

Applies to: TBM Studio 12.0 and later

In addition to basic syntax conventions for formula and function code, the function syntax
includes rules for:

- Data Lookup - Referencing the current table (internal lookup) and other tables (external
  lookup).
- Referencing Column Names - When referencing column names, the best practice is to enclose
  column names in curly braces, and this is required when column names contain special
  characters.
- Operators - Standard operators are supported as well as rollup operators, which reference
  the source or target units of a data rollup.
- String Concatenation - You can format formulas to include combine strings such as units
  of measure with calculated values.

## Syntax conventions

The information below employs the following conventions to describe function syntax.

- Monospace - This document presents all function syntax in monospace.
- MixedCase monospace - Function names are shown in MixedCase, but function names are not
  case sensitive.
- [ ] (brackets) - Optional elements. (Do not type the brackets.)
- ,...n - Indicates that the preceding argument can be repeated any number of times,
  separated by commas.

## Spaces

Do not put spaces in formulas, except as part of a quoted string or as needed in column names. In
this document, the syntax specifications may include spaces to enhance readability, but all examples
are given without spaces. The syntax in these help documents employs monospace font and spaces to
enhance readability. However, spaces should not be used when writing formulas and functions in the
application.

## Strings

Enclose all strings in double-quotes ( " " ).

For example:

"Total Costs for Year 2009"

Column names are not considered strings and do not have to be enclosed in double-quotes.

To escape a quote symbol, use double quotes ("" "").

## Null return values

Functions that resolve to 0 or to null display as 0 in the field.
