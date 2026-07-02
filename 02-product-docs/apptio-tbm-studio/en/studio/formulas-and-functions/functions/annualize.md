---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Annualize function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/annualize.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Annualize function

**Applies to**: TBM Studio 12.0 and later

The Annualize function calculates the average period value to date for a metric, and then
multiplies that value by the number of periods to project the total annual value for the fiscal
year. This function is most often used to project actual values such as cost and units rather than
planning and forecasting values. The latter values usually are delivered for the full year all at
one time.

The Annualize function is different from the [Annual function](annual.htm "(Opens in a new tab or window)"). The Annual function returns the value of a specified metric
in the same table for a specified fiscal or calendar year, summing the values for the entire
year.

## Where to use

This function can be used in:

- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

`Annualize(metric)`

## Arguments

*metric*

A metric in the project. The function returns the projected total annual value of the metric for
the fiscal year based on the value of the metric up to the current period.

## Return type

Number

## Example

Assume your fiscal year runs from July to June. It is January, and you want to project costs
through the remainder of the fiscal year. Total costs to date are $2,400,000. You would enter the
following function:

`=Annualize(Cost)`

The function performs the following calculations:

$2,400,00/6 periods \* 12 periods= $48,000,000

$2,400,00/6 periods \* 13 periods= $52,000,000

See also:

- [Annual](annual.htm "(Opens in a new tab or window)")
- [PreviousMonth](previousmonth.htm "(Opens in a new tab or window)")
- [PreviousYear](previousyear.htm "(Opens in a new tab or window)")
- [TimePeriod](timeperiod.htm "(Opens in a new tab or window)")
- [YearToDate](yeartodate.htm "(Opens in a new tab or window)")
