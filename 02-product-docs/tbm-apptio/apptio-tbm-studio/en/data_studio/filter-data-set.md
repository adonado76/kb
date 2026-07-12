---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "data_studio"
title: "Filter data"
breadcrumb: []
source_path: "data_studio/filter-data-set.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filter data

Applies to: Apptio TBM Studio R12.0 and later

To filter data, add a filter to the transform steps. You can enter one or more filter expressions
and combine them using AND and OR logic. Also, you can nest filter expressions using parentheses.
You can apply filters to the following:

- Data sets in the transform pipeline
- Model object
- Allocations

Tip: As a best practice, if you use both OR/AND, make sure to use parentheses to
group-related arguments.

![](../../resources/images/studio_images/studioimages/studio/stu500.png)

## Filter rows

To add a filter expression:

1. Add a filter step to the transform pipeline.
2. Construct the first filter expression:
   - From the drop-down menu in the filter step, select the column to be filtered.
   - From the drop-down field in the center, select an operator (Equals,
     Not Equals, and so forth).

     Note: Some row-filter operators work only with certain data types. See [Operators and Data Types with Filters](#Filterdata__Operatorsanddatatypeswithfilters).
   - In the field on the right, enter a filter value (example: Compute).

     ![](../../resources/images/studio_images/studioimages/studio_filter_compute.png)

If you want, add more filter expressions.

To add a simple filter expression (using either OR or AND, not both), complete these steps:

1. Click Add condition, just below the previous filter expression. A new
   expression line is added below the previous one, along with a Boolean selector list (for AND and
   OR).
2. Select AND or OR.
3. Type values for column, operator, and filter for the new expression, then click
   Save.

The filter is applied.

![](../../resources/images/studio_images/studioimages/studio_filter%20data_row.png)

To add a complex filter expression (using both OR and AND), complete these steps:

1. Click the Plus-Parenthesis![](../../resources/images/studio_images/studioimages/icons/paren.png) icon on the right. ![](../../resources/images/studio_images/studioimages/studio_filter_add%20row.png)
2. Selecting the parentheses icon indents an expression from the other arguments.

   ![](../../resources/images/studio_images/studioimages/studio_filter_add%20condition.png)

   Tip: As a best practice, when using both OR/AND, make sure to use parentheses to
   group related arguments. This helps to ensure that user expectations are reflected correctly in the
   filter configuration. Using both OR/AND arguments with no parentheses can result in the system not
   filtering records per user expectations.
3. Click Add condition. A new, indented expression line is added below the
   previous line, which means it is also enclosed in parentheses, along with a Boolean selector list
   (for AND and OR).
4. Select AND or OR.
5. Type values for column, operator, and filter for the new expression, then click
   Save.

More options when adding expressions:

- To add an expression line without sub-nesting, click Add condition at the
  left. Select a Boolean operator, then complete the expression line as before.
- To add an expression line with another layer of sub-nesting, click the
  Plus-Parenthesis icon ![](../../resources/images/studio_images/studioimages/icons/paren.png) at the right. Select a
  Boolean operator, then complete the expression line as before. Users can see when an expression is
  in parentheses because the expression is indented to show how the parentheses are grouping
  expressions.![](../../resources/images/studio_images/studioimages/studio_filter_it%20resource%20tower.png)
- To delete a line, click the Delete icon ![](../../resources/images/studio_images/studioimages/icons/delete_icon.png) at the right of the
  criteria.

## Copy/paste filters

Use the Copy/Paste icons to copy or paste a set of filters from one table to another.

![](../../resources/images/studio_images/studioimages/studio/stu659.png)

## Operators and data types with filters

Some row-filter operators work with certain data types only. For example, Less Than works
with columns that contain numeric data only, while Equals works with columns containing any
data type. The following table describes the data types that work with each row filter operator. The
top group of operators in the table provides functionality similar to wild cards. Filters do not
support traditional wild card symbols, such as \*.

|  |  |
| --- | --- |
| Row filter operator | Data type of column |
| ContainsDoes Not ContainEnds WithDoes Not End WithStarts WithDoes Not Start With | String |
| Less ThanLess Than or Equal ToGreater ThanGreater Than or Equal To | Numeric |
| EqualsNot EqualsIs NullIs Not NullIs InIs Not In | All types |
| Intersects CurrentUser ColumnIntersects Table:Column | String |

## Is In and Is Not In operators

The Is In operator checks to see if a value in one column also exists in **one or
more** other columns in the table. The Is Not In operator checks to see if a value in one
column does not exist in one or more other columns. Unlike the other operators, Is In
and Is Not In can take multiple entries in the right field. Each entry must be separated by a
comma.

![](../../resources/images/studio_images/studioimages/studio_filter_is%20in.png)

For the filter to apply to a row, the filter expression must be true for all the columns
listed.
