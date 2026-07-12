---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "DateFormat function"
breadcrumb: []
source_path: "formulas-and-functions/functions/dateformat.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# DateFormat function

Applies to: TBM Studio 12.0 and later.

The `DateFormat` function allows the user to change the format of a date.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text

## Syntax

```
DateFormat(date_expression,"format_string",["time_zone"], ["from_format"])
```

## Arguments

date\_expression
:   This argument can take a column of the Date or Label type. It can also take the result of a
    nested formula or a String constant.

    A date value in UNIX Time Stamp (epoch time) format (this
    can be generated using the Now( ) function), or any of the supported Apptiodate formats. Unix Epoch
    time is the number of seconds that have elapsed since January 1, 1970.

    NOTICE

    Elements
    of date values can be separated by a dash ( - ) or a slash ( / ). Therefore, M-d-yy is the
    same as M/d/yy.

    "ffff" is a fiscal year definition and "yyyy" is a calendar year
    definition. If your fiscal year starts in a month other than January, these may not give the same
    value.

    ‘p’ and ‘M’ are different in that ‘M’ is the name of the calendar month for the
    period. Apptio supports 13-period calendars, where the time periods may not align to calendar
    months. In a 13-period calendar, ‘P’ will return the period number (1 for the 1st period of the
    fiscal year) since month names cannot uniquely identify every period.

    Table 1.

    | Format | Example output |
    | --- | --- |
    | ppp | Jan |
    | pppp | January |
    | ffff | FY2012 |
    | yy | 09 |
    | yyyy | 2009 |
    | MMM | Jan |
    | MMM-yy | Jan-09 |
    | M-d-yy | 1-20-09 |
    | M-d-yy HH:mm | 1-20-09 14:00 |
    | M-d-yy hh:mm a | 1-20-09 2:00 PM |
    | M-d-yy HH:mm:ss | 1-20-09 14:00:30 |
    | M-d-yy hh:mm:ss a | 1-20-09 2:00:30 PM |
    | M-d-yy HH:mm:ss.S | 1-20-09 14:00:30.007 |
    | M-d-yy hh:mm:ss.S a | 1-20-09 2:00:30.007 PM |
    | yyyy-M-d | 2009-1-20 |
    | yyyy-M-d HH:mm | 2009-1-20 14:00 |
    | yyyy-M-d hh:mm a | 2009-1-20 2:00 PM |
    | yyyy-M-d HH:mm:ss | 2009-1-20 14:00:30 |
    | yyyy-M-d hh:mm:ss a | 2009-1-20 2:00:30 PM |
    | yyyy-M-d HH:mm:ss.S | 2009-1-20 14:00:30.007 |
    | yyyy-M-d hh:mm:ss.S a | 2009-1-20 2:00:30.007 PM |
    | MMM d, yyyy | Jan 20, 2009 |
    | dd-MMM | 20-Jan |
    | dd-MMM-yyyy | 20-Jan-2009 |
    | dd-MMM-yyyy HH:mm | 20-Jan-2009 14:00 |
    | dd-MMM-yyyy hh:mm a | 20-Jan-2009 2:00 PM |
    | dd-MMM-yyyy HH:mm:ss | 20-Jan-2009 14:00:30 |
    | dd-MMM-yyyy hh:mm:ss a | 20-Jan-2009 2:00:30 PM |
    | dd-MMM-yyyy HH:mm:ss.S | 20-Jan-2009 14:00:30.007 |
    | dd-MMM-yyyy hh:mm:ss.S a | 20-Jan-2009 2:00:30.007 PM |
    | dd-MM-yyyy | 20-01-2009 |
    | dd-MM-yyyy HH:mm | 20-01-2009 14:00 |
    | dd-MM-yyyy hh:mm a | 20-01-2009 2:00 PM |
    | dd-MM-yyyy HH:mm:ss | 20-01-2009 14:00:30 |
    | dd-MM-yyyy h:mm:ss a | 20-01-2009 2:00:30 PM |
    | dd-MM-yyyy HH:mm:ss.S | 20-01-2009 14:00:30.007 |
    | dd-MM-yyyy hh:mm:ss.S a | 20-01-2009 2:00:30.007 PM |
    | Eon yy | Eon 09 |

