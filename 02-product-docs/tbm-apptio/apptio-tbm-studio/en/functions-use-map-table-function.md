---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Use_Map_Table function"
breadcrumb:
  - "Reference"
  - "Formulas and functions"
  - "Use_Map_Table function"
source_path: "SSWRJM/studio/formulas-and-functions/functions/usemaptable.html"
images:
  - "03-media/apptio-tbm-studio/studio_mapping%20table_distributing.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Use_Map_Table function

*Applies to : TBM Studio 12.0 and later*

Use this function to create allocations between two objects using a manually-entered formula.

## Where to use

When defining an allocation between two objects in a model, select Advanced as the Allocation option. The application displays the Edit Formula dialog where you can enter the function. The advantage of using the Use_Map_Table function is that it does not rely on the inference engine to link the unit identifiers of the two objects. Identifiers in the source object can be mapped to identifiers in the target object.

## Syntax

Use_Map_Table(table:weight_column[,source_column,target_column][,format)]

or

Use_Map_Table(table:weight_column[,format)]

## Arguments

table

References a mapping table.

weight_column

The column in the table containing the weighting numbers.

source_column

The column in the table containing the unit ID of the source object.

target_column

The column in the table containing the unit ID of the target object.

format

When using the first syntax statement (table:weight), this can be "ratio," "percent," or "fraction_percent," where the default is "fraction_percent."

When using the second syntax statement (table:weight), this can be "percent" or "fraction_percent," where the default is "fraction_percent."

## Return type

The type of the columns in the matching table.

## Remarks

For the first syntax, if Object A is rolling values up to Object B, the mapping table must include the following types of columns:

| A | B | weight_column |
| --- | --- | --- |
| Values from A'sidentifier column | Values from B'sidentifier column | Numeric percentage (for example: 0.2 = 20%, 1.0 = 100%) |

## Tasks for Studio 12

If your project was upgraded from TBM Studio version 11 to version 12, any allocations using use_map_table will function after upgrading. However, if you edit the allocation, you must alter the allocation to function in version 12. To do this, you will convert the use_map_table into a modeled object. Then, you will allocate from the original source object into the new mapping object, and then from the new mapping object, to the original target object.

1. Add a modeling step to the mapping table originally used in the use_map_table function.
1. Allocate from the original source object into the newly-modeled mapping table. On this allocation, be sure to specify a data relationship using the source object's identifier, and the mapping table's source_column column. Update this allocation to weight appropriately by the mapping table's weight_column column. How you do this will depend on the format of your use_map_table function. If your use_map_table format is ratio , then use weighting as your distribution rule, and specify the source_column in the mapping table. If your use_map_table format is percent, then create an advanced allocation with the formula: =SOURCE*Mapping Table.weight_column/100 If your use_map_table format is fraction_percent, then create an advanced allocation with the formula: =SOURCE*Mapping Table.weight_column Example: Allocation from Source to Mapping Table
1. Allocate from the newly modeled mapping table into the original target object. On this allocation, be sure to specify a data relationship using the source object's identifier, and the mapping table's source_column column. Typically, the weighting on this allocation will not matter since each row in the mapping table allocates to one row in the receiving object.

## Summary

The end result of this method is the same as the original use_map_table function, follows TBM Studio version 12 best practices, and allows the Apptio modeling engine optimizations to have their full effect.
