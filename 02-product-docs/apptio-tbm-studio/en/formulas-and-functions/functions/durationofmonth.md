---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "DurationOfMonth function"
breadcrumb: []
source_path: "formulas-and-functions/functions/durationofmonth.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DurationOfMonth function

Applies to: TBM Studio 12.0 and later

The DurationOfMonth function returns the number of days, hours, minutes, seconds, or milliseconds
in a month for a specific year. It takes into account leap years.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

`DurationOfMonth ("d/h/m/s/S", [month[, year]])`

## Return type

Number

## Arguments

*d/h/m/s/S*

> Enter one of the arguments.
>
> - d: day
> - h: hour
> - m: minute
> - s: seconds
> - S: milliseconds

*month*

> Enter the number of the month to be evaluated. Months are numbered from January, where January is
> 1 and December is 12.
>
> If this argument is left blank, the default is the current month. Can be used without the
> *year* argument.

Also, you can enter the name of a column or a formula. (Applies to: 12.2.1+)

*year*

> The year in which to evaluate the month.
>
> If this argument is left blank, the default is the current year. If this argument is specified,
> you also must specify the month argument.

## Examples

- Returns the number of days in the current month of the current
  year:`=DurationOfMonth("d")`
- Returns the number of hours in February of the current year:`=DurationOfMonth("h",
  2)`
- Returns the number of minutes in November 2011:

  ```
  =DurationOfMonth("m", 11, 2011)
  ```
