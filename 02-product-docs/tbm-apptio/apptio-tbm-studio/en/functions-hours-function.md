---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Hours function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Hours function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/hours.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Hours function

*Converts a date value into the number of hours since January 1, 1970, as a numeric value.*

## Syntax

Hours(date_expression, date_format)

## Arguments

- date_expression : The date to convert. Format must be a supported date format. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required.
- date_format : The format of the date string. Required only if the date_expression is not in a standard supported format. Optional

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

=Hours(Date Submitted)

The result is the following table:

| Ticket Source | Date Submitted | Hours |
| --- | --- | --- |
| Presales | 2/2/2010 17:38 | 351425.633 |
| CS | 3/10/2010 9:41 | 352281.683 |
| Products | 3/9/2010 13:14 | 352261.233 |

```
Hours("2/2/2010 17:38")
```

Returns the number of hours since January 1, 1970 for the given date and time.

## Behavior

- Takes a date input and converts it to a numeric value representing hours since the epoch (January 1, 1970).
- If no date_format is provided, the application assumes the input is in a supported standard format.
- The result is useful for performing arithmetic or comparisons with other time-based values.
