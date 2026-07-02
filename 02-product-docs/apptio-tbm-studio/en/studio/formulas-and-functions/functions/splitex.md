---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "SplitEx function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/splitex.html"
images:
  - "resources/images/studio_images/studioimages/studio_splitex-function_separate-row.png"
  - "resources/images/studio_images/studioimages/studio_splitex_formulas.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# SplitEx function

Splits a string in a column into multiple rows based on one or more delimiter characters.
Each segment of the split becomes a separate row in the transformed dataset.. If a column in
your data contains multiple values separated by a character such as a comma, and you want to
generate a separate row for each value, use the SplitEx function. For example, assume you have
the table shown below:

![split ex f sample](../../../resources/images/studio_images/studioimages/studio_splitex_state%20and%20city.png)

You want to generate a separate row for each
city as shown below:

![split ex f sample](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_splitex-function_separate-row.png)

Enter the formula shown below for the
**City** column:

![](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio_splitex_formulas.png)

![split ex f sample]()

## Syntax

`Split(column,delimiter)`

## Parameters

*column*: The column in a table to be split.

*delimiter*: One or more characters used to split the string. Delimiters must be enclosed in
double quotes. For example, ";>/" uses semicolon, greater-than, and slash as delimiters.
Required

## Return type

String

## Examples

`SplitEx(City, ",")`: Splits the {City} column on commas. For example:

**Input:**

| State | City |
| --- | --- |
| Washington | Seattle, Tacoma, Spokane |
| California | Los Angeles, San Francisco, San Diego |

**Output:**

| State | City |
| --- | --- |
| Washington | Seattle |
| Washington | Tacoma |
| Washington | Spokane |
| California | Los Angeles |
| California | San Francisco |
| California | San Diego |

`SplitEx(Items, ";>/")`: Splits the {Items} column using semicolon,
greater-than, or slash as delimiters.
