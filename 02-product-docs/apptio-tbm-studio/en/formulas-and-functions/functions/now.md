---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Now function"
breadcrumb: []
source_path: "formulas-and-functions/functions/now.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Now function

Applies to: TBM Studio 12.0 and later

The Now( ) function returns the current date and time as a UNIX time stamp based on the server
time. The time is based on the time the function is executed. The result is cached on disk, across
restarts, etc. It is updated only when a full recalculation is performed.

## Where to use

This function can be used in:

- Formula columns in report tables
- Dynamic text

## Syntax

`Now()`

## Arguments

None

## Return type

UNIX Time Stamp

## Example

The following example determines the number of days remaining until the end date. In the example,
End Date is the name of a column. TRUNC is a function that removes the fractional part of the
number.

> ```
> =TRUNC(Days(End
>       Date)-Days(Now()))+1
> ```

Notes:

- The Now function cannot be used in transform tables because it will not update. If a Now
  function was added to a Release 8 transform table, it must be removed.
- You can format the date using the [DateFormat](dateformat.htm "(Opens in a new tab or window)") function.For example:`=DATEFORMAT(Now(),"MMddYY")`

See also:

- [CurrentDate](currentdate.htm "(Opens in a new tab or window)")
