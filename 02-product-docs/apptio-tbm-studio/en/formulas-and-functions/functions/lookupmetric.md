---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "LookupMetric function"
breadcrumb: []
source_path: "formulas-and-functions/functions/lookupmetric.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupMetric function

Applies to: TBM Studio 12.0 and later

Looks up a column from another metric using the same data path. It takes the current path,
substitutes a new metric, and re-runs the model before looking up a value in a specified column.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables

Use to look up a metric in the current data path that is not normally available.

## Syntax

`LookupMetric(metric,column)`

## Arguments

*metric*

> The name of the metric to use.

*column*

> The column in the new table to look up.

## Return type

Metric

## Example

This example results in an AssignmentRatios table that has an additional column named
{NewCol}.

> ```
> demo.apptio.com:BanksDemo/
> CostModels/
> Default/
> Cost/
> 1199145600000/
> Services/
> .Drivers/
> Servers/
> !FILTER[ServerCMDB.Server Product="ASP.NET"]/
> !GROUPBY[ServerCMDB.Server Product]/
> .AssignmentRatios/
> !NEWCOLUMN[{NewCol}=LookupMetric(Chargeback,{ASP.NET})]/
> ```

The value for the {NewCol} column is provided by the LookupMetric function referencing the
{ASP.NET} column of the following table:

> ```
> demo.apptio.com:BanksDemo/
> CostModels/
> Default/
> ```
>
> `Chargeback`
>
> ```
> /
> 1199145600000/
> Services/
> .Drivers/
> Servers/
> !FILTER[ServerCMDB.Server Product="ASP.NET"]/!GROUPBY[ServerCMDB.Server
>               Product]/
> .AssignmentRatios/
> ```

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [Lookup and
  Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
