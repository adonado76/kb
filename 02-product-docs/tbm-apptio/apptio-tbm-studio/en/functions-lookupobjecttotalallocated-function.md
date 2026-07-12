---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "LookupObjectTotalAllocated function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "LookupObjectTotalAllocated function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/lookupobjecttotalallocated.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# LookupObjectTotalAllocated function

*Applies to : TBM Studio 12.0 and later*

Finds the per unit value allocated from a source object to one or more target objects in a model. The function only works from the context of an object.

This function focuses on the source object, not the target objects. The function pulls the value from the Assigned column in the .Unassigned table.

## Where to use

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text
- Allocation source formulas

## Syntax

LookupObjectTotalAllocated(metric)

## Arguments

metric

The value to be retrieved. Usually, this will be a model metric such as Cost.

## Return type

String

- IPLookup
- Lookup and Lookup_Wild
- LookupEx
- LookupFromPath
- LookupMetric
- LookupObjectTotalValue
- LookupObjectUnitAllocated
- LookupObjectUnitValue
