---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Annotated list of functions by type"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/annotated-list-of-functions-by-type.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Annotated list of functions by type

**Applies to**: TBM Studio 12.0 and later

The information below summarizes the functions and their syntax by type. The functions are listed
by the following types:

- Database
- Date and time
- Formatting
- Math
- String
- Table transformation

## Apptio project related Reports

## Database functions

| **Function** | **Description** |
| --- | --- |
| [CopyTable](functions/copytable.html "Applies to: TBM Studio v12.0+") | ``` CopyTable("Source Table","Destination Project","Destination Data Set","Time               Period to Copy To") ``` |
| [GetInfo](functions/getinfo.html "Applies to: TBM Studio 12.0 and later") | `GETINFO("attribute1",["DomainName:ProjectName"]` |
| [If](functions/if.html "Evaluates a filter expression and returns one value if true and another value if false. Supports both AND and OR operations in the condition.") | `If(filter_expression,true_expression,false_expression)` |
| [Key](functions/key-function.html "Applies to: TBM Studio 12.0 and later") | `Key(value1,value2,...)` |
| [PeriodsInHalf](functions/periodsinhalf.html "Applies to: TBM Studio and later") | `PeriodsInHalf(half)` |
| [PeriodsInQuarter](functions/periodsinquarter.html "Applies to: TBM Studio and later") | `PeriodsInQuarter(quarter)` |
| [PeriodsInYear](functions/periodsinyear.html "Applies to: TBM Studio and later") | `PeriodsInYear()` |
| [Replace](functions/replace.html "Replaces values in a table based on mappings from a separate lookup table. The function matches on key columns and assigns new values from specified columns in the replacement table. All values are treated as strings.") | `=Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)` |
| [Row](functions/row.html "Returns the index of the current row in the table, starting with zero for the first row.") | ``` Row(               ) ``` |
| [RowCount](functions/rowcount.html "Returns a count of the total number of rows in a specified table. If no table is specified, it returns the number of rows in the current table context.") | `RowCount(table)` |
| [TableMatch](functions/tablematch.html "Returns a value based on a rules table that functions like a set of IF statements. Each row in the rules table defines one rule. Conditions in the same row are combined with AND, and values within the same cell are treated as OR conditions.") | `TableMatch(Table,Column)` |
| [UniqueCount](functions/uniquecount.html "Applies to: TBM Studio 12.0 and later") | `UniqueCount(column)` |
| [UniqueValues](functions/uniquevalues.html) | `UniqueValues(column)` |

## Date and time functions

| Function | Syntax |
| --- | --- |
| [CurrentDate](functions/currentdate.html "Returns the starting date of the currently selected time period, if time is enabled. If not, returns Eon 2000.") | `CurrentDate([format_string])` |
| [Days](functions/days.html "Converts a specified date to a numeric value representing the number of days since January 1, 1970.") | `Days(date_expression)` |
| [DurationOfMonth](functions/durationofmonth.html) | `DurationOfMonth ("d/h/m/s/S", [month[, year]])` |
| [Elapsed](functions/elapsed.html "Calculates the elapsed time between two dates in seconds, optionally accounting for excluded periods and supporting formatted output.") | `Elapsed(startDate,endDate[,table[,startCol,endCol])` |
| [Hours](functions/hours.html "Converts a date value into the number of hours since January 1, 1970, as a numeric value.") | `Hours(date_expression)` |
| [Minutes](functions/minutes.html "Converts a date value into the number of minutes since January 1, 1970, as a numeric value.") | `Minutes(date_expression)` |
| [Months](functions/months.html "Converts a specified date to a decimal value representing the number of periods since January 1, 1970. Useful for time-based calculations such as determining durations or pro-rating costs.") | `Months(date_expression)` |
| [Now](functions/now.html) | `Now(metric)` |
| [Period](functions/period.html "Applies to: TBM Studio 12.0 and later") | `Period(["time_period"][n])` |

## Formatting functions

| Function | Syntax |
| --- | --- |
| [Currency](functions/currency.html "Formats numeric values as currency strings, adding the appropriate currency symbol based on the locale. By default, negative values are displayed in red.") | `Currency(column[,pattern[;negative_pattern]])` |
| [DateFormat](functions/dateformat.html "Converts a date expression to a specified date format.") | `DateFormat(date_expression,format_string)` |
| [NumberFormat](functions/numberformat.html "Formats a numeric value into a label (string) using custom patterns for positive and negative numbers, durations, or data size formatting. This function is designed for use in Label-type columns.") | `NumberFormat(column[,pattern[;negative_pattern]])` |
| [StatusIcon](functions/statusicon.html "Applies to: TBM Studio 12.0 and later") | `StatusIcon(green_expression,red_expression)` |

## Math functions

