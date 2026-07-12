---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Functions: Annotated list"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Functions: Annotated list"
source_path: "SSWRJM/studio/formulas-and-functions/functions/functions.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Functions: Annotated list

*Applies to : TBM Studio 12.0 and later*

Below is an annotated list of all functions in alphabetical order, with links to details on each.

| Function | Description |
| --- | --- |
| Abs | Returns the absolute value of a number.Syntax: Abs(column)Example: =Abs(Balance) |
| Annual | Returns the value of a specified metric in the same table for a specified fiscal or calendar year, summing the values for the entire year.Syntax: Annual(metric[,delta[,type]])Example: =Annual(Cost) |
| Annualize | Calculates the projected total annual value of a metric for the fiscal year based on the value of the metric up to the current month.Syntax: Annualize(metric)Example: =Annualize(Cost) |
| Average | Returns the average value in a specified column.Syntax: Average([rollup_operator]column)Example: =Average(Space) |
| Bullet | Generates a bullet chart within a table.Syntax: Bullet(performance_measure)Example: =Bullet(Cost,target=Budget) |
| CapFirstLetter | Capitalizes the first letter of each word in the string argument, and makes all other letters lowercase.Syntax: CapFirstLetter(string)Example: =CapFirstLetter(DATA CENTER BUDGET) |
| ColumnExists | Use this function to determine if a column exists in a table.Syntax: ColumnExists(column_name)Example: =ColumnExists(Business_Unit_Name) |
| ConvertCurrencyFromBase | Multiplies the value by the rate in the Currency Exchange table.Syntax: ConvertCurrencyFromBase(source column,"currency code","rate type")Example: ConvertCurrencyFromBase(Cost,"EUR","Plan") |
| ConvertCurrencyToBase | Divides the value by the rate in the Currency Exchange table.Syntax: ConvertCurrencyToBase(source column,"currency code","rate type")Example: ConvertCurrencyFromBase(Cost,"EUR","Plan") |
| CopyTable | Copies tables and raw data sets from within a project or from one project to another project within the same instance.Syntax: CopyTable("Source Table","Destination Project","Destination Data Set","Time Period to Copy To")Example: CopyTable("customer.com%Project+A/Data/946684800000/Example+Data+Set/", "customer.com:Project+B", "Example Data Set", "Eon:2000") |
| Currency | Formats numbers and adds the appropriate currency sign to the beginning of the return value.Syntax: Currency(column[,"pattern[;negative_pattern]]")Example: =Currency({Cost},"#,###.00") |
| CurrentDate | Returns the starting date of the currently selected time period, if time is enabled. If not, returns Eon 2000.Syntax: CurrentDate([format_string])Example: =CurrentDate("MM/dd/yyyy") |
| DateFormat | Converts a date expression to a specified date format.Syntax: DateFormat(date_expression,"format_string",["time_zone"])Example: =DateFormat(Column1,"MM/dd/yy hh:mm:ss a") |
| DateSum | Returns the sum of all values in columns with column names that conform to the standard application date formats.Syntax: DateSum() |
| Days | Converts a specified date to a double value, which can be used in formulas. The double value is the number of days since January 1, 1970.Syntax: Days(date_expression)Example: =(Days(ProjectEnd)-Days(ProjectStart)*ProjectCostPerDay) |
| DomainName | Returns the name of currently active domain.Syntax: DomainName() |
| DurationOfMonth | Returns the number of days, hours, minutes, seconds, or milliseconds in a month.Syntax: DurationOfMonth ("d/h/m/s/S", [month[, year]])Example: =DurationOfMonth("m",11,2015) |
| DynamicColumn() | Replaces the Eval() function. Syntax: DynamicColumn() Example: See Dynamic Columns. |
| Elapsed | Calculates the time between two dates in seconds. To handle time period exclusions, the function relies on an exclusions table.Syntax: Elapsed(startDate,endDate[,exclustion table[,startCol,endCol])Example: =Elapsed("04/23/2015 18:00","04/26/2015 11:00",Exclusions,From,To) |
| Eval | Takes a string that looks like an expression and evaluates it as if it were an expression. |
| EvalWiki | Evaluates Wiki text in a formula or text string and formats it so it can be displayed on a report.Syntax: EvalWiki(wikitext)Example: =EvalWiki("["&amp;"[/myObject/!FILTER[myColumn="""&amp;myColumn&amp;"""]/ myReport|click here to see my report") |
| Find | Searches for a specified string (search_string) within another string (in_string) and returns a value representing the position in the in_string, counting from left to right, of the first character of the search_string. This function is case sensitive.Syntax: Find(search_string,in_string,[starting_position])Example: =Search("c", "58762 Functional Actuals", 12) |
| GetGroupbyColumn | In a table that has been filtered by one or more columns and grouped by another column, this function returns the name of the column used to group the table.Syntax: GetGroupbyColumn() |
| GetInfo | Returns a wide range of information about a project.Syntax: GETINFO("attribute",["DomainName:ProjectName"])Example: =GetInfo("project.startDate") |
| GetLastFilterColumn | Returns the name of the last column to which a filter was applied.Syntax: GetLastFilterColumn() |
| GetLastFilterValue | Returns the last value applied to a filter.Syntax: GetLastFilterValue(column) |
| GetLastPublishTime | Returns the last publish time the Editable table data was published to the transform table Syntax: GetLastPublishTime(“transform_table_name”) |
| GetNextPublishTime | Returns the next publish time the Editable table data was published to the transform table Syntax: GetNextPublishTime(“TableName”) |
|  |  |
|  |  |
| GetReportName | Returns the name of the report where the function is placed.Syntax: GetReportName() |
| GetReportDisplayName | Returns the alias of a report where the function is placed.Syntax: =GetReportDisplayName()Available beginning with Studio 12.9 |
| GetReportPath | Returns the path of the report where the function is placed.Syntax: GetReportPath() |
| GetTimeOffset | Determines the offset of the current period to the current month, quarter, half year, or whole year. For example, if it is April 2017, and you set the function to determine the offset from the end of the quarter (June 2017), it would return a value of 2.Syntax: GetTimeOffset(granularity,start/end,span,[period]) |
| Hours | Converts a specified date to a double value, which can be used in formulas. The double value is the number of hours since January 1, 1970.Syntax: Hours(date_expression)Example: =Hours(Date Submitted) |
| Icon | Evaluates two or more expressions and returns one of up to five HTML &lt;img&gt; tags for colored icons based on the results.Syntax: Icon(["icon-type"],expression,expression+)Example: Icon("3arrows",Avg CPU Util&gt;65,Avg CPU Util&gt;50,Avg CPU Util&gt;0) |
| If | Evaluates a specified filter expression. If true, it returns the value of the specified true expression; if false, it returns the value of the specified false expression. The function supports both AND and OR operations.Syntax: If(filter_expression,true_expression,false_expression)Example: =If({Consulting Hours.Type}="Billable",{Consulting Hours.Hours},0) |
| IPLookup | Finds an IP address in a specified source column in the current table and searches for an IP address in a specified column of a lookup table.Syntax: IPLookup(source_column,lookup_table,matching_column,replacement_column,"default_value") |
| IsNumeric | Evaluates a string or column name to determine if it is a number.Syntax: IsNumeric("value") or IsNumeric({column name})Example: IsNumeric({Location}) |
| Key | Defines a value that is the combination of two or more columns and/or a text string or a formula.Syntax: Key(value1,value2,...)Example: =key("Key:",Application,Service Level) |
| Large | Returns the largest value in a specified column.Syntax: Large([rollup_operator]column)Example: =Large(Square Feet) |
| LargeIf | Returns the largest value in a category in a transform.Syntax: LargeIf(category_column, value_column, [criteria])Example: =LargeIf(Category, Average Price, Compare Category) |
| Left | Returns a specified number of characters from a string (including white spaces), starting from the left.Syntax: Left(string[,count])Example: =Left({Application},3) |
| Len | Returns the length of a string.Syntax: Len(string_expression)Example: =Len({Ticket Description}) |
| Lookup and Lookup_Wild | Finds the value in a specified source column in the current table and searches for a matching value in a specified column of a lookup table. Lookup_Wild supports regular expressions in the matching column.Syntax: Lookup(source_column,lookup_table,matching_column,replacement_column[,leave_original_value][,replace_nulls][,ignore_case])Example: =Lookup(Location,Time Zone,City,Time Zone) |
| LookupContains | Performs a multi-column partial-match lookup. The main use is for data cleansing using one-to-many lookups (single source, multiple target columns) and many-to-one lookups (multiple source, single target columns).Syntax: varies with the type of lookup. |
| LookupEx | LookupEx is the same as Lookup, except that LookupEx returns values for all matches rather than just the last one.Syntax: LookupEx(source_column,lookup_table,matching_column,lookup_value_column[,leave_original_value ][,replace_nulls][,ignore_case ]) |
| Lookup_From_Editable | Brings columns from an editable table via a lookup to include it in report tables that are displaying either data from a different editable table, or data from a transform/model. It retrieves values and returns the sum of the values. |
| LookupFromPath | Retrieves values from any table in any domain and project. If there are multiple matches, the function returns {VARIOUS} for text columns and a sum for numeric columns.Syntax: LookupFromPath("lookup_table_path",source_column,matching_column,lookup_value_column)Example: =LookupFromPath(“apptio.com:BankDemo/Data/January:2010/GL Actuals” DomainName()&amp; “:” &amp; ProjectName() &amp; “/Data/” &amp; CurrentDate(“MMMM:yyyy”) &amp; “/&lt;some dataset name here&gt;”VIDEO: What Causes Various? |
| LookupMetric | Looks up a column from another metric using the same data path. It takes the current path, substitutes a new metric, and re-runs the model before looking up a value in a specified column.Syntax: LookupMetric(metric,column)Example: !NEWCOLUMN[{NewCol}=LookupMetric(Chargeback,{ASP.NET})] |
| LookupObjectTotalAllocated | Finds the value allocated from a source object to one or more target objects in a model.Syntax: LookupObjectTotalAllocated(metric) |
| LookupObjectTotalValue | Finds the total value of an object. If the metric parameter is not used, the function uses the current model. If the driver parameter is supplied, it looks up the total value of the driver specified.Syntax: LookupObjectTotalValue(object[,metric[, driver]])Example: =LookupObjectTotalValue(Object C,Cost,Object A) |
| LookupObjectUnitAllocated | Looks up the value allocated between two objects for a particular metric on a unit-by-unit basis.Syntax: LookupObjectUnitAllocated(sourceObject,destObject,metric,columnInLocalTable,columnInSourceObjectTable)Example: !NEWCOLUMN[alloc=LookupObjectUnitAllocated(Support,Services,Cost,ID,ID)][canSum] |
| LookupObjectUnitValue | Finds the value of a unit for an object. If the driver parameter is supplied, it looks up the total value of the driver specified.Syntax: LookupObjectUnitValue(object,metric,targetCol,lookupCol[,driver])Example: =SOURCE*LookupObjectUnitValue(OS Direct,Cost,OS Indirect.OS,OS Direct.OS)/LookupObjectTotalValue(OS Direct,Cost) |
| Lower | Converts a specified string to lowercase. Can reference a column.Syntax: Lower(expression)Example: =Lower("HWbudget" ) |
| Max | Compares two expressions and returns the greater value.Syntax: Max(numeric_expression 1,numeric_expression2 )Example: =Max(42*Hours,Max(3,7)) |
| Mid | Returns a specified number of characters from a string (including white spaces), starting a specified number of characters from the left.Syntax: Mid(string,start,count)Example: =Mid("123456",2,3) |
| Min | Compares two expressions and returns the lesser value.Syntax: Min(numeric_expression 1,numeric_expression 2)Example: =Min(42*Hours,Min(3,7)) |
| Minutes | Converts a specified date to a double value, which can be used in formulas. The double value is the number of minutes since January 1, 1970.Syntax: Minutes(date_expression)Example: =(Minutes({SupportTicket_End}))-(Minutes({SupportTicket_Start})) |
| Mod | Takes one number and divides it by a second number, and then returns the remainder.Syntax: Mod(number,divisor)Example: =Mod(5,3) |
| Months | Converts a specified date to a double value, which can be used in formulas. The double value is the number of days, hours, etc. since January 1, 1970.Syntax: Months(date_expression)Example: =((Months(ProjectEnd)-Months(ProjectStart))*ProjectCostPerMonth) |
| Now | Returns the current date and time as a UNIX time stamp based on the server time.Syntax: Now()Example: =TRUNC(Days(End Date)-Days(Now()))+1 |
| NumberFormat | Converts numbers in Label columns to a specified format.Syntax: NumberFormat({column}[,"pattern[;negative_pattern]"])Example: =NumberFormat(Cost,"$###,###.##") |
| ObjectName | Returns the name of the object driving the current report.Syntax: ObjectName()Example: &lt;%=ObjectName()%&gt; |
| Percentile | Returns a specified percentile for a specified column.Syntax: Percentile([rollup_operator]column,percentage)Example: =Percentile(Servers,50) |
| Period | Returns a string that represents the selected time period, based on a specified example format.Syntax: Period(["time_period"][n])Example: Total Cost: &lt;%=Cost%&gt; &lt;%=Period("per month")%&gt; |
| PeriodsInHalf | Returns the number of periods in the first or second half of the year.Syntax: PeriodsInHalf(half)Example: &lt;%=(PeriodsInHalf(1))%&gt; |
| PeriodsInQuarter | Returns the number of periods in the specified quarter of the year.Syntax: PeriodsInQuarter(quarter)Example: &lt;%=(PeriodsInQuarter(2))%&gt; |
| PeriodsInYear | Returns the number of periods in the year.Syntax: PeriodsInYear()Example: &lt;%=(PeriodsInYear())%&gt; |
| Plural | Converts singular nouns to their plural forms.Syntax: Plural(noun[,count]) |
| Pluralize | Converts singular nouns to their plural forms and capitalizes the first letter in each word.Syntax: Pluralize(noun[,count]) |
| Power | Raises a specified base number to the power of a specified exponent.Syntax: Power(base,exponent)Example: =Power(2,3) |
| PreviousMonth | Returns the value of a specified metric in the current table for the previous month.Syntax: PreviousMonth(metric)Example: =PreviousMonth(Cost) |
| PreviousYear | Returns the sum of a specified metric in the current table for the previous number of periods in a fiscal year. In a 12 period calendar, this would be 12 periods. In a 13 period calendar, this would be 13 periods.Syntax: PreviousYear(metric)Example: =PreviousYear(Cost) |
| ProjectExists | If the specified project exists, the function returns "true." If the name project does not exist, the function returns "false."Syntax: ProjectExists(domain:project) |
| ProjectName | Returns the name of the current project.Syntax: ProjectName( ) |
| Quarter | Returns the value of a specified metric in the same table for a specified quarter, summing the values for the entire quarter.Syntax: Quarter(metric[,delta[,type]])Example: =Quarter(Cost,1) |
| QuarterToDate | Returns the value in a specified metric in the same table for the current fiscal year, summing the values up to and including the selected quarter.Syntax: QuarterToDate(column)Example: =QuarterToDate(Cost) |
| Rand | Returns a random number between 0.0 and 1.0.Syntax: Rand() |
| Ratio | Use in allocation advanced formulas to handle situations where the weighting column values are zero. The function returns a value of 1, evenly spreading the allocation.Syntax: Ratio({column reference},~{column reference}) |
| Replace | Replaces values in one or more columns in a transform table with values from a search and replace table. The function only works on transform tables.Syntax: Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)Example: =Replace((Dept,ID),Search_and_Replace_Table,(Dept,ID),(New_Dept,New_ID),New_ID) |
| ReplaceRegex | Use to cleanse data by replacing text using regular expressions.Syntax: LookupRegex(column_name,match_expression,replacement_expression) |
| Right | Returns a specified number of characters from a string (including white spaces), starting from the right.Syntax: Right(string[,count])Example: =Right("ABC100", 3) |
| Round | Rounds a real number to the specified number of decimal places.Syntax: Round(numeric_expression,digits)Example: =Round(1.23,1) |
| Row | Returns the number of the current row in the current table, starting with zero for the first row.Syntax: Row() |
| RowCount | Returns a count of the total number of rows in a table.Syntax: RowCount([table])Example: =RowCount(Servers) |
| Search | Searches for a specified string (search_string) within another string (in_string) and returns a value representing the position in the in_string, counting from left to right, of the first character of the search_string.Syntax: Search(search_string,in_string[,starting_position])Example: =Search("c", "58762 Functional Actuals", 12) |
| SLN | Returns the straight-line depreciation of an asset for one year.Syntax: SLN(original,salvage,lifespan)Example: =SLN(4000,800,5) |
| Small | Returns the smallest value in a specified column.Syntax: Small([rollup_operator]column)Example: =Small(GB) |
| SmallIf | Returns the smallest value in a category in a transform.Syntax: SmallIf(category_column, value_column, [criteria])Example: =SmallIf(Category, Average Price, Compare Category) |
| SmallAcrossTime | Returns the smallest value in a specified column across one or more periods of time.Syntax: SmallAcrossTime(column, period, period, etc.)Example: =SmallAcrossTime(GB) |
| Sparkline | Creates small trend charts in the cells of tables on reports.Syntax: Sparkline(past,future,column)Example: =Sparkline(4,4,Cost) |
| Split | Returns an element of a delimited string.Syntax: Split(string,n[,delimiters])Example: =Split(Name,1," ") |
| SplitEx | Generates new rows in a table for each element in a table cell.Syntax: SplitEx(column,delimiter)Example: SplitEx(Column A, ",") |
| StatusIcon | Evaluates two expressions and returns one of five HTML <img> tags for colored icons based on the results. This function has been replaced by the function Icon . |
| Substitute | Searches a specified target string for the presence of a specified search string. If the search string is found, it replaces it with a specified replacement string.Syntax: Substitute(target_string,search_string,replacement_string)Example: =Substitute("virtual server","virtual","physical") |
| Sum | Sums the values in a specified column in the unit table of a modeled object.Syntax: Sum(column)Example: =Sum(Cost) |
| SumIf | Adds the values associated with specific entries in a table that match a set of criteria.Syntax: SumIf(key_column,criteria,sum_range)Example: =SumIf(Region,"Americas",Weight) |
| SumIfHierarchy | The SumIfHierarchy function is used to calculate the cost of a service based on the cost of its sub-services.Syntax: SumIfHierarchy(Service,Consumes,Quantity), SumIfHierarchy(Consumes,Service,Quantity,BasePrice)Example: =SumIfHierarchy(Service,Subservice,Quantity) |
| TableInfo | The TableInfo function retrieves metadata, such as the time stamp for the last upload, from a table.Syntax: TableInfo(infoType,<tableName>,[timePeriod])Example: =TableInfo("Last updated by,Servers,Mar:FY2020")Available beginning with Studio 12.9 |
| TableMatch | Use to create complex IF statements using a table-based format. The function supports text and numbers.Syntax: TableMatch(Rules Table,Column)Example: =TableMatch(Cost Center Rules,Cost Center) Syntax: TableMatch(Rules Table,Column, sort=ColumnName_to_Sort, sortOrder=asc|desc, exclude=ColumnName_to_Exclude,exclude=...) Example: =TableMatch(Cost Center Rules,Cost Center, sort=Cost Center, sortOrder=asc, exclude=SomeColumn1, exclude=SomeColumn2) |
| TimePeriod | Returns the value of a specified metric in the same table for the time unit (for example, month) that falls a specified number of time units prior to or after the current time unit.Syntax: TimePeriod(metric,time)Example: =TimePeriod(Sales,-6) |
| Trim | Removes leading and trailing spaces from a specified string.Syntax: Trim(expression)Example: =Trim(" server") |
| Trunc | Truncates a real number to an integer by removing the fractional part of the number.Syntax: Trunc(value)Example: =Trunc(Cost) |
| Undrill | Returns the undrilled down value for a metric.Syntax: Undrill(metric)Example: =Undrill(Cost) |
| UniqueCount | Returns a count of distinct values in a column.Syntax: UniqueCount(table:column)Example: =UniqueCount(Servers:Location) |
| UniqueValues | Returns a list of unique values in a column.Syntax: UniqueValues(table:column)Example: =UniqueValues(Servers:Location) |
| Untag | Directs the application to ignore any tags assigned to drivers in the current model.Syntax: Untag(value)Example: =SOURCE*Untag({Qualified CtB(Cost driver)}) |
| Upper | Converts a specified string to uppercase.Syntax: Upper(expression)Example: =Upper("HWbudget" ) |
| Use_Map_Grid | For table-based allocations, specifies one-to-one unit mappings and a percentage of the source unit's value. This function replaces USE_MAP_TABLE.Syntax: Use_Map_Grid(table:source_column[,notation]) |
| Use_Map_Table | Creates allocations using a manually entered formula.Syntax: Use_Map_Table(table:weight_column[,source_column,target_column][,format)] |
| Value | Converts numeric-looking strings to numbers.Syntax: Value(value[,pattern])Example: =Value(Storage,"#GB") |
| YearToDate | Returns the value in a specified metric in the same table for the current fiscal year, summing the values up to the selected month.Syntax: YearToDate(column)Example: =YearToDate(Cost) |
