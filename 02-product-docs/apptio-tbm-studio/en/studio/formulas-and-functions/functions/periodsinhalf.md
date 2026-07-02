---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "PeriodsInHalf function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/periodsinhalf.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# PeriodsInHalf function

**Applies to**: TBM Studio and later

Returns the number of periods in the first or second half of the year.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables
- Dynamic text

## Syntax

`PeriodsInHalf(half)`

## Arguments

*Half*

The number of the half, either 1 or 2 for the first or second half.

## Return type

String

## Example

Given a 13-period project, and period set to P10 FY2013, the following function returns the
results shown below.

| Function | Return |
| --- | --- |
| PeriodsInHalf(1) | 6 |
| PeriodsInHalf(2) | 7 |
