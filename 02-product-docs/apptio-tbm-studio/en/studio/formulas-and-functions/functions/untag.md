---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Untag function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/untag.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Untag function

**Applies to**: TBM Studio 12.0 and later

The Untag function tells the application to ignore any tags assigned to drivers in the current
model.

## Where to use

This function can be used in:

- Formula columns in report tables
- Allocation source formulas

In an **Advanced** allocation formula in a model.

## Syntax

`Untag(value)`

## Arguments

*value*

Either a modeled or calculated metric, or a formula.

## Return type

The return type is the same as the argument column.

## Example

`=SOURCE*Untag({Qualified CtB (Cost driver)})`
