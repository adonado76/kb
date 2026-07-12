---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "DateFormat function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "DateFormat function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/dateformat.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# DateFormat function

*Converts a date expression to a specified date format.*

## Syntax

```
DateFormat(date_expression, format_string [, time_zone [, from_format]])
```

## Parameters

- date_expression : The date value to be formatted. Can be a Date or a String. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required
- format_string : Specifies the desired format of the output string. Uses standard date formatting patterns (e.g., 'yyyy-MM-dd'). See the Pattern Reference section below for a complete list of available pattern letters. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required
- time_zone : Specifies the time zone for displaying the date and time. To include the time zone in the output, the format_string must include a 'z'. Optional (default: GMT)
- from_format : Specifies the current format of the date_expression if it is a String. Used to correctly parse the date before formatting. Uses the same pattern letters as format_string - see the Pattern Reference section below. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Optional (default: Locale-dependent default parsing)

## Examples

The following examples assume a date of Oct. 12, 2014 10:24:52 AM.

- Formats the current date as 'year-month-day'. DateFormat(CurrentDate(), "yyyy-MM-dd")
- Parses the input ISO timestamp, shifts to Pacific Time, and formats as 'Apr 29, 2025'. DateFormat("2025-04-29T08:00:00", "MMM dd, yyyy", "PST", "yyyy-MM-dd'T'HH:mm:ss")

## Date and Time Pattern Reference

Date and time formats are defined using pattern strings. In these strings, unquoted letters from 'A'–'Z' and 'a'–'z' serve as pattern symbols that represent parts of the date or time. To include literal text, you can use single quotes ('); two consecutive single quotes ('') represent a literal single quote. Any other characters are treated as literal—they are either inserted into the formatted output or matched exactly when parsing. The following table shows the pattern letters that can be used in format_string and from_format:

| Format Element | Format | Description | Example |
| --- | --- | --- | --- |
| M | MMMMMMMMMMM | Month | M: 6MM: 06MMM: JunMMMMM: June |
| D | DDDDDD | Day in the year. The number of Ds determines the number of digits displayed | D: 7 (January 7th)DD: 07 (January 7th)DDD: 007 (January 7th) |
| d | ddd | Day in month (1 through 31) | d: 2dd: 02 |
| w | www | The week of the year (1 through 52) | w: 9ww: 09 |
| W | W | Week of the month in which the date occurs (1 through 5) | 1 |
| E | E | Day in the week | Mon |
| E | EEEE | Day in the week (long) | Monday |
| F | F | Day of week in the month (the number of times the weekday has occurred during the month) | 2 |
| y | yyyyyy | Year | yy: 14yyyy: 2014 |
| H | HHH | Hour in military time (0-23) | H: 4, 14HH: 04, 14 |
| h | hhh | Hour in am/pm (1-12) | h: 2hh: 02 |
| m | mmm | Minute (0-59) | m: 3, 30mm: 03, 30 |
| s | sss | Second in minute (0-59) | s: 3, 30ss: 03, 30 |
| S | SSSSSS | Millisecond | S: 7SS: 07SSS: 007 |
| a |  | Display AM or PM as appropriate | AM |
| z | z | General time zone (short format) | GMT |
| z | zzzz | General time zone (long format) | Greenwich Mean Time |
| Z | Z | RFC822 time zone (offset from GMT) | 8 (for Pacific time) |
| p | ppp | Short period description | Period calendar types: P1Gregorian calendar type: Mar |
| p | pppp | Long period description | Period calendar types: Period 1Gregorian calendar type: March |
| f | ffff | Period fiscal year | FY2014 |

## Return Type

String
