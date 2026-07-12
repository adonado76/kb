---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Use_Map_Grid function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Use_Map_Grid function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/usemapgrid.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Use_Map_Grid function

*Applies to : TBM Studio 12.0 and later*

For table-based allocations, specifies one-to-one unit mappings and a percentage of the source unit's value. This function replaces the Use_Map_Table .

## Where to use

In an Advanced allocation formula in a model.

## Syntax

Use_Map_Grid(table:source_column[,notation])

## Arguments

table

References a mapping table.

source_column

Specifies the source unit column name.

notation

- percent = A whole number that specifies a percent weighting (can be n or n %).
- ratio = A whole number, divided by the total to get a decimal value.

If notation is not specified, the numbers are assumed to already be a decimal value (for example, 0.25 = 25%).

## Return type

The type of the columns in the matching table.

## Remarks

The table will have a single column (which is specified in the function). All the rest of the columns are target unit columns.
