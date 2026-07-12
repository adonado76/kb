---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Annotated list of functions by type"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Annotated list of functions by type"
source_path: "SSWRJM/studio/formulas-and-functions/annotated-list-of-functions-by-type.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Annotated list of functions by type

*Applies to : TBM Studio 12.0 and later*

- Database
- Date and time
- Formatting
- Math
- String
- Table transformation

## Apptio project related Reports

## Database functions

| Function | Description |
| --- | --- |
| CopyTable | CopyTable("Source Table","Destination Project","Destination Data Set","Time Period to Copy To") |
| GetInfo | GETINFO("attribute1",["DomainName:ProjectName"] |
| If | If(filter_expression,true_expression,false_expression) |
| Key | Key(value1,value2,...) |
| PeriodsInHalf | PeriodsInHalf(half) |
| PeriodsInQuarter | PeriodsInQuarter(quarter) |
| PeriodsInYear | PeriodsInYear() |
| Replace | =Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column) |
| Row | Row( ) |
| RowCount | RowCount(table) |
| TableMatch | TableMatch(Table,Column) |
| UniqueCount | UniqueCount(column) |
| UniqueValues | UniqueValues(column) |

## Date and time functions

| Function | Syntax |
| --- | --- |
| CurrentDate | CurrentDate([format_string]) |
| Days | Days(date_expression) |
| DurationOfMonth | DurationOfMonth ("d/h/m/s/S", [month[, year]]) |
| Elapsed | Elapsed(startDate,endDate[,table[,startCol,endCol]) |
| Hours | Hours(date_expression) |
| Minutes | Minutes(date_expression) |
| Months | Months(date_expression) |
| Now | Now(metric) |
| Period | Period(["time_period"][n]) |

## Formatting functions

| Function | Syntax |
| --- | --- |
| Currency | Currency(column[,pattern[;negative_pattern]]) |
| DateFormat | DateFormat(date_expression,format_string) |
| NumberFormat | NumberFormat(column[,pattern[;negative_pattern]]) |
| StatusIcon | StatusIcon(green_expression,red_expression) |

## Math functions

| Function | Syntax |
| --- | --- |
| Abs | Abs(column) |
| Annual | Annual(metric[,delta[,type]]) |
| Annualize | Annualize(metric) |
| Average | Average(rollup_operator column) |
| DateSum | DateSum() |
| Large | Large (rollup_operator column) |
| Max | Max(numeric_expression,numeric_expression) |
| Min | Min(numeric_expression,numeric_expression) |
| Mod | Mod(number,divisor) |
| Percentile | Percentile(rollup_operator column,percentage) |
| Power | Power(base,exponent) |
| PreviousMonth | PreviousMonth(metric) |
| PreviousYear | PreviousYear(metric) |
| QuarterToDate | QuarterToDate(column) |
| Rand | Rand( ) |
| Ratio | Ratio(column,~column) |
| Round | Round(numeric_expression,digits) |
| SLN | SLN(original,salvage,lifespan) |
| Small | Small(rollup_operator column) |
| Sum | Sum(column) |
| TimePeriod | TimePeriod(metric,time) |
| Trunc | Trunc(value) |
| Untag | Untag(value) |
| YearToDate | YearToDate(column) |

## String functions

| Function | Syntax |
| --- | --- |
| CapFirstLetter | CapFirstLetter(string) |
| Eval | Eval(string) |
| EvalWiki | EvalWiki(wikitext) |
| Find | Find(search_string,in_string,[starting_position]) |
| IPLookup | IPLookup(source_column,lookup_table,matching_column,replacement_column ,default_value) |
| IsNumeric | IsNumeric("value") or ISNUMERIC({column name}) |
| Left | Left(string[,count]) |
| Len | Len(string_expression) |
| Lookup function | Lookup(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) |
| Lookup_Wild function | Lookup_Wild(source_column, lookup_table, matching_column, replacement_column, leave_original_value, replace_nulls, ignore_case, default_value) |
| LookupEx | LookupEx(source_column,lookup_table,matching_column,replacement_column [,leave_original_value][,replace_nulls][,ignore_case]) |
| LookupFromPath | LookupFromPath("path",target_column,lookup_column,lookup_value_column) |
| LookupObjectTotalAllocated | LookupObjectTotalAllocated(metric) |
| LookupObjectTotalValue | LookupObjectTotalValue(object[,metric [, driver]]) |
| LookupObjectUnitAllocated | LookupObjectUnitAllocated (sourceObject,destObject,metric, columnInLocalTable,columnInSourceObjectTable) |
| LookupObjectUnitValue | LookupObjectUnitValue (object,metric,targetCol,lookupCol[,driver]) |
| LookUpMetric | LookUpMetric(metric,column) |
| Lower | Lower(expression) |
| Mid | Mid(string,start[,count]) |
| Pluralize | Pluralize(noun[,count]) |
| Right | Right(string[,count]) |
| Search | Search(search_string,in_string[,starting_position]) |
| Split | Split(expression,n[,delimiters]) |
| Substitute | Substitute(target_string,search_string,replacement_string) |
| Trim | Trim(expression) |
| Undrill | Undrill(metric) |
| Upper | Upper(expression) |
| Value | Value(value[,pattern]) |

## Table transformation functions

| Function | Syntax |
| --- | --- |
| Use_Map_Grid | Use_Map_Grid(table:source_column[,notation]) |
| Use_Map_Table | Deprecated. Replaced by Use_Map_Grid. |

## Apptio project related functions

| Function | Syntax |
| --- | --- |
| DomainName | DomainName( ) |
| ProjectExists | ProjectExists(domain:project) |
| ProjectName | ProjectName ( ) |

## Reports functions

| Function | Syntax |
| --- | --- |
| GetLastFilterColumn | GetLastFilterColumn() |
| GetLastFilterValue | GetLastFilterValue(column) |
| GetReportName | GetReportName() |
| GetReportPath | GetReportPath() |
| Icon | Icon(["icon-type"], expression, expression+) |
| ObjectName | ObjectName() |
| Sparkline | Sparkline(past,future,column) |
