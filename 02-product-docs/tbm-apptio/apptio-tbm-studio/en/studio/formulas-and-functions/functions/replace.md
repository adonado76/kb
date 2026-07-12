---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Replace function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/replace.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Replace function

Replaces values in a table based on mappings from a separate lookup table. The function
matches on key columns and assigns new values from specified columns in the replacement table.
All values are treated as strings.

The Replace function is used to replace values in a column in a transform table with values
from a search and replace table. The function is entered in the **Value Override** field
for a column in a transform table. The replacement values are entered into a
search\_and\_replace table (data set). The entries in the search\_and\_replace table are
executed sequentially working from the top of the table to the bottom. Replacements based on
the first rows in the table can be overwritten by replacements in the latter rows. All
values are treated as strings.

## Syntax

`=Replace((transform_table_column1,transform_table_column2,...),search_and_replace_table,(match_column1,match_column2,...),(new_column1,new_column2,...),replace_table_column)`

## Arguments

*transform\_table\_column1, 2, ...*

The names of the columns in the table that will be used to uniquely identify each row in the
table. The columns with values that will be replaced must be included as well.

*search\_and\_replace table*

The name of the table that will supply the replacement values.

*match\_column1, 2, ...*

The columns in the search\_and\_replace\_table that match the columns in the transform table. They
can have different names, but for each column in the transform table, there must be a matching
column in the search and replace table.

*new\_column1, 2, ...*

The names of the columns in the search\_and\_replace table that will be used to provide the new
values.

*replace\_table\_column*

The column in the search\_and\_replace table that will provide the new value.

## Example

Assume you have the following transform table:

| Dept | Location | ID |
| --- | --- | --- |
| Sales | Seattle | 001 |
| Marketing | Seattle | 002 |
| Research | Chicago | 003 |
| Development | Chicago | 004 |
| Distribution | Denver | 005 |

You want to change the IDs by adding a Ds in front of each ID. To ensure a unique identifier, you
create a new table (data set) called the **Search and Replace Table** (example follows):

| Dept | ID | New\_Dept | New\_ID |
| --- | --- | --- | --- |
| Sales | 001 | Sales | D001 |
| Marketing | 002 | Marketing | D002 |
| Research | 003 | Research | D003 |
| Development | 004 | Development | D004 |
| Distribution | 005 | Distribution | D005 |

Open the transform table in the application and enter the following in the **Value Override**
field for the ID column:

```
=Replace((Dept,ID),Search_and_Replace_Table,(Dept,ID),(New_Dept,
New_ID),New_ID)
```