| Function | Syntax |
| --- | --- |
| [Abs](functions/abs-function.html "Returns the absolute value of a number or expression, removing any negative sign.") | `Abs(column)` |
| [Annual](functions/annual.html "Returns a value for the specified metric adjusted forward or backward by a number of years, based on the selected calendar type.") | `Annual(metric[,delta[,type]])` |
| [Annualize](functions/annualize.html "Applies to: TBM Studio 12.0 and later") | `Annualize(metric)` |
| [Average](functions/average.html "Returns the average value in a specified column or metric.") | `Average(rollup_operator column)` |
| [DateSum](functions/datesum.html "Sums the values in all columns whose names conform to recognized date formats, ignoring non-date columns.") | `DateSum()` |
| [Large](functions/large.html "Returns the largest value in a specified column.") | ``` Large               (rollup_operator column) ``` |
| [Max](functions/max.html "Compares two expressions and returns the greater value.") | `Max(numeric_expression,numeric_expression)` |
| [Min](functions/min.html "Compares two numeric expressions and returns the lesser value.") | `Min(numeric_expression,numeric_expression)` |
| [Mod](functions/mod.html "Divides one number by another and returns the remainder, preserving the sign of the dividend (first number).") | `Mod(number,divisor)` |
| [Percentile](functions/percentile.html "Returns the specified percentile value for a given numeric column. A percentile represents the value below which a given percentage of the data falls.") | `Percentile(rollup_operator column,percentage)` |
| [Power](functions/power.html "Raises a specified base number to the power of a specified exponent, performing exponential calculation.") | `Power(base,exponent)` |
| [PreviousMonth](functions/previousmonth.html "Returns the value of a specified metric from the previous month within the same table. Useful for comparing current values to the prior month.") | `PreviousMonth(metric)` |
| [PreviousYear](functions/previousyear.html "Returns the sum of a specified metric in the current table for the previous number of periods in a fiscal year. In a 12-period calendar, this would be 12 periods. In a 13-period calendar, this would be 13 periods.") | `PreviousYear(metric)` |
| [QuarterToDate](functions/quartertodate.html "Returns the cumulative value of a specified metric from the beginning of the current fiscal quarter up to and including the current period.") | `QuarterToDate(column)` |
| [Rand](functions/rand.html "Generates a random decimal number between 0.0 (inclusive) and 1.0 (exclusive).") | ``` Rand(               ) ``` |
| [Ratio](functions/ratio.html "Applies to: TBM Studio 12.0 and later") | `Ratio(column,~column)` |
| [Round](functions/round.html "Rounds a real number to a specified number of decimal places using the 'round-half-up' algorithm. This means that values ending in .5 are rounded away from zero.") | `Round(numeric_expression,digits)` |
| [SLN](functions/sln.html "Applies to: TBM Studio 12.0 and later") | `SLN(original,salvage,lifespan)` |
| [Small](functions/small.html "Returns the smallest value in a specified column.") | `Small(rollup_operator column)` |
| [Sum](functions/sum.html "Returns the total sum of the values in the specified numeric column.") | `Sum(column)` |
| [TimePeriod](functions/timeperiod.html "Returns the value of a specified metric at the beginning of a time period (e.g., month, quarter, year) that is a specified number of periods before or after the current period. The time unit is determined by the selected view or an explicit granularity suffix.") | `TimePeriod(metric,time)` |
| [Trunc](functions/trunc.html "Truncates a real number by removing its fractional part.") | `Trunc(value)` |
| [Untag](functions/untag.html "Applies to: TBM Studio 12.0 and later") | `Untag(value)` |
| [YearToDate](functions/yeartodate.html "Returns the cumulative value of a specified metric from the beginning of the current fiscal year up to and including the current period. This differs from the Annual function, which always returns the total for the entire year regardless of the current period.") | `YearToDate(column)` |

## String functions

