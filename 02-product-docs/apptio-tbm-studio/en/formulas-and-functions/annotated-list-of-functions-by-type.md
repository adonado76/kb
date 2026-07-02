---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Annotated list of functions by type"
breadcrumb: []
source_path: "formulas-and-functions/annotated-list-of-functions-by-type.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Annotated list of functions by type

Applies to: TBM Studio 12.0 and later

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

| Function | Description |
| --- | --- |
| [CopyTable](functions/copytable.htm "(Opens in a new tab or window)") | ``` CopyTable("Source Table","Destination Project","Destination Data Set","Time               Period to Copy To") ``` |
| [GetInfo](functions/getinfo.htm "(Opens in a new tab or window)") | `GETINFO("attribute1",["DomainName:ProjectName"]` |
| [If](functions/if.htm "(Opens in a new tab or window)") | `If(filter_expression,true_expression,false_expression)` |
| [Key](functions/key-function.htm "(Opens in a new tab or window)") | `Key(value1,value2,...)` |
| [PeriodsInHalf](functions/periodsinhalf.htm "(Opens in a new tab or window)") | `PeriodsInHalf(half)` |
| [PeriodsInQuarter](functions/periodsinquarter.htm "(Opens in a new tab or window)") | `PeriodsInQuarter(quarter)` |
| [PeriodsInYear](functions/periodsinyear.htm "(Opens in a new tab or window)") | `PeriodsInYear()` |
| [Replace](functions/replace.htm "(Opens in a new tab or window)") | `=Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)` |
| [Row](functions/row.htm "(Opens in a new tab or window)") | ``` Row(               ) ``` |
| [RowCount](functions/rowcount.htm "(Opens in a new tab or window)") | `RowCount(table)` |
| [TableMatch](functions/tablematch.htm "(Opens in a new tab or window)") | `TableMatch(Table,Column)` |
| [UniqueCount](functions/uniquecount.htm "(Opens in a new tab or window)") | `UniqueCount(column)` |
| [UniqueValues](functions/uniquevalues.htm "(Opens in a new tab or window)") | `UniqueValues(column)` |

## Date and time functions

| Function | Syntax |
| --- | --- |
| [CurrentDate](functions/currentdate.htm "(Opens in a new tab or window)") | `CurrentDate([format_string])` |
| [Days](functions/days.htm "(Opens in a new tab or window)") | `Days(date_expression)` |
| [DurationOfMonth](functions/durationofmonth.htm "(Opens in a new tab or window)") | `DurationOfMonth ("d/h/m/s/S", [month[, year]])` |
| [Elapsed](functions/elapsed.htm "(Opens in a new tab or window)") | `Elapsed(startDate,endDate[,table[,startCol,endCol])` |
| [Hours](functions/hours.htm "(Opens in a new tab or window)") | `Hours(date_expression)` |
| [Minutes](functions/minutes.htm "(Opens in a new tab or window)") | `Minutes(date_expression)` |
| [Months](functions/months.htm "(Opens in a new tab or window)") | `Months(date_expression)` |
| [Now](functions/now.htm "(Opens in a new tab or window)") | `Now(metric)` |
| [Period](functions/period.htm "(Opens in a new tab or window)") | `Period(["time_period"][n])` |

## Formatting functions

| Function | Syntax |
| --- | --- |
| [Currency](functions/currency.htm "(Opens in a new tab or window)") | `Currency(column[,pattern[;negative_pattern]])` |
| [DateFormat](functions/dateformat.htm "(Opens in a new tab or window)") | `DateFormat(date_expression,format_string)` |
| [NumberFormat](functions/numberformat.htm "(Opens in a new tab or window)") | `NumberFormat(column[,pattern[;negative_pattern]])` |
| [StatusIcon](functions/statusicon.htm "(Opens in a new tab or window)") | `StatusIcon(green_expression,red_expression)` |

## Math functions

