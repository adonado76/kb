---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Eval function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/eval.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Eval function

**Applies to**: TBM Studio 12.0 and later

Takes a string that looks like an expression and evaluates it as if it were an expression.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic Text

## Where NOT to use:

- Transforms - use the [DynamicColumn](dynamic-column.htm "(Opens in a new tab or window)") function instead.

## Syntax

`Eval(string)`

## Arguments

*string*

A string that looks like an expression.

## Example

The following example returns 12.

`Eval("=24/2")`

To maximize the calc performance improvements of the new "precision calculations" feature, the
functionality of the Eval() function is replaced with DynamicColumn() or other code changes. The
customers that still have Eval() in their project configuration, can make the necessary changes
using the [OOTB Eval()
replacement code](../updated-eval-formulas.htm "(Opens in a new tab or window)") document that has information of all the reports and metric changes.

Note: If you have modified the OOTB reports, the Eval() will not be removed from reports in earlier
templates (e.g. ,v104, v105, v106. v107). Also see, [DynamicColumn](dynamic-column.htm "(Opens in a new tab or window)")
