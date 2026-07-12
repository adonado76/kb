---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "String concatenation"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "String concatenation"
source_path: "SSWRJM/studio/formulas-and-functions/string-concatenation.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# String concatenation

*Applies to : TBM Studio 12.0 and later*

To format values for metrics, you can specify a string in an expression.

The following example puts a dollar sign ( $ ) in front of the value in the Cost column. If Cost is 200, this expression evaluates to $200.

="$"+Cost

The above example could also be written with an ampersand ( & ) as the concatenation operator, as shown in the following example.

="$"&Cost

The following example puts the value in the Ticket Description column before the value of the Ticket Number column, which is in parentheses. If Ticket

Description is Hardware and Ticket Number is 10065, this expression evaluates to Hardware(10065).

```
=Ticket
            Description&"("&Ticket Number&")"
```

## Using hyphens

When concatenating text, you can represent hyphens with a double ampersand (&&). Often this is used to create unique keys for general ledger entries. If an item to be concatenated is blank then it won’t include it in the concatenation.

For example, if you enter this string:

string1&&string2&&string3

It will translate as:

string1 - string3

Note that the && puts a space before and after the hyphen.

## Example

Case 1: A space is added in between 2 &&’s

="A"&&" "&&"B" will translate as A - - B

Case 2: Null or “” is added in between 2 &&’s

="A"&&""&&"B" will translate as A – B

Case 3: No “” is added between 2 &&’s will result in error

="A"&&&&"B" will translate as an ERROR
