---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "LookupObjectTotalValue function"
breadcrumb: []
source_path: "formulas-and-functions/functions/lookupobjecttotalvalue.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupObjectTotalValue function

Applies to: TBM Studio 12.0 and later

Finds the total value of an object. If the metric parameter is not used, the function uses the
current model. If the driver parameter is supplied, it looks up the total value of the driver
specified.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Model metrics
- Formula columns in report tables
- Dynamic text
- Allocation source formulas

## Syntax

*LookupObjectTotalValue(object [,metric [, driver]])*

## Arguments

*object*

> The name of the target object. The object must not be above the current level in the model
> hierarchy where the function is being used.

*metric*

> If specified, returns the value of the metric as it applies to the object.
>
> If not specified, returns the value of the object in the current model.

*driver*

> If specified, returns the value of the driver. The driver must be a driver associated with the
> object.

## Return type

String

## Examples

Assume you have the cost model shown in the following image. Object C has two drivers: Object A
and Object B.

![](../../../resources/images/studio_images/studioimages/visio%20diagrams/lookupobjecttotalvalue.png)

You want to be able to use the value of Object A elsewhere in the model. You would use the
following function:

> ```
> =LookupObjectTotalValue(Object
>       A,Cost)
> ```

The function would return the value $7M.

Now, suppose you want to find the value of Object C that is contributed by the driver from Object
A. You would use the following function:

> ```
> =LookupObjectTotalValue(Object C,Cost,Object
>       A)
> ```

In the function, Object A is the name of the driver coming from Object A.

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [Lookup and
  Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