| Function | Syntax |
| --- | --- |
| [CapFirstLetter](functions/capfirstletter.html "Capitalizes the first letter of each word in the string argument, and makes all other letters lowercase.") | `CapFirstLetter(string)` |
| [Eval](functions/eval.html "Applies to: TBM Studio 12.0 and later") | `Eval(string)` |
| [EvalWiki](functions/evalwiki.html "Applies to: TBM Studio 12.0 and later") | `EvalWiki(wikitext)` |
| [Find](functions/find.html "Returns the position of the first occurrence of a search string within another string, starting at an optional position. This function is case-sensitive.") | `Find(search_string,in_string,[starting_position])` |
| [IPLookup](functions/iplookup.html "Applies to: TBM Studio 12.0 and later") | ``` IPLookup(source_column,lookup_table,matching_column,replacement_column               ,default_value) ``` |
| [IsNumeric](functions/isnumeric.html "Evaluates an expression to determine if it is a valid number, returning 'true' or 'false' as a string.") | `IsNumeric("value") or ISNUMERIC({column name})` |
| [Left](functions/left.html "Returns a specified number of characters from a string (including white spaces), starting from the left.") | `Left(string[,count])` |
| [Len](functions/len.html "Returns the number of characters in a given string, including spaces.") | `Len(string_expression)` |
| [Lookup function](functions/lookup.html "Searches for a value in a lookup table based on a match between a column in the current table and a column in the lookup table, and returns the corresponding value from a replacement column.") | ``` Lookup(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) ``` |
| [Lookup\_Wild function](functions/lookup_wild.html "Searches for a value in a lookup table using pattern matching (regular expressions) in the matching column, and returns the corresponding value from a replacement column.") | ``` Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) ``` |
| [LookupEx](functions/lookupexandlookupex_wild.html "Performs a lookup across tables and returns all matching values, creating new rows for each match. This function enables a one-to-many relationship by joining every matching row from the lookup table into the transformed table.") | ``` LookupEx(source_column,lookup_table,matching_column,replacement_column               [,leave_original_value][,replace_nulls][,ignore_case]) ``` |
| [LookupFromPath](functions/lookupfrompath.html "Applies to: TBM Studio 12.0 and later") | `LookupFromPath("path",target_column,lookup_column,lookup_value_column)` |
| [LookupObjectTotalAllocated](functions/lookupobjecttotalallocated.html "Applies to: TBM Studio 12.0 and later") | `LookupObjectTotalAllocated(metric)` |
| [LookupObjectTotalValue](functions/lookupobjecttotalvalue.html "Applies to: TBM Studio 12.0 and later") | ``` LookupObjectTotalValue(object[,metric  [, driver]]) ``` |
| [LookupObjectUnitAllocated](functions/lookupobjectunitallocated.html "Applies to: TBM Studio 12.0 and later") | ``` LookupObjectUnitAllocated  (sourceObject,destObject,metric,  columnInLocalTable,columnInSourceObjectTable) ``` |
| [LookupObjectUnitValue](functions/lookupobjectunitvalue.html "Applies to: TBM Studio 12.0 and later") | ``` LookupObjectUnitValue  (object,metric,targetCol,lookupCol[,driver]) ``` |
| [LookUpMetric](functions/lookupmetric.html "Applies to: TBM Studio 12.0 and later") | `LookUpMetric(metric,column)` |
| [Lower](functions/lower.html "Converts the input string to all lowercase. characters") | `Lower(expression)` |
| [Mid](functions/mid.html "Returns a specified number of characters from a string, starting at a given position from the left.") | `Mid(string,start[,count])` |
| [Pluralize](functions/pluralize.html "Applies to: TBM Studio 12.0, 12.1") | `Pluralize(noun[,count])` |
| [Right](functions/right.html "Returns the specified number of characters from the end (right side) of a string, including white spaces.") | `Right(string[,count])` |
| [Search](functions/search.html) | `Search(search_string,in_string[,starting_position])` |
| [Split](functions/split.html "Applies to: TBM Studio 12.0 and later") | `Split(expression,n[,delimiters])` |
| [Substitute](functions/substitute.html) | `Substitute(target_string,search_string,replacement_string)` |
| [Trim](functions/trim.html "Removes leading and trailing spaces from a specified string. It does not remove spaces within a string.") | `Trim(expression)` |
| [Undrill](functions/undrill.html "Applies to: TBM Studio 12.0 and later") | `Undrill(metric)` |
| [Upper](functions/upper.html "Converts the input string to all uppercase characters.") | `Upper(expression)` |
| [Value](functions/value.html "Converts a numeric-looking string into a number using an optional formatting pattern. Useful for extracting numeric values from strings that include text or symbols.") | `Value(value[,pattern])` |

## Table transformation functions

| Function | Syntax |
| --- | --- |
| [Use\_Map\_Grid](functions/usemapgrid.html "Applies to: TBM Studio 12.0 and later") | `Use_Map_Grid(table:source_column[,notation])` |
| [Use\_Map\_Table](functions/usemaptable.html "Applies to: TBM Studio 12.0 and later") | ``` Deprecated.               Replaced by Use_Map_Grid. ``` |

## Apptio project related functions

| Function | Syntax |
| --- | --- |
| [DomainName](functions/domainname.html "Applies to: TBM Studio 12.0 and later") | ``` DomainName(               ) ``` |
| [ProjectExists](functions/project-exists-function.html "Applies to: TBM Studio 12.0 and later") | `ProjectExists(domain:project)` |
| [ProjectName](functions/projectname.html "Applies to: TBM Studio 12.0 and later") | ``` ProjectName               ( ) ``` |

## Reports functions

| Function | Syntax |
| --- | --- |
| [GetLastFilterColumn](functions/getlastfiltercolumn.html "Applies to: TBM Studio 12.0 and later") | `GetLastFilterColumn()` |
| [GetLastFilterValue](functions/getlastfiltervalue.html "Applies to: TBM Studio 12.0 and later") | `GetLastFilterValue(column)` |
| [GetReportName](functions/getreportname.html "Applies to: TBM Studio 12.0 and later") | `GetReportName()` |
| [GetReportPath](functions/getreportpath.html "Applies to: TBM Studio 12.0 and later") | `GetReportPath()` |
| [Icon](functions/icon.html "Applies to: TBM Studio 12.0 and later") | `Icon(["icon-type"], expression, expression+)` |
| [ObjectName](functions/objectname.html "Applies to: TBM Studio 12.0 and later") | `ObjectName()` |
| [Sparkline](functions/sparkline.html "Applies to: TBM Studio 12.0 and later") | `Sparkline(past,future,column)` |