format\_string
:   Specifies the format for the string returned by the function. This argument can take a column of
    type Label. It can also take the result of a nested formula that returns a label, or a String
    constant.

    Table 2.

    | Format Element | Format | Description | Example |
    | --- | --- | --- | --- |
    | M | M  MM  MMM  MMMMM | Month | M: 6  MM: 06  MMM: Jun  MMMM: June |
    | D | D  DD  DDD | Day in the year. The number of Ds determines the number of digits displayed | D: 7 (January 7th)  DD: 07 (January 7th)  DDD: 007 (January 7th) |
    | d | d  dd | Day in month (1 through 31) | d: 2  dd: 02 |
    | w | w  ww | The week of the year (1 through 52) | w: 9  ww: 09 |
    | W | W | Week of the month in which the date occurs (1 through 5) | 1 |
    | E | E | Day in the week | Mon |
    | E | EEEE | Day in the week (long) | Monday |
    | F | F | Day of week in the month (the number of times the weekday has occurred during the month) | 2 |
    | y | y  yy | Year | y: 14  yyyy: 2014 |
    | H | H  HH | Hour in military time (0-23) | H: 4, 14  HH: 04, 14 |
    | h | h  hh | Hour in am/pm (1-12) | h: 2  hh: 02 |
    | m | m  mm | Minute (0-59) | m: 3, 30  mm: 03, 30 |
    | s | s  ss | Second in minute (0-59) | s: 3, 30  ss: 03, 30 |
    | S | S  SS  SSS | Millisecond | S: 7  SS: 07  SSS: 007 |
    | a |  | Display AM or PM as appropriate | AM |
    | z | z | General time zone (short format) | GMT |
    | z | zzzz | General time zone (long format) | Greenwich Mean Time |
    | Z | Z | RFC822 time zone (offset from GMT) | 8 (for Pacific time) |
    | p | ppp | Short period description | Period calendar types: P1  Gregorian calendar type: Mar |
    | p | pppp | Long period description | Period calendar types: Period 1  Gregorian calendar type: March |
    | f | ffff | Period fiscal year | FY2014 |

## Special characters and escaping

The following special characters can be used in a quoted date string:

- Period (`.`)
- Forward Slash (`/`)
- Hyphen (`-`)

To add additional text to the date format-string, enclose the text in single quotes. For example,
for the date and time value Jan. 12, 2015 12:15 am:

```
MMM dd, yyyy 'at' hh:mm a
```

time\_zone
:   Indicates the time zone used to display the time. For a time zone to be displayed in a date, use
    a format string that includes a "z" argument at the end. If this argument is not included, the time
    will be displayed in GMT format. All time zones included in the Java TimeZone class can be used in
    this argument. To see a complete list of time zones, search the web for "Java TimeZone class." If
    you want to specify arguments after this, but not specify a time zone, you can specify
    `""` for this argument as follows:

    ```
    =Dateformat(Column1,"MM/dd/yy","",MMM dd,yyyy")
    ```

from\_format
:   [Supported on 12.4.1+]

    Indicates the current format of the date\_expression. This format is used to parse the date. If
    unspecified, the system will try to parse the date with the default dates for the current locale. If
    the user wants to specify a from\_format, but with the time zone used to display the time. For a time
    zone to be displayed in a date, use a format string that includes a "z" argument at the end. If this
    argument is not included, the time will be displayed in GMT format. All time zones included in the
    Java TimeZone class can be used in this argument. To see a complete list of time zones, search the
    web for "Java TimeZone class."

    The syntax for this argument is the same as that of the date\_format argument.

## Examples

The following examples assume a date of Oct. 12, 2014 10:24:52 AM.

- The following example returns 10/12/15 10:24:52
  AM:

  ```
  =DateFormat(Column1,"MM/dd/yy hh:mm:ss a")
  ```
- The following example in UNIX timestamp (Epoch time) format returns 01/24/2015:

  ```
  =DateFormat(1295908500,"MM/dd/yyyy")
  ```
- The following example in UNIX timestamp (Epoch time) format returns FY2015:

  ```
  =DateFormat(1295908500,"ffff")
  ```
- The following example in UNIX timestamp (epoch time) format returns P1:FY2015.

  ```
  =DateFormat(1295908500,"ppp:ffff")
  ```
- The following formula will convert a date from a date format that means different things in the
  United States and the United Kingdom, into a format that has the same meaning in both countries. It
  also parses the date in terms of calendar year, but displays a value in terms of fiscal year:
  - Convert the UK date of 5/6/2017 to June 5th,
    2017:

    ```
    =DateFormat(column,"MMM ddth, ffff","","dd/MM/yyyy")
    ```
  - Convert the US date of 5/6/2017 to May 6th,
    2017:

    ```
    =DateFormat(column,"MMM ddth, ffff","","MM/dd/yyyy")
    ```

