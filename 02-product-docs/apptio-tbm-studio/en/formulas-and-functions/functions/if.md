---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "If function"
breadcrumb: []
source_path: "formulas-and-functions/functions/if.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# If function

Applies to: TBM Studio 12.0 and later

Evaluates a specified filter expression. If true, it returns the value of the specified true
expression; if false, it returns the value of the specified false expression. The function supports
both AND and OR operations.

## Where to use

This function can be used in:

- Data sets
- Calculated metrics and reports with metric columns
- Formula columns in report tables
- Dynamic Text

## Syntax

`If(filter_expression,true_expression,false_expression)`

## Arguments

*filter\_expression*

> Specifies a condition to be evaluated as true or false. The format is:
>
> ```
> {column}
>           operator value
> ```
>
> In the expression, *column* is the table.column to filter on, *operator* is one of the
> comparison operators (=, !=, <, >, <=, >=, IN, NOT IN), and *value* is the value for
> comparison. If value is text, it must be enclosed in quotes. You can use functions in the expression
> on both sides of the equation, and embed functions within functions.
>
> For example the *filter\_expression* Cost<10 evaluates to true if the value of Cost is
> less than 10; otherwise, it evaluates to false.
>
> The filter expression supports AND and OR operators.
>
> For example:
>
> ```
> If(filter_expression AND (filter_expression OR
>           filter_expression),true_expression,false_expression)
> ```
>
> The order of evaluation is AND and then OR. Operations within parentheses are evaluated
> first.

Note: You cannot use the word "BLANK" as a keyword in the filter expression as the comparison value.
To represent a blank, enter "" .

*true\_expression*

> Specifies the value to be returned if *filter\_expression* is true. If the true expression is
> text, it must be enclosed in quotes.

*false\_expression*

> Specifies the value to be returned if *filter\_expression* is false. If the true expression
> is text, it must be enclosed in quotes.

## Return type

The return type is the same as the *true\_expression* or *false\_expression*, whichever
is returned.

Notes:

- If you find you are creating a very complex nested IF statement, consider using the TableMatch
  function instead. For more information, see [TableMatch](tablematch.htm "(Opens in a new tab or window)").
- You can use functions inside the If function on both sides of the equation.For example:
  `If(Trim("Baskets ") = Pluralize("Basket"), 1, 0` returns 1.
- The If function supports most functions, including Lookup. It does not support LookupEx,
  TableMatch, and External Data Lookup.

## Examples

- The following example returns 1 if the Type column contains the string Int, otherwise it returns
  the value of the NumCPU column:`=If(Type="Int",1,NumCPU)`
- The following example returns "yes" if Column B equals 100 and Column C equals "hello", or
  Column A is greater than zero. Otherwise it returns
  "no."

  ```
  If(colA > 0 OR colB = 100 AND colC = “hello”,
                “yes”, “no”)
  ```
- The following example looks at the Type field in the Consulting Hours table to determine if the
  hours are billable. If they are, it returns the number of hours entered in the Hours column. If the
  hours are not billable, it returns a zero.

  ```
  =If({Consulting
                Hours.Type}="Billable",{Consulting Hours.Hours},0)
  ```
- The following example performs a simple overtime pay
  calculation:

  ```
  =If(Hours>40,Rate*40+Overtime
                Rate*(Hours-40),Rate*Hours)
  ```
- The following example selects a browser program based on operating
  system:`=If(OS_Type="Windows","Internet Explorer","Firefox")`
- The following example returns 0 when null and 1
  otherwise:`=If(IsDataPresentHere="",0,1)`
- The following example shows a nested If:`=If(a=b,If(c=d,q,p),z)`
- The following example computes absolute value:`=If(x<0,x*(-1),x)`
- The following example would return a value of
  1:

  ```
  =If(Trim("Baskets ") = Pluralize("Basket"), 1, 0
                )
  ```
- The following example would return "true" if a wireless phone number is not one of the specified
  numbers:

  ```
  =IF(Wireless Number NOT IN
                ("202-321-4143","310-697-9064"),"true","false")
  ```
