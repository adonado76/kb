---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Lookup and Lookup_Wild functions"
breadcrumb: []
source_path: "formulas-and-functions/functions/lookupandlookup_wild.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lookup and Lookup_Wild functions

Applies to: TBM Studio 12.0 and later

Finds the value in a specified source column in the current table and in a specified column of a
lookup table. Lookup and Lookup\_Wild return the value in the corresponding specified replacement
column of the lookup table. If two or more values are found in the lookup table, the value {Various}
is returned. The only difference between the two functions is that Lookup\_Wild supports regular
expressions in the matching column and Lookup does not.

To increase row count by creating a new row for every return value instead of {Various}, use
[LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)").

If you are using Lookup to bring in a numeric value, and you want the values summed instead of
returning various, use the [Data
lookup](../data-lookup.htm "(Opens in a new tab or window)") syntax.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables (Though this is not recommended. Use inference instead.)
- Data Mapper
- Dynamic Text

## Replaces

There are new versions of Lookup and Lookup\_Wild functions that replace the old versions. If
there are old versions that you have used, the application renames them to Lookup\_Old and
Lookup\_Wild\_Old. DO NOT EDIT THESE OLD VERSIONS. If you need to make changes to these functions,
delete them and enter new Lookup and Lookup\_Wild functions.

## Syntax

`Lookup(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

`Lookup_Wild(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])`

## Arguments

*source\_column*

> The column in the current table containing the value to search for. This value may be the
> name of a column of type label. Lookup does not support numeric values in the source column. You can
> include two or more matching source columns by using the operator "&" (performs both tests) or
> "&&" (performs second test only if first test is true). You must include the same number of
> columns in the matching\_column parameter.
>
> NOTICE
>
> The column cannot be type
> "Numeric".

*lookup\_table*

> The name of the table containing the return values. This must be a constant, and cannot reference
> other columns or formulas.

*matching\_column*

> The column in the *lookup\_table* in which to look for a match. If using Lookup\_Wild, you
> can enter regular expressions in the column. For information on regular expressions, search the
> Web.
>
> You can include two or more matching columns by using the operator "&" (performs both
> tests) or "&&" (performs second test only if first test is true).
>
> NOTICE
>
> The
> column cannot be type "Numeric".

*replacement\_column*

> The column in the lookup\_table that supplies the return value.
>
> If you place an equals sign (=) in front of the column name, the function will check the value in
> the column in the source table. The value it finds will be used as the name of the column to use in
> the lookup\_table. This allows the replacement column to be dynamic on a per row basis.

*leave\_original\_value*

> A boolean value (true or false) that controls the value that is returned if the value searched
> for is not found. If leave\_original\_value = true, Lookup returns the value searched for; if false,
> Lookup returns a blank cell. If this argument is not specified, it defaults to false.

*replace\_nulls*

> A boolean value (true or false) that controls the value that is returned when the value searched
> for is empty or null. If you enter true, it will search for a value in the replacement\_column whose
> corresponding value in the matching\_column is null. If you enter false, a NULL value in the
> source\_column will remain null. If the matching\_column does not contain NULL or an empty value, the
> return value will be NULL. This value defaults to false.

*ignore\_case*

> A boolean value (true or false) that controls whether the lookup ignores case when comparing
> values from the source\_column to the matching\_column. If ignore\_case = true, Lookup ignores case; if
> false, Lookup is case-sensitive. If this argument is not specified, it defaults to false. The Lookup
> operation will be faster when ignore\_case is false, so only change this when needed.

## Return type

The type of the lookup column.

Notes:

- If the LookUp function finds multiple matching rows, it returns {Various} instead of a
  null.
- If you are using the *replace\_nulls* or *ignore\_case* optional arguments, you also
  must specify the optional arguments that come before them.
- Use the standard curly braces { } to escape special characters or operators that might appear in
  column names being referenced. For example, {P&L Rate}.
- Inference linking multiple tables is preferable to doing lookups and can be used anytime the
  resulting column is not needed in a data set.

## Lookup example

Assume you have the following table called Data Centers that lists data centers and their
location:

![](../../../resources/images/studio_images/studioimages/studio/aug036.png)

Based on the location, you want to fill in the Time Zone column. You have the following table
called Time Zone that can supply the GMT offset.

![](../../../resources/images/studio_images/studioimages/studio/aug037.png)

You enter the following in the Value Override field for the Location column in the Data Centers
table:

> ```
> =Lookup(Location,Time Zone,City,Time
>       Zone)
> ```

The result is:

![](../../../resources/images/studio_images/studioimages/studio/aug039.png)

See also:

- [IPLookup](iplookup.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
