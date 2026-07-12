---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "If function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/if.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# If function

Evaluates a filter expression and returns one value if true and another value if false.
Supports both AND and OR operations in the condition.

## Syntax

`If(filter_expression, true_expression, false_expression)`

## Arguments

*filter\_expression*: The condition to evaluate. Supports logical operators like AND, OR, and
comparison operators (=, !=, <, >, <=, >=, IN, NOT IN). Note: This parameter accepts
an expression, meaning you can provide a literal value, a column reference, or the result of
another function. Required

*true\_expression*: The value to return if the filter\_expression evaluates to true. Note:
This parameter accepts an expression, meaning you can provide a literal value, a column
reference, or the result of another function. Required

*false\_expression*: The value to return if the filter\_expression evaluates to false. Note:
This parameter accepts an expression, meaning you can provide a literal value, a column
reference, or the result of another function. Required

## Behavior

- Evaluates the given condition (filter\_expression).
- If the condition evaluates to true, returns the result of true\_expression.
- If the condition evaluates to false, returns the result of false\_expression.
- Logical operations like AND and OR are supported, with AND evaluated before OR unless
  overridden by parentheses.
- Supports nesting of If functions within each other for more complex logic.
- Supports most functions within the If statement, but does not support LookupEx,
  TableMatch, or External Data Lookup functions.

## Return type

Depends on the return type of true\_expression or false\_expression (String, Number, or
Date).

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

Note:

- If you find yourself writing a very complex nested If statement, consider using the
  TableMatch function instead.
- Functions can be used within If conditions and results, except for LookupEx,
  TableMatch, and External Data Lookup.
- For blank comparisons, use "" instead of the keyword BLANK.
