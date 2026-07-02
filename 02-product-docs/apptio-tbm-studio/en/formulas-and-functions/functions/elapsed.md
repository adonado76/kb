---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Elapsed function"
breadcrumb: []
source_path: "formulas-and-functions/functions/elapsed.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Elapsed function

Applies to: TBM Studio 12.0 and later

Calculates the time between two dates in seconds. To handle time period exclusions, the function
relies on an exclusions table.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables

## Syntax

```
Elapsed("startDate","endDate"["format",exclusion
      table[,startCol,endCol])
```

## Arguments

In the arguments below, all times must be enclosed in quotes.

*startDate*

> Beginning time. Format is: "MM/DD/YYYY HH:MM," or any other [standard date format](dateformat.htm "(Opens in a new tab or window)") supported by the application.

*endDate*

> Ending time. Format is: "MM/DD/YYYY HH:MM," or any other [standard date format](dateformat.htm "(Opens in a new tab or window)") supported by the application.

*format* (Applies to: v12.1, v12.2+)

> If you enter this argument (the word "format" in quotes), the function returns the value in
> Years, Days, Hours, Minutes, and Seconds.

*exclusion table*

> Optional argument that identifies an exclusions table that includes times that should be excluded
> from calculations.

*startCol*

> Optional argument that identifies the From time in the exclusions table.
>
> Format is: "MM/DD/YYYY HH:MM," or any other [standard date format](dateformat.htm "(Opens in a new tab or window)") supported by the application.

*endCol*

> Optional argument that identifies the To time in the exclusions table.
>
> Format is: "MM/DD/YYYY HH:MM", or any other [standard date format](dateformat.htm "(Opens in a new tab or window)") supported by the application.

## Return value

The number of seconds between the two dates. If the number is negative, the function returns
0.

## Exclusions table

To calculate spans of time that exclude non-working hours, holidays, etc., the function relies on
an exclusions table defined as a data set in your Apptio project. A sample exclusions table is shown
below. The Description column is ignored by the function.

| From | To | Description |
| --- | --- | --- |
| 00:00 Saturday | 00:00 Monday | Exclude weekends |
| 16:00 | 08:00 | Standard working hours are 8:00 A.M. to 4:00 P.M. |
| 1/1/2009 00:00 | 1/2/2009 00:00 | New Years Day |
| 1/18/2009 00:00 | 1/19/2009 00:00 | MLK Day |
| 2/15/2009 00:00 | 2/16/2009 00:00 | Presidents Day |
| 6/4/2009 00:00 | 6/5/2009 00:00 | July 4th |
| 12/25/2009 00:00 | 12/26/2009 00:00 | Christmas |

## Examples

The following example returns the number of seconds between 8:00 A.M. and 10:00 A.M. on April 23,
2010:

```
=Elapsed("04/23/2010 08:00","04/23/2010
        10:00")
```

- The following example returns the number of seconds between the time entered in a column called
  Date Submitted and a column called Date 1st Response:

  `=Elapsed(Date Submitted,Date 1st
  Response)`
- The following example returns the number of seconds between 6:00 P.M. Friday, April 23, 2010 and
  11:00 A.M. Monday, April 26, 2010. It references an exclusion table called Exclusions that blocks
  Saturdays and Sundays from calculations:

  `=Elapsed("04/23/2010 18:00","04/26/2010
  11:00",Exclusions,From,To)`
