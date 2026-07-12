---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "LookupObjectUnitValue function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "LookupObjectUnitValue function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/lookupobjectunitvalue.html"
images:
  - "03-media/apptio-tbm-studio/aug559.png"
  - "03-media/apptio-tbm-studio/aug558.png"
  - "03-media/apptio-tbm-studio/lookupobjectunitvalue.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# LookupObjectUnitValue function

*Applies to : TBM Studio 12.0 and later*

Finds the value of a unit for an object. If the driver parameter is supplied, it looks up the total value of the driver specified.

The LookupObjectUnitValue function often is used to weight one cost driver against the calculated cost in another part of a model. Be careful not to create circular references in your calculations.

## Where to use

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text
- Allocation source formulas

## Syntax

LookupObjectUnitValue(object,metric,targetCol,lookupCol[,driver])

## Arguments

object

The name of the object that will provide a cost value.

metric

The name of the metric to look up. Often this is the same metric where you are using the function.

targetCol

The name of the column in the source table that will be matched to the lookupCol.

lookupCol

The name of the column in the matching table that will supply the lookup value.

driver

This is an optional parameter. If you specify a driver, it limits the function to the value being contributed by the specified driver. For example, if drivers A and B both contribute value to the unit C, then you could limit the LookupObjectUnitValue function to the value supplied by either driver A or driver B.

## Return type

String

## Example 1

Assume you have the following object and table in a model called Statistics:

As shown above, the Activity object has a unit identifier of Matching.Activity and a driver with the formula of =1. The formula produces the values in the Statistics column in the table above. The LookupObjectUnitValue function will use the values in the Statistics column to do the calculations.

You have placed the following Target table in a report:

You want to determine the number of activities associated with each server and display the result in the Number of Activities column in the Target table.

In the Number of Activities column you enter the following formula:

=LookupObjectUnitValue(Activity,Statistics,Server,Matching.Server)

- Activity is the name of the object.
- Statistics is the name of the model metric.
- Server is the name of the column in the Target table.
- Matching.Server is the name of the lookup column in the Activity object unit table.

## Example 2

Assume you have the cost model shown in the following image:

In the model, the Servers object values are allocated to the OS Direct object as shown. The result is 80% of the direct costs are allocated to Windows servers and 20% to Linux servers. The Shared object represents a single bucket of $600 dollars. You want to allocate the $600 dollars to the OS Indirect object in the same ratio as the costs for the OS Direct object.

To allocate the costs, you create two separate allocations from the Shared object to the OS Indirect object: one for Windows and one for Linux. For both allocations, you use the following formula:

=SOURCE*LookupObjectUnitValue(OS Direct,Cost,OS Indirect.OS,OS Direct.OS)/LookupObjectTotalValue(OS Direct,Cost)

In the formula, the $600 (SOURCE) is multiplied by the ratio of the LookupObjectUnitValue to the LookupObjectTotalValue.

To target each allocation to the correct operating system, you select the Some option in the Properties dialog and filter for either Windows or Linux.

- IPLookup
- Lookup and Lookup_Wild
- LookupEx
- LookupFromPath
- LookupMetric
- LookupObjectTotalValue
- LookupObjectTotalAllocated
- LookupObjectUnitAllocated
