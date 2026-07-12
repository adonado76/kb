---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Quarter function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Quarter function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/quarter.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Quarter function

Returns the total value of a specified metric in the same table for a specified quarter, summing the values for the entire quarter. If no quarter is specified, the function is evaluated for the current quarter. This function returns the total for the entire quarter regardless of what month in which it is viewed.

## Syntax

Quarter(metric[,delta[,type]])

## Parameters

- metric : A metric in the same table. The function returns the sum of this metric for the entire quarter.
- delta : The number of quarters to shift relative to the current quarter. Use negative numbers to look back (e.g., -2 for two quarters ago). Defaults to 0 (current quarter). Optional (default: 0)
- type : Specifies whether the quarter is based on fiscal ( FY ) or calendar ( CY ) year. Defaults to FY . Must be provided as a string literal. Optional (default: "FY")

## Behavior

- Calculates the total value of the specified metric for the full quarter.
- Supports both fiscal and calendar quarter types, depending on dataset configuration.
- Defaults to the current fiscal quarter if no delta or type is provided.
- Always returns the full-quarter value regardless of the month from which the function is evaluated.

## Return type

Number

## Example

The following example returns the total {cost} for the current fiscal quarter:

=Quarter(Cost)

The following example returns the total {cost} for the next fiscal quarter:

=Quarter(Cost,1)

Returns the total {Cost} from two calendar quarters ago.

Quarter(Cost, -2, "CY")
