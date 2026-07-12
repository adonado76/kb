---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Introduction to formulas and functions"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Introduction to formulas and functions"
source_path: "SSWRJM/studio/formulas-and-functions/introduction-to-formulas-and-functions.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Introduction to formulas and functions

*Applies to : TBM Studio 12.0 and later*

You can use formulas to insert calculated values into a table column or a metric. A function is a predefined procedure that can be used in a formula to simplify the coding of complex calculations.

- The Value , Value Override , and Possible Values fields for a data set column.
- The Value Calculation field for a metric.
- The formula bar in the Report ribbon.
- A unit driver definition.

## Formulas

An expression is a combination of symbols and operators that can be evaluated to obtain a single data value. Simple expressions can be a single constant, variable, column, or scalar function. Operators can be used to join two or more simple expressions into a complex expression.

- Constants
- Column names
- Formulas
- Functions

A string expression evaluates to a string. A numeric expression evaluates to a number. A date expression evaluates to a date. Many functions take expressions as their arguments.

The format for formulas is:

=expression

The following example is a simple formula that multiplies the value in the Rate column by the value in the Time column.

=Rate*Time

## Functions

A function is a predefined procedure that inserts a value into a table or model. The format for functions is:

=Function_Name(arguments)

Function names are shown in MixedCase, but function names are not case sensitive. Arguments represent the input data that the function requires. The following example shows a call to the function Max, with the required arguments, which in this case are column names. This function evaluates the values in the columns SalesEast and SalesWest and returns the higher of the two values.

=Max(SalesEast,SalesWest)

For detailed descriptions of all the functions, see Functions - annotated list .

## Where functions can be used

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic text
- Allocation source formulas

The function descriptions include a list of the formally supported places where a function can be used. A function may work else where, but its behavior will be inconsistent.
