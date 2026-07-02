---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Hours function"
breadcrumb: []
source_path: "formulas-and-functions/functions/hours.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Hours function

Applies to: TBM Studio 12.0 and later

Converts a specified date to a decimal value, which can be used in formulas. The decimal value is
the number of hours since January 1, 1970.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

`Hours(date_expression[,date_format])`

## Arguments

*date\_expression*

> An expression that evaluates to a date to be converted to a double value. Format is: "MM/DD/YYYY
> HH:MM," or any other standard date format supported by the application. See [DateFormat function](dateformat.htm "(Opens in a new tab or window)").

*date\_format*

> The format of the date that is being evaluated. Use this parameter only if the date is not in one
> of the standard data formats supported by the application. See [DateFormat function](dateformat.htm "(Opens in a new tab or window)").

## Return type

Number

## Example

Assume you have the following table:

| Ticket Source | Date Submitted |
| --- | --- |
| Presales | 2/2/2010 17:38 |
| CS | 3/10/2010 9:41 |
| Products | 3/9/2010 13:14 |

You create a third column called Hours using the following function:

> `=Hours(Date Submitted)`

The result is the following table:

| Ticket Source | Date Submitted | Hours |
| --- | --- | --- |
| Presales | 2/2/2010 17:38 | 351425.633 |
| CS | 3/10/2010 9:41 | 352281.683 |
| Products | 3/9/2010 13:14 | 352261.233 |

See also:

- [CurrentDate](currentdate.htm "(Opens in a new tab or window)")
- [Days](days.htm "(Opens in a new tab or window)")
- [Minutes](minutes.htm "(Opens in a new tab or window)")
- [Months](months.htm "(Opens in a new tab or window)")
