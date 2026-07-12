---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "TableMatch function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "TableMatch function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/tablematch.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# TableMatch function

*Returns a value based on a rules table that functions like a set of IF statements. Each row in the rules table defines one rule. Conditions in the same row are combined with AND, and values within the same cell are treated as OR conditions.*

The TableMatch function replaces long, complex IF statements. It uses a rules table to capture the information contained in the IF statements. In the table, each column represents an AND statement. Entries within a column separated by a comma represent an OR statement. The last column in the table represents the value that will be returned by the function. If no rows evaluate to true, the value in the last row in the table is the returned as the result.

## Sort feature

- sort=ColumnName
- sortOrder

defaults to ascending if no parameter

sortOrder=desc for descending

Example:

Ascending: Matched Result =TableMatch(Rules_Tablename, Value, sort=ColumnName_to_Sort)

Descending: Matched Result =TableMatch(Rules_Tablename, Value, sort=ColumnName_to_Sort, sortOrder=desc)

- exclude optional param to the tablematch() function.

Example:

=TABLEMATCH(RulesData,Value,exclude=Foo,exclude={Bar},exclude=Baz)

From version 12.5+, the TableMatch() sort column feature also includes an optional "exclude" param to the tablematch() function. See the syntax for example.

Here is an example of a rules table:

| A | B | C |
| --- | --- | --- |
| Seattle | Windows, UNIX | server |
| Seattle | laptop | mobile |
| Seattle | PC | desktop |
| Workstation | monitor | LCD |
| Workstation | developer | dual core |
|  |  | unknown |

- First row: If Seattle and Windows or UNIX, then server.
- Fourth row: If Workstation and monitor, then LCD.
- Last row: If none of the rules evaluates to true, return the value "unknown."

The function supports both text and numbers.

Watch this video from Apptio Education Services: The TableMatch Function .

## Rules table values supported

You can preface text with the ! symbol to search for entries that do not contain the text. For numbers, you can use the standard operators: =,<, <=, >, >=,!=. To search for an empty cell, enter the word BLANK in the filter box. To search for cells that are not empty, enter ! BLANK in the filter box. The * wild card is supported. The search options are summarized in the table below.

| Option | Description |
| --- | --- |
| text | Search for "text." Commas can be escaped using backslash character. For example, "ABC\, Inc" would march "ABC, Inc". |
| text1,text2,text...n | Search for entries that contain one of two or more text strings. This is an "or" operation. DO NOT place the values inside parentheses. |
| !text | Search for entries that do not contain "text." |
| !(text1,text2,text...n) | Search for entries that do not contain two or more text strings. This is an AND operation. An entry will match only if it does not contain all of the text strings. |
| BLANK | Enter this word to search for empty cells. |
| !BLANK | Enter this word to search for cells that are not empty. |
| = > < >= <= != | Use these operators with number columns. A comma can be used as an "or" operator. For example: =10,=20 can be read as "equal to 10 or equal to 20." A comma can be used as an "and" operator when enclosed in parentheses. For example: (>10,<20) can be read as "greater than 10 and less than 20." |
| *text text* text*text *text* | The * indicates any number of characters coming before, after, or in the middle of a text string. |

## Syntax

- sort is optional
- sortOrder is optional, defaults to ascending
- exclude is optional

For versions prior to 12.5:

```
TableMatch(Rules Table, Column[,
          suppressNullReturnsOnMatch=true])
```

For version 12.5+:

```
TableMatch(Rules Table, Column[, specifiedColumn=column_name, useRegex=false,
          suppressNullReturnsOnMatch=true])
```

## Arguments

Rules Table

The name of the table containing the rules.

Column

The column in the rules table that contains the value that will be returned by the function.

Do not use curly braces around the column name.

Example :

Correct: =Tablematch(Rules Table,Server-Unix)

Incorrect: =Tablematch(Rules Table,{Server-Unix})

suppressNullReturnsOnMatch

If this parameter is included, the function will not return null values.

useRegex (Supported in TBM Studio 12.5+; Learn more )

If this parameter is included, he function will use regular expressions when matching. The match table is treated as regular expressions.

For more information on regex syntax or to test your own regex statements, visit http://www.rexegg.com/regex-quickstart.html and regex101.com .

specifiedColumn (Supported in TBM Studio 12.5+; Learn more )

If this parameter is included, the function returns the value from the specified source table column if no rule is matched.

## Return type

String

Notes :

This function is not supported in the Ribbon formula bar or in the data preview function on the Data tab.

## Examples

=TableMatch(Cost Center Rules,Cost Center, sort=Cost Center, sortOrder=asc, exclude=SomeColumn1, exclude=SomeColumn2)

Assume you have general ledger data such as the following in a table called Cost Center:

| Acct No | Code | Cost | Date |
| --- | --- | --- | --- |
| 100 | RSF | 1,000 | 6/3/2010 |
| 200 | RRT | 2,000 | 6/8/2010 |
| 300 | CAC | 1,500 | 6/8/2010 |
| 400 | CAC | 3,500 | 6/12/2010 |
| 500 | SIS | 6,000 | 6/18/2010 |
| 600 | SIS | 5,000 | 6/21/2010 |
| 900 | ACD | 4,500 | 6/21/2010 |

- Software
- Network
- Servers
- Support
- Data center

To do that, you want to create a new column in the general ledger table shown above called Cost Center . To populate the new column, you create a new data set called Cost Center Rules that will serve as the rules table. The rules table is shown below:

| Acct No | Code | Cost Center |
| --- | --- | --- |
| 100 | RSF,RSG | Software |
| 200 | RRT | Network |
| 300 | CAC,CAD | Servers |
| 400 | CAC,CAD | Support |
| 500,600 | SIS | Data Centers |
|  |  | Unknown |

- The Acct No and Code columns are used to create an AND statement. For example, the first row would read as: If Acct No equals 100 and Code equals RSF or RSG, then Cost Center is Software.
- The last row provides the default value of "Unknown" if none of the rules evaluate to true.

The following TableMatch function is entered as the value for the new column:

```
=TableMatch(Cost Center Rules,Cost
      Center)
```

In the function, Cost Center Rules is the name of the rules table and Cost Center is the name of the column containing the results.

After applying the TableMatch function, the general ledger table looks like the following table:

| Acct No | Code | Cost | Date | Cost Center |
| --- | --- | --- | --- | --- |
| 100 | RSF | 1,000 | 6/3/2010 | Software |
| 200 | RRT | 2,000 | 6/8/2010 | Network |
| 300 | CAC | 1,500 | 6/8/2010 | Servers |
| 400 | CAD | 3,500 | 6/12/2010 | Support |
| 500 | SIS | 6,000 | 6/18/2010 | Data Centers |
| 600 | SIS | 5,000 | 6/21/2010 | Data Centers |
| 900 | ACD | 4,500 | 6/21/2010 | Unknown |
