---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "LookupObjectUnitAllocated function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/lookupobjectunitallocated.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectUnitAllocated function

**Applies to**: TBM Studio 12.0 and later

Looks up the value allocated between two objects for a particular metric on a unit-by-unit
basis.

## Where to use

This function can be used in:

- Reports with modeled metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

```
=LookupObjectUnitAllocated(sourceObject,destObject,metric,
columnInLocalTable,columnInSourceObjectTable)
```

## Arguments

*sourceObject*

The object providing the value.

*destObject*

The object receiving the value.

*metric*

The name of the metric to look up.

*columnInLocalTable*

The name of the column in the target table that identifies the units.

*columnInSourceObjectTable*

The column in the source table that identifies the units.

## Return type

String

**Notes**:

The Apptio Billing application uses this function in conjunction with the LookupObjectUnitValue
function to determine the total quantity of a service being consumed from within a pricing style
model.

If you are using this function with !NEWCOLUMN while editing a data path, you will generally need
to specify the [canSum] keyword on the !NEWCOLUMN because it cannot recalculate with different
grouping parameters.

## Example

The following data path example determines the cost allocated from the Support object to the
Services object. The value is taken from the units in the Support.ID column and allocated to the
units in the Services.ID column.

```
!NEWCOLUMN[alloc=LookupObjectUnitAllocated
(Support,Services,Cost,ID,ID)][canSum]
```

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [Lookup and
  Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
