---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Split function"
breadcrumb: []
source_path: "formulas-and-functions/functions/split.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Split function

Applies to: TBM Studio 12.0 and later

Returns an element of a delimited string.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables
- Dynamic text
- Calculated metrics and reports with metric columns

## Syntax

`Split(string,n[,delimiters])`

## Arguments

*string*

> The string to be searched to see if it contains the element. Usually, this will be a column in a
> table.

*n*

> An integer indicating the number of the element in the string to be returned. For example, 4
> returns the fourth element in the string. If *n* is larger than the number of elements in the
> string, Split returns null. If a negative number is entered, the count is from right to left.

*delimiters*

> A character or characters that will be used as the delimiter(s) in the *string*. You can
> enter multiple delimiter characters. For example: ";>/" represents three delimiters: semicolon,
> greater than, and forward slash. The delimiter(s) must be enclosed in quotes. To represent a blank,
> use " ." If this argument is not specified, it defaults to /- (slash and hyphen).

## Return type

String

## Examples

Assume you have a column in a table that contains the first and last names of employees. For
example: John Smith, Tom Jones, Sarah Brown. You want to separate the first name from the last name
to produce the following table:

![](../../../resources/images/studio_images/studioimages/studio/aug482.png)

To accomplish this, you would enter the following equations in the Value Override field
for the First Name and Last Name columns. The " " delimiter represents the blank space between the
first and last name.

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