| Function | Syntax |
| --- | --- |
| [Abs](functions/abs-function.htm "(Opens in a new tab or window)") | `Abs(column)` |
| [Annual](functions/annual.htm "(Opens in a new tab or window)") | `Annual(metric[,delta[,type]])` |
| [Annualize](functions/annualize.htm "(Opens in a new tab or window)") | `Annualize(metric)` |
| [Average](functions/average.htm "(Opens in a new tab or window)") | `Average(rollup_operator column)` |
| [DateSum](functions/datesum.htm "(Opens in a new tab or window)") | `DateSum()` |
| [Large](functions/large.htm "(Opens in a new tab or window)") | ``` Large               (rollup_operator column) ``` |
| [Max](functions/max.htm "(Opens in a new tab or window)") | `Max(numeric_expression,numeric_expression)` |
| [Min](functions/min.htm "(Opens in a new tab or window)") | `Min(numeric_expression,numeric_expression)` |
| [Mod](functions/mod.htm "(Opens in a new tab or window)") | `Mod(number,divisor)` |
| [Percentile](functions/percentile.htm "(Opens in a new tab or window)") | `Percentile(rollup_operator column,percentage)` |
| [Power](functions/power.htm "(Opens in a new tab or window)") | `Power(base,exponent)` |
| [PreviousMonth](functions/previousmonth.htm "(Opens in a new tab or window)") | `PreviousMonth(metric)` |
| [PreviousYear](functions/previousyear.htm "(Opens in a new tab or window)") | `PreviousYear(metric)` |
| [QuarterToDate](functions/quartertodate.htm "(Opens in a new tab or window)") | `QuarterToDate(column)` |
| [Rand](functions/rand.htm "(Opens in a new tab or window)") | ``` Rand(               ) ``` |
| [Ratio](functions/ratio.htm "(Opens in a new tab or window)") | `Ratio(column,~column)` |
| [Round](functions/round.htm "(Opens in a new tab or window)") | `Round(numeric_expression,digits)` |
| [SLN](functions/sln.htm "(Opens in a new tab or window)") | `SLN(original,salvage,lifespan)` |
| [Small](functions/small.htm "(Opens in a new tab or window)") | `Small(rollup_operator column)` |
| [Sum](functions/sum.htm "(Opens in a new tab or window)") | `Sum(column)` |
| [TimePeriod](functions/timeperiod.htm "(Opens in a new tab or window)") | `TimePeriod(metric,time)` |
| [Trunc](functions/trunc.htm "(Opens in a new tab or window)") | `Trunc(value)` |
| [Untag](functions/untag.htm "(Opens in a new tab or window)") | `Untag(value)` |
| [YearToDate](functions/yeartodate.htm "(Opens in a new tab or window)") | `YearToDate(column)` |

## String functions

