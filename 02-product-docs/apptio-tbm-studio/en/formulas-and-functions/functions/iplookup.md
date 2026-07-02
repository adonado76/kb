---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "IPLookup function"
breadcrumb: []
source_path: "formulas-and-functions/functions/iplookup.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# IPLookup function

Applies to: TBM Studio 12.0 and later

Finds an IP address in a specified source column in the current table and searches for an IP
address in a specified column of a lookup table. IPLookup returns the value in the corresponding
specified replacement column of the lookup table for the last match it finds. IP addresses can be
entered individually or use masks and ranges.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables

## Syntax

`IPLookup(source_column,lookup_table,matching_column,replacement_column,"default_value")`

## Arguments

*source\_column*

> The column in the current table containing the IP address for which you want to search. Note:
> only enter the column name, not the table name.column name.

*lookup\_table*

> The name of the table containing the return values.

*matching\_column*

> The column in the *lookup\_table* in which to look for a match. The values can be in one of
> several formats:
>
> - Specific IP addresses such as 99.9.1.4.
> - IP address masks such as 99.1.0.0 where 0.0 will match any set of numbers. For example, 99.1.0.0
>   would include IP addresses such as 99.1.5.6, 99.1.9.234, and 99.1.43.144.
> - IP address ranges such as 99.1-99.6 which will match any IP ranges between the two values. For
>   example, the range 99.1-99.6 would include IP addresses such as 99.1.1.4, 99.3.1.54, and
>   99.6.6.6.

*replacement\_column*

> The column in the *lookup\_table* that supplies the return value.

*default\_value*

> The value to return if no match is found. The value must be in quotes.

## Return type

The type of either *replacement\_column* or *default\_value*, whichever applies.

## Example

Assume you have the following table called Machines that lists machines and their IP
addresses:

![](../../../resources/images/studio_images/studioimages/studio/aug032.png)

Based on the IP address, you want to fill in the Location column. You have the following table
called Locations that can supply the locations:

![](../../../resources/images/studio_images/studioimages/studio/aug033.png)

You enter the following in the Value Override field for the Location column in the Machines
table:

> ```
> =IPLookup(IP Address,Location,IP
>           Address,Location,"Unknown")
> ```

The result is:

![](../../../resources/images/studio_images/studioimages/studio/aug035.png)

Note:

- The first two machines have an IP address of 99.9.1.4 and are assigned to Altanta, not New York.
  That is because in the Locations table, the last reference for IP address 99.9.1.4 is Atlanta.
- 77.1.2.3 is not listed in the Locations table, so the value Unknown is returned.

See also:

- [Lookup and
  Lookup\_Wild](lookupandlookup_wild.htm "(Opens in a new tab or window)")
- [LookupEx](lookupexandlookupex_wild.htm "(Opens in a new tab or window)")
- [LookupFromPath](lookupfrompath.htm "(Opens in a new tab or window)")
- [LookupMetric](lookupmetric.htm "(Opens in a new tab or window)")
- [LookupObjectTotalAllocated](lookupobjecttotalallocated.htm "(Opens in a new tab or window)")
- [LookupObjectTotalValue](lookupobjecttotalvalue.htm "(Opens in a new tab or window)")
- [LookupObjectUnitAllocated](lookupobjectunitallocated.htm "(Opens in a new tab or window)")
- [LookupObjectUnitValue](lookupobjectunitvalue.htm "(Opens in a new tab or window)")
