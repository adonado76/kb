---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Sparkline function"
breadcrumb: []
source_path: "formulas-and-functions/functions/sparkline.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Sparkline function

Applies to: TBM Studio 12.0 and later

The Sparkline function creates small trend charts in the cells of tables on reports.

Sometimes, it is useful to display small trend graphs for the rows in a table. The Sparkline
function is used for this purpose. An example is shown below:

![](../../../resources/images/studio_images/studioimages/studio/aug499.png)

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic text
- Calculated metrics and reports with metric columns

## Syntax

`Sparkline(past,future,column)`

## Arguments

*past*

> The number of periods to trend back in time. This is a positive number.

*future*

> The number of periods to trend forward in time. This is a positive number.

*column*

> The column to trend.

## Return type

Graph

## Example

The sparklines in Figure A above were created using this formula: Sparkline(4,4,Cost).

See also: [Adding sparklines to a table](../../reports/tables/add-sparkline-column-to-tables.htm "(Opens in a new tab or window)") .