| Function | Syntax |
| --- | --- |
| [CapFirstLetter](functions/capfirstletter.htm "(Opens in a new tab or window)") | `CapFirstLetter(string)` |
| [Eval](functions/eval.htm "(Opens in a new tab or window)") | `Eval(string)` |
| [EvalWiki](functions/evalwiki.htm "(Opens in a new tab or window)") | `EvalWiki(wikitext)` |
| [Find](functions/find.htm "(Opens in a new tab or window)") | `Find(search_string,in_string,[starting_position])` |
| [IPLookup](functions/iplookup.htm "(Opens in a new tab or window)") | ``` IPLookup(source_column,lookup_table,matching_column,replacement_column               ,default_value) ``` |
| [IsNumeric](functions/isnumeric.htm "(Opens in a new tab or window)") | `IsNumeric("value") or ISNUMERIC({column name})` |
| [Left](functions/left.htm "(Opens in a new tab or window)") | `Left(string[,count])` |
| [Len](functions/len.htm "(Opens in a new tab or window)") | `Len(string_expression)` |
| [Lookup and Lookup\_Wild](functions/lookupandlookup_wild.htm "(Opens in a new tab or window)") | ``` Lookup(source_column,lookup_table,matching_column,replacement_column               [,leave_original_value][,replace_nulls][,ignore_case]) ``` |
| [LookupEx](functions/lookupexandlookupex_wild.htm "(Opens in a new tab or window)") | ``` LookupEx(source_column,lookup_table,matching_column,replacement_column               [,leave_original_value][,replace_nulls][,ignore_case]) ``` |
| [LookupFromPath](functions/lookupfrompath.htm "(Opens in a new tab or window)") | `LookupFromPath("path",target_column,lookup_column,lookup_value_column)` |
| [LookupObjectTotalAllocated](functions/lookupobjecttotalallocated.htm "(Opens in a new tab or window)") | `LookupObjectTotalAllocated(metric)` |
| [LookupObjectTotalValue](functions/lookupobjecttotalvalue.htm "(Opens in a new tab or window)") | ``` LookupObjectTotalValue(object[,metric  [, driver]]) ``` |
| [LookupObjectUnitAllocated](functions/lookupobjectunitallocated.htm "(Opens in a new tab or window)") | ``` LookupObjectUnitAllocated  (sourceObject,destObject,metric,  columnInLocalTable,columnInSourceObjectTable) ``` |
| [LookupObjectUnitValue](functions/lookupobjectunitvalue.htm "(Opens in a new tab or window)") | ``` LookupObjectUnitValue  (object,metric,targetCol,lookupCol[,driver]) ``` |
| [LookUpMetric](functions/lookupmetric.htm "(Opens in a new tab or window)") | `LookUpMetric(metric,column)` |
| [Lower](functions/lower.htm "(Opens in a new tab or window)") | `Lower(expression)` |
| [Mid](functions/mid.htm "(Opens in a new tab or window)") | `Mid(string,start[,count])` |
| [Pluralize](functions/pluralize.htm "(Opens in a new tab or window)") | `Pluralize(noun[,count])` |
| [Right](functions/right.htm "(Opens in a new tab or window)") | `Right(string[,count])` |
| [Search](functions/search.htm "(Opens in a new tab or window)") | `Search(search_string,in_string[,starting_position])` |
| [Split](functions/split.htm "(Opens in a new tab or window)") | `Split(expression,n[,delimiters])` |
| [Substitute](functions/substitute.htm "(Opens in a new tab or window)") | `Substitute(target_string,search_string,replacement_string)` |
| [Trim](functions/trim.htm "(Opens in a new tab or window)") | `Trim(expression)` |
| [Undrill](functions/undrill.htm "(Opens in a new tab or window)") | `Undrill(metric)` |
| [Upper](functions/upper.htm "(Opens in a new tab or window)") | `Upper(expression)` |
| [Value](functions/value.htm "(Opens in a new tab or window)") | `Value(value[,pattern])` |

## Table transformation functions

| Function | Syntax |
| --- | --- |
| [Use\_Map\_Grid](functions/usemapgrid.htm "(Opens in a new tab or window)") | `Use_Map_Grid(table:source_column[,notation])` |
| [Use\_Map\_Table](functions/usemaptable.htm "(Opens in a new tab or window)") | ``` Deprecated.               Replaced by Use_Map_Grid. ``` |

## Apptio project related functions

| Function | Syntax |
| --- | --- |
| [DomainName](functions/domainname.htm "(Opens in a new tab or window)") | ``` DomainName(               ) ``` |
| [ProjectExists](functions/project-exists-function.htm "(Opens in a new tab or window)") | `ProjectExists(domain:project)` |
| [ProjectName](functions/projectname.htm "(Opens in a new tab or window)") | ``` ProjectName               ( ) ``` |

## Reports functions

| Function | Syntax |
| --- | --- |
| [GetLastFilterColumn](functions/getlastfiltercolumn.htm "(Opens in a new tab or window)") | `GetLastFilterColumn()` |
| [GetLastFilterValue](functions/getlastfiltervalue.htm "(Opens in a new tab or window)") | `GetLastFilterValue(column)` |
| [GetReportName](functions/getreportname.htm "(Opens in a new tab or window)") | `GetReportName()` |
| [GetReportPath](functions/getreportpath.htm "(Opens in a new tab or window)") | `GetReportPath()` |
| [Icon](functions/icon.htm "(Opens in a new tab or window)") | `Icon(["icon-type"], expression, expression+)` |
| [ObjectName](functions/objectname.htm "(Opens in a new tab or window)") | `ObjectName()` |
| [Sparkline](functions/sparkline.htm "(Opens in a new tab or window)") | `Sparkline(past,future,column)` |
