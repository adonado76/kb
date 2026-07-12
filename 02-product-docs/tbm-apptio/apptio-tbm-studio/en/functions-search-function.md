---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Search function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Search function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/search.html"
images:
  - "03-media/apptio-tbm-studio/studio_search_string.png"
  - "03-media/apptio-tbm-studio/studio_diagram_search.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Search function

Searches for a specified string ( search_string ) within another string ( in_string ) and returns a value representing the position in the in_string , counting from left to right, of the first character of the search_string .

Optionally, you can specify a starting_position for the search. The starting_position is an integer value representing the position in the in_string , counting from left to right, to start searching. The search is performed from left to right.

Search returns a value if it finds the search_string embedded within the in_string . For example, it will find pie in spies. If no match is found, it returns 0.

Search does not support wild card characters.

Search is not case sensitive.

## Syntax

Search(search_string, in_string, starting_position)

## Arguments

search_string : The substring to search for. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

in_string : The string to search in. You may also provide the name of a column. Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Required

starting_position : The position to start searching from (1-based index). Note: This parameter accepts an expression, meaning you can provide a literal value, a column reference, or the result of another function. Optional (default: 1)

## Return type

Number

## Examples

- The following example returns 7, which is the position of the letter " F" in the first instance of the search_string . =Search("Functional", "58762 Functional Actuals")
- The following example returns 19, which is the position of the letter "c" in the first instance of the search_string after the 12-character offset is taken. =Search("c", "58762 Functional Actuals", 12)
- The following example returns 0, because the search_string "99" is not found in the in_string . =Search("99", "58762 Functional Actuals")
- The following example uses nested Search functions within a LEFT function to capture the first two octets of an IP address. =LEFT(IP, Search(."",IP,Search(."",IP)+1)) Because IP octets can contain from 1 to 3 digits, the count argument of the LEFT function must be a pair of nested Search functions that find the second dot ( . ) of each IP address.

The inner search is performed first. It finds the location of the first dot, and with 1 added it gives a starting_position argument for the outer search that causes it to begin on the character after the first dot. The outer search returns the position of the second dot, which gives the LEFT function an accurate count argument for capturing the first two octets of the address.

For example, if the column IP contains a value of 10.10.1.113, the inner search returns a value of 3, to which 1 is added, returning 4. The return value 4 is the starting_position for the outer search, which returns 6. The return value 6 is the count for the LEFT function, which returns 10.10.

This example is a good way to find a portion of an IP address, but when searching for complete IP addresses, use the IPLOOKUP function.
