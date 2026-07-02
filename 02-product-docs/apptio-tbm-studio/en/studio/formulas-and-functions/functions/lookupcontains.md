---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "LookupContains function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/lookupcontains.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupContains function

**Applies to**: TBM Studio 12.0 and later

Performs a multi-column partial-match lookup. The main use is for data cleansing using
one-to-many lookups (single source, multiple target columns) and many-to-one lookups (multiple
source, single target columns).

For a discussion of this function, see the blog [R12 Quick Guide: Lookup Contains](https://community.apptio.com/people/dmahan@apptio.com/blog/2017/02/04/r12-quick-guide-lookupcontains "(Opens in a new tab or window)") by Douglas Mahan.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables (though this is not recommended because of performance
  issues)
- Dynamic text

## Syntax

One-to-many lookups:

`LookupContains(sourceColumn,TargetTable,[targetCol1,TargetCol2,...TargetColN],TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false}))`

The function will return the value of the TargetTable:TargetValueColumnName for the row when the
following conditions are true:

1. The row has a match: the value of at least one of the target columns is "contained" in the value
   of the source column at that row (case sensitive contains determined by last optional flag).
2. The row has the maximum number of possible matches.
3. The row is unique (only one row with the maximum number of matching columns exists).

If only the first two conditions are true, and outputVariousOnMultipleMatches is true, the
function returns "{Various}", otherwise the function returns null.

Many-to-one lookups:

`LookupContains([sourceColumn1,..sourceColumnN],TargetTable,targetCol,TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false})`

The function will return the value of the TargetTable:TargetValueColumnName for the row when the
following conditions are true:

1. The row has a match: the value of at least one of the source columns is "contained" in the value
   of the target column (case sensitive contains determined by last optional flag).
2. The row has the maximum number of possible matches.
3. The row is unique (only one row with the maximum number of matching columns exists).

If only first two conditions are true, and outputVariousOnMultipleMatches is true, the function
returns "{Various}", otherwise the function returns null.

One-to-one lookups:

`LookupContains(sourceColumn,TargetTable,targetCol,TargetValueColumnName,caseSensitivity={true/false},outputVariousOnMultipleMatches={true/false},oneToOneBidirectional={true/false},oneToOneSourceToTarget={true/false})`

Analogous to the cases above, with an optional flag to specify if the match requires containment
in both directions (oneToOneBidirectional), or if the match requires containment only from the
source to target (oneToOneSourceToTarget).

## Arguments

sourceColumn

The column in the current table containing the value to search for. This value may be the name of
a column of type label. Lookup does not support numeric values in the source column.

TargetTable

The name of the table containing the return values. This must be a constant, and cannot reference
other columns or formulas.

targetCol

The column(s) in the target table in which to look for a match.

TargetValueColumnName

The column in the target table that supplies the return value.

If you place an equals sign (=) in front of the column name, the function will check the value in
the column in the source table. The value it finds will be used as the name of the column to use in
the target table. This allows the replacement column to be dynamic on a per row basis.

caseSensitivity={true/false}

Value can be true or false.

outputVariousOnMultipleMatches={true/false}

true: If there is more than one match, the function returns "{Various}."

false: If there is more than one match, the function returns null. [Is this correct, or does it
return the first or last match?]

oneToOneBidirectional={true/false}

true: The match requires containment in both directions.

false: The match requires containment in only one direction.

oneToOneSourceToTarget={true/false}

true: The match requires containment from a single source to a single target.

false: The match can have containment from more than one source to more than one target.

## Return type

The type of the lookup column.

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
