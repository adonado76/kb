---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Hours function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/hours.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Hours function

Converts a date value into the number of hours since January 1, 1970, as a numeric
value.

## Syntax

`Hours(date_expression, date_format)`

## Arguments

- *date\_expression*: The date to convert. Format must be a supported date format.
  Note: This parameter accepts an expression, meaning you can provide a literal value, a
  column reference, or the result of another function. Required.
- *date\_format*: The format of the date string. Required only if the date\_expression
  is not in a standard supported format. Optional

## Return type

Number

## Example

Assume you have the following table:

| Ticket Source | Date Submitted |
| --- | --- |
| Presales | 2/2/2010 17:38 |
| CS | 3/10/2010 9:41 |
| Products | 3/9/2010 13:14 |

You create a third column called Hours using the following
function:

`=Hours(Date Submitted)`

The result is the following
table:

| Ticket Source | Date Submitted | Hours |
| --- | --- | --- |
| Presales | 2/2/2010 17:38 | 351425.633 |
| CS | 3/10/2010 9:41 | 352281.683 |
| Products | 3/9/2010 13:14 | 352261.233 |

`Hours("2/2/2010 17:38")`

Returns the number of hours since January
1, 1970 for the given date and time.

Note: If the input date is in a non-standard
format, use the date\_format parameter to specify the correct format. See the DateFormat
function for formatting rules.

## Behavior

- Takes a date input and converts it to a numeric value representing hours since the epoch
  (January 1, 1970).
- If no date\_format is provided, the application assumes the input is in a supported
  standard format.
- The result is useful for performing arithmetic or comparisons with other time-based
  values.
