---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "PeriodsInQuarter function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "PeriodsInQuarter function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/periodsinquarter.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# PeriodsInQuarter function

*Applies to : TBM Studio and later*

Returns the number of periods in the first, second, third, or fourth quarter.

## Where to use

- Data sets
- Formula columns in report tables
- Dynamic text

## Syntax

PeriodsInQuarter(quarter)

## Arguments

quarter

The number of the quarter, either 1, 2, 3, or 4.

## Return type

String

## Example

Given a 13-period project with the third quarter having four periods, and the calendar picker set to P10 FY2013, the following function returns the results shown below:

| Function | Return |
| --- | --- |
| PeriodsInQuarter(1) | 3 |
| PeriodsInQuarter(2) | 3 |
| PeriodsInQuarter(3) | 4 |
| PeriodsInQuarter(4) | 3 |
