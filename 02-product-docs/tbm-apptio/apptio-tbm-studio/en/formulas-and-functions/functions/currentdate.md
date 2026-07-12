---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "CurrentDate function"
breadcrumb: []
source_path: "formulas-and-functions/functions/currentdate.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# CurrentDate function

Applies to: TBM Studio 12.0 and later

Returns the starting date of the currently selected time period, if time is enabled. If not,
returns Eon 2000.

## Where to use

This function can be used in:

- Dynamic text
- Formula columns in report tables
- Calculated metrics and reports with metric columns
- Data sets

## Syntax

CurrentDate([format\_string])s

## Arguments

*format\_string*

> Specifies a date format for the return value. Same as format\_string in [DateFormat](dateformat.htm "(Opens in a new tab or window)").

## Return type

String

## Example

For the current date May 1, 2009, the following example returns 05/01/2009.

> `=CurrentDate("MM/dd/yyyy")`

See also:

- [Hours](hours.htm "(Opens in a new tab or window)")
- [Now](now.htm "(Opens in a new tab or window)")
- [Minutes](minutes.htm "(Opens in a new tab or window)")
- [Months](months.htm "(Opens in a new tab or window)")
