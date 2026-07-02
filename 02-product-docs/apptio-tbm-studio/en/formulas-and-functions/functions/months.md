---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Months function"
breadcrumb: []
source_path: "formulas-and-functions/functions/months.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Months function

Applies to: TBM Studio 12.0 and later

Converts a specified date to a decimal value which can be used in formulas. The decimal value
represents the number of periods since January 1, 1970.

The number returned is the number of periods. Partial periods are represented by decimals. For
example: 1.1 periods would represent approximately one period and three days.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Months(date_expression)`

## Arguments

*date\_expression*

> An expression that evaluates to a date to be converted to a double value. Format is: "MM/DD/YYYY
> HH:MM" or any other standard date format supported by the application. The expression can be the
> name of a column.

## Return type

Number

## Example

The following example subtracts the number of months from the project start date to the project
end date, and then multiplies the result by the cost per month.

> `=((Months(ProjectEnd)-Months(ProjectStart))*ProjectCostPerMonth)`

See also:

- [CurrentDate](currentdate.htm "(Opens in a new tab or window)")
- [Days](days.htm "(Opens in a new tab or window)")
- [Hours](hours.htm "(Opens in a new tab or window)")
- [Minutes](minutes.htm "(Opens in a new tab or window)")
