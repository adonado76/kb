---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "SLN function"
breadcrumb: []
source_path: "formulas-and-functions/functions/sln.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SLN function

Applies to: TBM Studio 12.0 and later

Returns the straight-line depreciation of an asset for one year.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables
- Dynamic text
- Calculated metrics and reports with metric columns

## Syntax

`SLN(original,salvage,lifespan)`

## Arguments

*original*

> The original value of the asset being depreciated.

*salvage*

> The salvage value of the asset being depreciated.

*lifespan*

> The number of years to be depreciated over.

## Return type

Number

## Example

The following example calculates straight-line depreciation over 5 years for a $4000 asset with a
salvage value of $800. This function returns an annual depreciation value of 640.

> `=SLN(4000,800,5)`
