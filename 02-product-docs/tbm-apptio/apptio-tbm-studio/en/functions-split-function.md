---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Split function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Split function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/split.html"
images:
  - "03-media/apptio-tbm-studio/aug482.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Split function

*Applies to : TBM Studio 12.0 and later*

Returns an element of a delimited string.

## Syntax

Split(string,n[,delimiters])

## Parameters

- string: The string to split and extract an element from. Usually this is a column reference. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required
- n: An integer indicating which element to return. A positive number counts from the left; a negative number counts from the right. Required
- delimiters: Optional. A string of delimiter characters to split the string by. Multiple characters are allowed (e.g., ";>/" uses semicolon, greater-than, and slash). Use a period (.) to represent a space. Defaults to "/-". Optional (default: /-)
- ignoreAdjacentDelimiters: Optional. A boolean (true or false) indicating whether adjacent delimiters should be treated as one. Defaults to true. Optional (default: true)

## Return type

String

## Examples

Assume you have a column in a table that contains the first and last names of employees. For example: John Smith, Tom Jones, Sarah Brown. You want to separate the first name from the last name to produce the following table:

To accomplish this, you would enter the following equations in the Value Override field for the First Name and Last Name columns. The " " delimiter represents the blank space between the first and last name.

| Column | Value Override formula |
| --- | --- |
| First Name | =Split(Name,1," ") |
| Last Name | =Split(Name,2," ") |

Below are other examples for the Split function.

| Example Function | Return Value |
| --- | --- |
| =Split("a/b/c/d",3,"/") | c |
| =Split("a,b,c,d",7,",") | Null |
| =Split("a&b&c&d",4,"&") | d |
| =Split("foo",1) | foo (the entire string) |
| =Split("foo",2) | Null |
| =Split("a/b/c/d",-3) | b |

- Split("Seattle, Tacoma, Spokane", 2, ",") : Returns " Tacoma" — the second item in the comma-separated list.
- Split("Region/US-East", -1) : Returns "East" — the last element split by the default "/-" delimiters.
- Split({City List}, 3, ",;") : Splits values in the {City List} column using comma or semicolon and returns the third element.
