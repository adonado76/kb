---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "LookupObjectTotalAllocated function"
breadcrumb: []
source_path: "formulas-and-functions/functions/lookupobjecttotalallocated.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectTotalAllocated function

Applies to: TBM Studio 12.0 and later

Finds the per unit value allocated from a source object to one or more target objects in a model.
The function only works from the context of an object.

This function focuses on the source object, not the target objects. The function pulls the value
from the Assigned column in the .Unassigned table.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text
- Allocation source formulas

## Syntax

`LookupObjectTotalAllocated(metric)`

## Arguments

*metric*

> The value to be retrieved. Usually, this will be a model metric such as Cost.

## Return type

String

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [Lookup and
  Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
