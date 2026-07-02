---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Substitute function"
breadcrumb: []
source_path: "formulas-and-functions/functions/substitute.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Substitute function

Applies to: TBM Studio 12.0 and later

Searches a specified target string for the presence of a specified search string. If the search
string is found, it replaces it with a specified replacement string.

## Where to use

This function can be used in:

- Data sets
- Formula columns in report tables
- Dynamic text
- Calculated metrics and reports with metric columns

## Syntax

`Substitute(target_string,search_string,replacement_string)`

## Arguments

*target\_string*

> The string to search in.

*search\_string*

> The string to search for within the *target\_string*.

*replacement\_string*

> The string to replace the *search\_string*.

## Return type

String

## Example

The following example searches all occurrences of virtual server and replaces
virtual with physical.

> ```
> =Substitute("virtual
>           server","virtual","physical")
> ```

The following example searches for single quotes and replaces them with nothing, essentially
removing the single quotes from the string. This can be useful if you are importing data from Excel
and some, but not all, of the entries have a leading single quote.

> ```
> =Substitute(Billing
>     ID,"'","")
> ```
