---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Annual function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/annual.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Annual function

Returns a value for the specified metric adjusted forward or backward by a number of
years, based on the selected calendar type.

## Syntax

`Annual(metric, delta, calendarType)`

## Parameters

*metric*: The name of the metric you want to adjust. Optional.

*delta*: Optional. The number of years to look forward (positive value) or backward
(negative value). If not specified, defaults to 0.

*calendarType*: Optional. The calendar system to use. Supported values are 'FY' for Fiscal
Year (default) and 'CY' for Calendar Year. If not specified, defaults to 'FY'.

## Behavior

- Requires a metric as input.
- Optionally adjusts the value based on the number of years specified by delta.
- Uses the specified calendar type to determine how years are calculated.
- If delta is not specified, it defaults to 0 (no adjustment).
- If calendarType is not specified, it defaults to 'FY' (Fiscal Year).

## Return type

Number

## Example

The following example returns the total Cost for the current year.

`=Annual(Cost)`

`=Annual(Budget,0,"CY`

`Annual(Budget)`: Returns the 'Budget' metric for the current fiscal year.

`Annual(Budget, -1)`: Returns the 'Budget' metric from one fiscal year ago.

`Annual(Budget, 1, "CY")`: Returns the 'Budget' metric for next calendar
year.

Note:

- The delta parameter must be a numeric value such as 0, 1, or -1.
- Use 'FY' (Fiscal Year) for 445 variant and 13-period fiscal calendars.
- Use 'CY' (Calendar Year) for standard Gregorian calendars.