## Formats

The following international formats are supported. If you need to use an unsupported date format,
convert your date to a supported date format in a table transform. Specify the appropriate date
format in the ‘Date Format’ property on a column of type ‘date’ in a table transform. Then point the
DateFormat function at that column to convert to a supported format.

United States
:   - MMM d, yyyy
    - M/d/yy
    - MMMM d, yyyy
    - MMM d, yyyy h:mm:ss a
    - MMM d, yyyy h:mm a
    - MMM d, yyyy h:mm:ss a z
    - M/d/yy h:mm:ss a
    - M/d/yy h:mm a
    - M/d/yy h:mm:ss a z
    - MMMM d, yyyy h:mm:ss a
    - MMMM d, yyyy h:mm a
    - MMMM d, yyyy h:mm:ss a z
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - yyyy-M-d hh:mm a
    - yyyy-M-d HH:mm a
    - yyyy-M-d hh:mm:ss a
    - yyyy-M-d hh:mm:ss.S a
    - yyyy/M/d hh:mm a
    - yyyy/M/d HH:mm a
    - yyyy/M/d hh:mm:ss a
    - yyyy/M/d hh:mm:ss.S a
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S.

Argentina
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S.

Austria
:   - dd.MM.yyyy
    - dd.MM.yy
    - dd. MMMM yyyy
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss z
    - dd.MM.yy HH:mm:ss
    - dd.MM.yy HH:mm
    - dd.MM.yy HH:mm:ss z
    - dd. MMMM yyyy HH:mm:ss
    - dd. MMMM yyyy HH:mm
    - dd. MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S.

Belgium (Dutch)
:   - d-MMM-yyyy
    - d/MM/yy
    - d MMMM yyyy
    - d-MMM-yyyy H:mm:ss
    - d-MMM-yyyy H:mm
    - d-MMM-yyyy H:mm:ss z
    - d/MM/yy H:mm:ss
    - d/MM/yy H:mm
    - d/MM/yy H:mm:ss z
    - d MMMM yyyy H:mm:ss
    - d MMMM yyyy H:mm
    - d MMMM yyyy H:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy H:mm
    - dd-MMM-yyyy H:mm:ss
    - dd-MMM-yyyy H:mm:ss z
    - dd.MM.yyyy H:mm:ss
    - dd.MM.yyyy H:mm
    - dd.MM.yyyy H:mm:ss z
    - d/M/yy H:mm:ss
    - d/M/yy H:mm
    - d/M/yy H:mm:ss z
    - d-M-yy H:mm:ss
    - d-M-yy H:mm
    - d-M-yy H:mm:ss z.

Belgium (French)
:   - dd-MMM-yyyy
    - d/MM/yy
    - d MMMM yyyy
    - dd-MMM-yyyy H:mm:ss
    - dd-MMM-yyyy H:mm
    - dd-MMM-yyyy H:mm:ss z d/MM/yy H:mm:ss
    - d/MM/yy H:mm
    - d/MM/yy H:mm:ss z
    - d MMMM yyyy H:mm:ss
    - d MMMM yyyy H:mm
    - d MMMM yyyy H:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyy.M.d
    - yyy.M.d HH:mm
    - yyy.M.d HH:mm:ss
    - yyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S.

Botswana
:   - yyyy-M-d
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyy/M/d
    - yyy/M/d HH:mm:ss
    - yyy/M/d HH:mm:ss.S
    - yyy.M.d
    - yyy.M.d HH:mm:ss
    - yyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Brazil
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Columbia
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Ecuador
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

El Salvador
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Ethiopia
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

France
:   - d MMM yyyy
    - dd/MM/yy
    - d MMMM yyyy
    - d MMM yyyy HH:mm:ss
    - d MMM yyyy HH:mm
    - d MMM yyyy HH:mm:ss z
    - dd/MM/yy HH:mm:ss
    - dd/MM/yy HH:mm
    - dd/MM/yy HH:mm:ss z
    - d MMMM yyyy HH:mm:ss
    - d MMMM yyyy HH:mm
    - d MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Germany
