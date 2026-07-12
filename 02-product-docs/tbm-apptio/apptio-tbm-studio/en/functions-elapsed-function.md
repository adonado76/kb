---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Elapsed function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Elapsed function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/elapsed.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Elapsed function

*Calculates the elapsed time between two dates in seconds, optionally accounting for excluded periods and supporting formatted output.*

## Syntax

Elapsed(startDate, endDate [, "format" [, exclusionTable [, startCol, endCol]]])

## Parameters

- startDate : An expression that evaluates to the start date and time. Must be in a recognized date-time format (e.g., 'MM/DD/YYYY HH:MM'). Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required
- endDate : An expression that evaluates to the end date and time. Must be in a recognized date-time format. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required
- format : Optional. If the string "format" is provided, the function returns the elapsed time split into Years, Days, Hours, Minutes, and Seconds instead of total seconds. Must be exactly "format" (case-sensitive). Optional (default: Returns total elapsed seconds)
- exclusionTable : Optional. A table reference that lists time periods to exclude from the elapsed time calculation. Optional (default: No exclusions applied)
- startCol : Optional. The column name in the exclusion table representing the start of the excluded period. Defaults to 'From'. Optional (default: "From" column)
- endCol : Optional. The column name in the exclusion table representing the end of the excluded period. Defaults to 'To'. Optional (default: "To" column)

## Behaviour

- Calculates the difference between startDate and endDate in seconds.
- If 'format' is provided as a string literal, returns output split into Years, Days, Hours, Minutes, and Seconds.
- Supports exclusion of time periods using an exclusion table and specified columns.
- If no startCol and endCol are provided, defaults to 'From' and 'To' columns in the exclusion table.

## Return Type

Number

## Exclusions table

To calculate spans of time that exclude non-working hours, holidays, etc., the function relies on an exclusions table defined as a data set in your Apptio project. A sample exclusions table is shown below. The Description column is ignored by the function.

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

- Elapsed("04/23/2010 08:00", "04/23/2010 10:00") Returns the number of seconds between 8:00 AM and 10:00 AM on April 23, 2010.
- Elapsed(DateSubmitted, DateFirstResponse) Calculates the elapsed time between the submission date and the first response date.
- Elapsed("04/23/2010 18:00", "04/26/2010 11:00", Exclusions, From, To) Calculates the elapsed time excluding periods defined in the 'Exclusions' table.
- Elapsed("04/23/2010 18:00", "04/26/2010 11:00", "format") Returns the formatted elapsed time as Years, Days, Hours, Minutes, and Seconds.
- Elapsed("04/23/2010 18:00", "04/26/2010 11:00", "format", Exclusions, From, To) Returns the formatted elapsed time, excluding periods defined in the 'Exclusions' table.

- All date and time values must be provided in recognized formats.
- The 'format' argument must be entered exactly as the string "format".
- When specifying an exclusion table, both start and end columns can optionally be customized.
- If the exclusion table is used but no startCol and endCol are specified, 'From' and 'To' are assumed.
