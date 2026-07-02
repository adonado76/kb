---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "formulas-and-functions"
title: "Use_Map_Table function"
breadcrumb: []
source_path: "formulas-and-functions/functions/usemaptable.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Use_Map_Table function

Applies to: TBM Studio 12.0 and later

Use this function to create allocations between two objects using a manually-entered formula.

Note: Support for this function has been deprecated in TBM Studio version 12. While this function is
still available, leveraging it for net-new allocations is not supported. If you are working with a
project that was upgraded from version 11 (that uses this function), see [Task to follow in v12](#UseMapTablefunction__TasksforStudio12) below which describes the best practice v12
to achieve the same allocations. Apportion encourages customers who upgrade to TBM Studio v12 to
switch to this new method. Additional information on this function is provided below for historical
purposes.

## Where to use

When defining an allocation between two objects in a model, select Advanced as the
Allocation option. The application displays the Edit Formula dialog where you can enter the
function. The advantage of using the Use\_Map\_Table function is that it does not rely on the
inference engine to link the unit identifiers of the two objects. Identifiers in the source object
can be mapped to identifiers in the target object.

## Syntax

> `Use_Map_Table(table:weight_column[,source_column,target_column][,format)]`

or

> `Use_Map_Table(table:weight_column[,format)]`

## Arguments

*table*

> References a mapping table.

*weight\_column*

> The column in the table containing the weighting numbers.

*source\_column*

> The column in the table containing the unit ID of the source object.

*target\_column*

> The column in the table containing the unit ID of the target object.

*format*

> When using the first syntax statement (table:weight), this can be "ratio," "percent," or
> "fraction\_percent," where the default is "fraction\_percent."
>
> When using the second syntax statement (table:weight), this can be "percent" or
> "fraction\_percent," where the default is "fraction\_percent."

## Return type

The type of the columns in the matching table.

## Remarks

For the first syntax, if Object A is rolling values up to Object B, the mapping table must
include the following types of columns:

| A | B | weight\_column |
| --- | --- | --- |
| Values from A'sidentifier column | Values from B'sidentifier column | Numeric percentage (for example: 0.2 = 20%, 1.0 = 100%) |

## Tasks for Studio 12

If your project was upgraded from TBM Studio version 11 to version 12, any allocations using
use\_map\_table will function after upgrading. However, if you edit the allocation, you must alter the
allocation to function in version 12. To do this, you will convert the use\_map\_table into a modeled
object. Then, you will allocate from the original source object into the new mapping object, and
then from the new mapping object, to the original target object.

In TBM Studio version 12, follow these steps:

1. Add a modeling step to the mapping table originally used in the use\_map\_table function.
2. Allocate from the original source object into the newly-modeled mapping table.
   - On this allocation, be sure to specify a data relationship using the source object's identifier,
     and the mapping table's source\_column column.
   - Update this allocation to weight appropriately by the mapping table's weight\_column column. How
     you do this will depend on the format of your use\_map\_table function.
     - If your use\_map\_table format is ratio, then use weighting as your distribution
       rule, and specify the source\_column in the mapping table.
     - If your use\_map\_table format is percent, then create an advanced allocation with the
       formula:

       ```
       =SOURCE*Mapping
                               Table.weight_column/100
       ```
     - If your use\_map\_table format is fraction\_percent, then create an advanced allocation with the
       formula:`=SOURCE*Mapping Table.weight_column`

       **Example: Allocation from Source to
       Mapping Table**

       ![](../../../resources/images/studio_images/studioimages/studio_mapping%20table_distributing.png)
3. Allocate from the newly modeled mapping table into the original target object.
   - On this allocation, be sure to specify a data relationship using the source object's identifier,
     and the mapping table's source\_column column.
   - Typically, the weighting on this allocation will not matter since each row in the mapping table
     allocates to one row in the receiving object.

## Summary

The end result of this method is the same as the original use\_map\_table function, follows TBM
Studio version 12 best practices, and allows the Apptio modeling engine optimizations to have their
full effect.
