---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Untag function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Untag function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/untag.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Untag function

*Applies to : TBM Studio 12.0 and later*

The Untag function tells the application to ignore any tags assigned to drivers in the current model.

## Where to use

- Formula columns in report tables
- Allocation source formulas

In an Advanced allocation formula in a model.

## Syntax

Untag(value)

## Arguments

value

Either a modeled or calculated metric, or a formula.

## Return type

The return type is the same as the argument column.

## Example

=SOURCE*Untag({Qualified CtB (Cost driver)})
