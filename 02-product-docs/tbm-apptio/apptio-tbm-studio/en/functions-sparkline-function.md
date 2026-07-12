---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Sparkline function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Sparkline function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/sparkline.html"
images:
  - "03-media/apptio-tbm-studio/aug499.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Sparkline function

*Applies to : TBM Studio 12.0 and later*

The Sparkline function creates small trend charts in the cells of tables on reports.

Sometimes, it is useful to display small trend graphs for the rows in a table. The Sparkline function is used for this purpose. An example is shown below:

## Where to use

- Formula columns in report tables
- Dynamic text
- Calculated metrics and reports with metric columns

## Syntax

Sparkline(past,future,column)

## Arguments

past

The number of periods to trend back in time. This is a positive number.

future

The number of periods to trend forward in time. This is a positive number.

column

The column to trend.

## Return type

Graph

## Example

The sparklines in Figure A above were created using this formula: Sparkline(4,4,Cost).

See also: Adding sparklines to a table .
