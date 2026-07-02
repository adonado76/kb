---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Minutes function"
breadcrumb: []
source_path: "formulas-and-functions/functions/minutes.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Minutes function

Applies to: TBM Studio 12.0 and later

Converts a specified date to a decimal value, which can be used in formulas. The decimal value is
the number of minutes since January 1, 1970.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Minutes(date_expression)`

## Arguments

*date\_expression*

> An expression that evaluates to a date to be converted to a double value. The format is
> MM/DD/YYYY HH:MM or any other standard date format supported by the application.

## Return type

Number

## Example

Assume you want to calculate the duration of support calls. You have a data set with two columns:
SupportTicket\_Start and SupportTicket\_End. The data in the columns is in the format MMDDYYYY HH:MM.
You define a third column in the table to calculate the length of each call. The formula for the
third column is:

> `=(Minutes({SupportTicket_End}))-(Minutes({SupportTicket_Start}))`

The result is shown below:

![](../../../resources/images/studio_images/studioimages/studio/aug120.png)

See also:

- [CurrentDate](currentdate.htm "(Opens in a new tab or window)")
- [Days](days.htm "(Opens in a new tab or window)")
- [Elapsed](elapsed.htm "(Opens in a new tab or window)")
- [Hours](hours.htm "(Opens in a new tab or window)")
- [Months](months.htm "(Opens in a new tab or window)")
