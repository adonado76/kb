---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "LookupEx function"
breadcrumb: []
source_path: "formulas-and-functions/functions/lookupexandlookupex_wild.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# LookupEx function

Applies to: TBM Studio 12.0 and later

LookupEx is the same as [Lookup and Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)"), except that LookupEx returns values for all matches rather than just
the last one. You must create a new column within the transformed table with the LookupEx, else it
is ignored.

The LookupEx function will add a row to the transform table for each match that it finds in a
second table. Essentially, it finds every possible combination between the two tables. Use this
function with caution as it can generate extremely large tables if your original tables are
themselves large.

NOTE: The column being populated by the function must be a new column added to the data
set transformed table.

## Where to use

This function can be used in:

- Data sets

Note: LookupEx cannot be nested in other functions, including IF statements.

## Syntax

```
LookupEx(source_column,lookup_table,matching_column,lookup_value_column
[,leave_original_value ][,replace_nulls][,ignore_case
        ])
```

## Arguments

*source\_column*

> The column in the current table containing the value to search for.

*lookup\_table*

> The name of the table containing the return values.

*matching\_column*

> The column in the lookup\_table in which to look for a match.

*lookup\_value\_column*

> The column in the lookup\_table that supplies the return value.

*leave\_original\_value*

> A boolean value (true or false) that controls the value that is returned if the value searched
> for is not found. If leave\_original\_value = true, LookupEx returns the value searched for; if false,
> LookupEx returns NULL. If this argument is not specified, it defaults to false.

*replace\_nulls*

> A boolean value (true or false) that controls the value that is returned when the value searched
> for is empty or null. If you enter true, it will search for a value in the replacement\_column whose
> corresponding value in the matching\_column is null. If there is more than one, it will take the last
> one found. If you enter false, a NULL value in the source\_column will remain null. If the
> matching\_column does not contain NULL or an empty value, the return value will be NULL.

*ignore\_case*

> A boolean value (true or false) that controls whether the lookup ignores case when comparing
> values from the source\_column to the matching\_column. If ignore\_case = true, LookupEx ignores case;
> if false, LookupEx is case-sensitive. If this argument is not specified, it defaults to false.

## Return type

The value of the lookup column. If there are multiple matches, the function returns
{VARIOUS}.

Notes:

- This function can have a significant impact on performance. It should be used only in data sets,
  never on a report.
- Only use one instance of this function in a table. If you use multiple instances, you will get
  incorrect results.
- If you are using the replace\_nulls or ignore\_case optional arguments, you must also specify the
  optional arguments that come before them.
- Do not use the standard curly braces { } to escape special characters or operators that might
  appear in column names being referenced. The Lookup function does not accept these.
- This function is not supported in the Ribbon formula bar or in the data preview function on the
  Data tab.

## Examples

Assume you have the following BU Cost Centers table:

![](../../../resources/images/studio_images/studioimages/studio/aug160.png)

You want to match each cost center category with the resources assigned to that category. To do
the matching, you have created the following Cost Category Resources table that lists the resources
for each category:

![](../../../resources/images/studio_images/studioimages/studio/aug161.png)

You add a new column to the BU Cost Centers table called Resources that uses the LookupEx
function. Below is the syntax for the function and the function as it would appear in the Resources
column.

> ```
> LookupEx(source_column,lookup_table,matching_column,replacement_column
> )
> ```
>
> ```
> =LookupEx(Cost Center Category,Cost Category
>             Resources,Cost Center
>       Category,Resources)
> ```

The result is shown in the following image. Note that the application added rows to the table for
each match it found. For example, there are three rows for the Development business unit
representing the three resources: Network, Applications, and Hardware.

![](../../../resources/images/studio_images/studioimages/studio/aug162.png)

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [Lookup and
  Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
