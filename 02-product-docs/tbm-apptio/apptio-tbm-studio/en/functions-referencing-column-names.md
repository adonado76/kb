---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Referencing column names"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Referencing column names"
source_path: "SSWRJM/studio/formulas-and-functions/referencing-column-names.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Referencing column names

*Applies to : TBM Studio 12.0 and later*

Column names are case sensitive and can include spaces. When referencing column names, the best practice is to enclose column names in curly braces, and this is required when column names contain special characters. By referencing grouped columns using rollup operators, you can cause a function to evaluate the values that contributed to the rollup, rather than the rolled-up valued.

## General rules

Below are the general rules for referencing columns in data sets.

| To reference a column in: | Use this format: |
| --- | --- |
| the same data set or table | {column name} |
| a different data set or table | {data set name}:{column name} |
| a data set in a different project in the same domain | project name!{data set name}:{column name} |
| a data set in a different project in a different domain | domain name:project name!{data set name}:{column name} |

## Referencing column names: special characters

In functions, if you reference a column name that contains any special characters, you must enclose the column name in curly braces: { }.

The following table lists the special characters.

| Character | Name |
| --- | --- |
| & | Ampersand |
| * | Asterisk |
| @ | At sign |
| ) | Close parenthesis |
| : | Colon |
| , | Comma |
| = | Equals sign |
| ! | Exclamation point |
| / | Forward slash |
| - | Hyphen |
| [ | Left bracket |
| ( | Open parenthesis |
| . | Period |
| + | Plus sign |
| ] | Right bracket |
| " | Straight double quotes |
| ~ | Tilde |

## Example column name with a special character

To reference a column name containing an asterisk (*), such as Hours*Rate, enclose the column name in brackets { } to differentiate it from the formula Hours*Rate, as shown in the following example:

Round({Hours*Rate},2)

You must also use curly braces around a column name if it contains a keyword (function name). For example, the column name Diff contains if , which is the name of a function, so you must reference that column name in curly braces: {Diff}.

Best Practice: Always enclose column names in curly braces.

## Referencing grouped columns

When referencing a grouped column, a function evaluates the rolled-up value from the grouping. However, putting an @ (at sign) before the column name, as in (@column), causes some functions to evaluate the values that contributed to the rollup. The @ can be used like this with the following functions: Average , Large , Percentile , and Small .

For example, consider the following tables. The following shows a table before grouping.

| c | c1 |
| --- | --- |
| a | 1 |
| a | 2 |
| a | 3 |
| b | 4 |
| b | 5 |
| b | 6 |
| c | 7 |
| c | 8 |
| c | 9 |

Grouping the data in the table above by column c gives the results shown in the table below. Column c1 now contains the sums of distinct units in column c. The table also contains a new column called .Count, which contains the number of rows in each group.

| c | c1 | .Count |
| --- | --- | --- |
| a | 6 | 3 |
| b | 15 | 3 |
| c | 24 | 3 |

Putting an at sign ( @ ) before the column name causes certain functions to evaluate the values that contributed to the rollup (Table 1) for each grouping. Calling the function =Small(@c1) against the grouped table (Table 2) returns the smallest value in the pre-rollup data (Table 1) for each group.

The following table shows the results when column c2 contains the function =Small(@c1).

| c | c1 | c2 | .Count |
| --- | --- | --- | --- |
| a | 6 | 1 | 3 |
| b | 15 | 4 | 3 |
| c | 24 | 7 | 3 |

## Reserved words

- if
- then
- else
- end
- sub
- true
- false
- exclude

For example:

| Old | New |
| --- | --- |
| sub | {sub} |
| sub A | {sub A} |
| SUB b | {SUB b} |
| end x | {end x} |