:   - dd.MM.yyyy
    - dd.MM.yy
    - d. MMMM yyyy
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss z
    - dd.MM.yy HH:mm:ss
    - dd.MM.yy HH:mm
    - dd.MM.yy HH:mm:ss z
    - d. MMMM yyyy HH:mm:ss
    - d. MMMM yyyy HH:mm
    - d. MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Ghana
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Honduras
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Ireland (English)
:   - dd-MMM-yyyy
    - dd/MM/yy
    - dd MMMM yyyy
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss z
    - dd/MM/yy HH:mm:ss
    - dd/MM/yy HH:mm
    - dd/MM/yy HH:mm:ss z
    - dd MMMM yyyy HH:mm:ss
    - dd MMMM yyyy HH:mm
    - dd MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Ireland (Irish)
:   - d MMM yyyy
    - dd/MM/yyyy
    - d MMMM yyyy
    - d MMM yyyy HH:mm:ss
    - d MMM yyyy HH:mm
    - d MMM yyyy HH:mm:ss z
    - dd/MM/yyyy HH:mm:ss
    - dd/MM/yyyy HH:mm
    - dd/MM/yyyy HH:mm:ss z
    - d MMMM yyyy HH:mm:ss
    - d MMMM yyyy HH:mm
    - d MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Italy
:   - d-MMM-yyyy
    - dd/MM/yy
    - d MMMM yyyy
    - d-MMM-yyyy H.mm.ss
    - d-MMM-yyyy H.mm
    - d-MMM-yyyy H.mm.ss z
    - dd/MM/yy H.mm.ss
    - dd/MM/yy H.mm
    - dd/MM/yy H.mm.ss z
    - d MMMM yyyy H.mm.ss
    - d MMMM yyyy H.mm
    - d MMMM yyyy H.mm.ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Kenya
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Lesotho
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Luxembourg (French)
:   - d MMM yyyy
    - dd/MM/yy
    - d MMMM yyyy
    - d MMM yyyy HH:mm:ss
    - d MMM yyyy HH:mm
    - d MMM yyyy HH:mm:ss z
    - dd/MM/yy HH:mm:ss
    - dd/MM/yy HH:mm
    - dd/MM/yy HH:mm:ss z
    - d MMMM yyyy HH:mm:ss
    - d MMMM yyyy HH:mm
    - d MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Luxembourg (German)
:   - dd.MM.yyyy
    - dd.MM.yy
    - d. MMMM yyyy
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss z
    - dd.MM.yy HH:mm:ss
    - dd.MM.yy HH:mm
    - dd.MM.yy HH:mm:ss z
    - d. MMMM yyyy HH:mm:ss
    - d. MMMM yyyy HH:mm
    - d. MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Malawi
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Mauritius
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Mexico
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Mozambique
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Netherland
:   - d-MMM-yyyy
    - d-M-yy d MMMM yyyy
    - d-MMM-yyyy H:mm:ss
    - d-MMM-yyyy H:mm
    - d-MMM-yyyy H:mm:ss z
    - d-M-yy H:mm:ss
    - d-M-yy H:mm
    - d-M-yy H:mm:ss z
    - d MMMM yyyy H:mm:ss
    - d MMMM yyyy H:mm
    - d MMMM yyyy H:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Nigeria
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Panama
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Portugal
:   - d/MMM/yyyy
    - dd-MM-yyyy
    - d' de 'MMMM' de 'yyyy
    - d/MMM/yyyy H:mm:ss
    - d/MMM/yyyy H:mm
    - d/MMM/yyyy H:mm:ss z
    - dd-MM-yyyy H:mm:ss
    - dd-MM-yyyy H:mm
    - dd-MM-yyyy H:mm:ss z
    - d' de MMMM de 'yyyy H:mm:ss
    - d' de MMMM de 'yyyy H:mm
    - d' de MMMM de 'yyyy H:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

South Africa
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Spain (Catalan)
:   - dd/MM/yyyy
    - dd/MM/yy
    - d' / MMMM / 'yyyy
    - dd/MM/yyyy HH:mm:ss
    - dd/MM/yyyy HH:mm
    - dd/MM/yyyy HH:mm:ss z
    - dd/MM/yy HH:mm:ss
    - dd/MM/yy HH:mm
    - dd/MM/yy HH:mm:ss z
    - d' / MMMM / 'yyyy HH:mm:ss
    - d' / MMMM / 'yyyy HH:mm
    - d' / MMMM / 'yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Spain (Spanish)
