---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Search function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/search.html"
images:
  - "resources/images/studio_images/studioimages/studio_diagram_search.png"
  - "resources/images/studio_images/studioimages/studio_search_string.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Search function

Searches for a specified string (*search\_string*) within another string (*in\_string*)
and returns a value representing the position in the *in\_string*, counting from left to right,
of the first character of the *search\_string*.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_search_string.png)

Optionally, you can specify a *starting\_position* for the search. The
*starting\_position* is an integer value representing the position in the *in\_string*,
counting from left to right, to start searching. The search is performed from left to right.

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_diagram_search.png)

Search returns a value if it finds the *search\_string* embedded within the *in\_string*.
For example, it will find pie in spies. If no match is found, it returns 0.

Search does not support wild card characters.

Search is not case sensitive.

## Syntax

`Search(search_string, in_string, starting_position)`

## Arguments

*search\_string*: The substring to search for. Note: This parameter accepts an expression,
meaning you can provide a literal value, a column reference, or the result of another
function. Required

*in\_string*: The string to search in. You may also provide the name of a column. Note: This
parameter accepts an expression, meaning you can provide a literal value, a column
reference, or the result of another function. Required

*starting\_position*: The position to start searching from (1-based index). Note: This
parameter accepts an expression, meaning you can provide a literal value, a column
reference, or the result of another function. Optional (default: 1)

## Return type

Number

## Examples

- The following example returns 7, which is the position of the letter " F" in the first instance
  of the *search\_string*.`=Search("Functional", "58762 Functional
  Actuals")`
- The following example returns 19, which is the position of the letter "c" in the first instance
  of the *search\_string* after the 12-character offset is
  taken.`=Search("c", "58762 Functional Actuals",
  12)`
- The following example returns 0, because the *search\_string* "99" is not found in the
  *in\_string*.`=Search("99", "58762 Functional
  Actuals")`
- The following example uses nested Search functions within a LEFT function to capture the first
  two octets of an IP address.`=LEFT(IP, Search(."",IP,Search(."",IP)+1))`Because IP octets can contain from 1 to 3 digits, the count argument of the LEFT
  function must be a pair of nested Search functions that find the second dot ( . ) of each IP
  address.

The inner search is performed first. It finds the location of the first dot, and with 1 added it
gives a *starting\_position* argument for the outer search that causes it to begin on the
character after the first dot. The outer search returns the position of the second dot, which gives
the LEFT function an accurate *count* argument for capturing the first two octets of the
address.

For example, if the column IP contains a value of 10.10.1.113, the inner search returns a value
of 3, to which 1 is added, returning 4. The return value 4 is the *starting\_position* for the
outer search, which returns 6. The return value 6 is the *count* for the LEFT function, which
returns 10.10.

This example is a good way to find a portion of an IP address, but when searching for complete IP
addresses, use the [IPLOOKUP](iplookup.htm "(Opens in a new tab or window)")
function.

Note: The Search function is case-insensitive. If you need a case-sensitive search, use the
Find function instead. All parameters accept expressions (e.g., literals, columns, or nested
functions).