:   - dd-MMM-yyyy
    - d/MM/yy
    - d' de MMMM de 'yyyy
    - dd-MMM-yyyy H:mm:ss
    - dd-MMM-yyyy H:mm
    - dd-MMM-yyyy H:mm:ss z
    - d/MM/yy H:mm:ss
    - d/MM/yy H:mm
    - d/MM/yy H:mm:ss z
    - d' de MMMM de 'yyyy H:mm:ss
    - d' de MMMM de 'yyyy H:mm
    - d' de MMMM de 'yyyy H:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Swaziland
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Switzerland (French)
:   - d MMM yyyy
    - dd.MM.yy
    - d. MMMM yyyy
    - d MMM yyyy HH:mm:ss
    - d MMM yyyy HH:mm
    - d MMM yyyy HH:mm:ss z
    - dd.MM.yy HH:mm:ss
    - dd.MM.yy HH:mm
    - dd.MM.yy HH:mm:ss z
    - d. MMMM yyyy HH:mm:ss
    - d. MMMM yyyy HH:mm
    - d. MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Switzerland (German)
:   - dd.MM.yyyy
    - dd.MM.yy
    - d. MMMM yyyy
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss z
    - dd.MM.yy HH:mm:ss
    - dd.MM.yy HH:mm
    - dd.MM.yy HH:mm:ss z
    - d. MMMM yyyy HH:mm:ss
    - d. MMMM yyyy HH:mm
    - d. MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Switzerland (Italian)
:   - d-MMM-yyyy
    - dd.MM.yy
    - d. MMMM yyyy
    - d-MMM-yyyy HH:mm:ss
    - d-MMM-yyyy HH:mm
    - d-MMM-yyyy HH:mm:ss z
    - dd.MM.yy HH:mm:ss
    - dd.MM.yy HH:mm
    - dd.MM.yy HH:mm:ss z
    - d. MMMM yyyy HH:mm:ss
    - d. MMMM yyyy HH:mm
    - d. MMMM yyyy HH:mm:ss z
    - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

Tanzania
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

Uganda
:   - yyyy-M-d
    - yyyy-M-d HH:mm
    - yyyy-M-d HH:mm:ss
    - yyyy-M-d HH:mm:ss.S
    - yyyy/M/d
    - yyyy/M/d HH:mm
    - yyyy/M/d HH:mm:ss
    - yyyy/M/d HH:mm:ss.S
    - yyyy.M.d
    - yyyy.M.d HH:mm
    - yyyy.M.d HH:mm:ss
    - yyyy.M.d HH:mm:ss.S
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - M/d/yy
    - M/d/yy HH:mm
    - M/d/yy HH:mm:ss
    - M/d/yy HH:mm:ss.S
    - M-d-yy
    - M-d-yy HH:mm
    - M-d-yy HH:mm:ss
    - M-d-yy HH:mm:ss.S

United Kingdom
:   - dd-MMM-yyyy
    - dd/MM/yy
    - dd MMMM yyyy
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss z
    - dd/MM/yy HH:mm:ss
    - dd/MM/yy HH:mm
    - dd/MM/yy HH:mm:ss z
    - dd MMMM yyyy HH:mm:ss
    - dd MMMM yyyy HH:mm
    - dd MMMM yyyy HH:mm:ss z
    - MMM d, yy
    - dd-MMM
    - dd-MMM-yyyy
    - dd-MMM-yyyy HH:mm
    - dd-MMM-yyyy HH:mm:ss
    - dd-MMM-yyyy HH:mm:ss.S
    - dd-MMM-yy
    - dd-MMM-yy HH:mm
    - dd-MMM-yy HH:mm:ss
    - dd-MMM-yy HH:mm:ss.S
    - dd.MM.yyyy
    - dd.MM.yyyy HH:mm
    - dd.MM.yyyy HH:mm:ss
    - dd.MM.yyyy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d/M/yy
    - d/M/yy HH:mm
    - d/M/yy HH:mm:ss
    - d/M/yy HH:mm:ss.S
    - d-M-yy
    - d-M-yy HH:mm
    - d-M-yy HH:mm:ss
    - d-M-yy HH:mm:ss.S

## Examples

The following examples assume a date of Oct. 12, 2014 10:24:52 AM.

- The following example returns 10/12/15 10:24:52 AM.

  ```
  =DateFormat(Column1,"MM/dd/yy hh:mm:ss
                a")
  ```
- The following example in UNIX timestamp (epoch time) format returns 01/24/2015.

  ```
  =DateFormat(1295908500,"MM/dd/yyyy")
  ```
- The following example in UNIX timestamp (epoch time) format returns FY2015.

  ```
  =DateFormat(1295908500,"ffff")
  ```
- The following example in UNIX timestamp (epoch time) format returns P1:FY2015.

  ```
  =DateFormat(1295908500,"ppp:ffff")
  ```
