---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Modify table structure"
breadcrumb: []
source_path: "reports/tables/modify-table-structure.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Modify table structure

Applies to: TBM Studio 12.0 and later

After you add a table to a report, you can make modifications such as sorting the contents,
hiding columns, and freezing columns. Make these modifications by selecting icons from the
Table and Data tabs or right-clicking on a column header to display a pop-up menu.

## Rename a column

To rename a column, right-click the column header and select Rename from the pop-up menu.
Enter a new name for the column.

## Group columns

You can group two or more columns in a table and put a header above the columns. In the following
image, there are two column groups: Information and Costs.

![](../../../resources/images/studio_images/studioimages/reports/rep202.png)

To group columns:

1. Hold down the Ctrl key (Alt key on the Mac) and
   click the header of each column that will be in the group.
2. Right-click and click Group Columns from the pop-up menu.
3. In the Group Columns dialog, enter the header to be placed above the
   columns and click OK. NOTE: You can use dynamic text
   in the header. For information on dynamic text, see [Insert context-dependent text into HTML](../html.htm#contextdependenttext).

To ungroup columns, right-click the column header and select Ungroup Columns from the
pop-up menu.

## Move a column

To move a column, click the column header and drag left or right to a new position in the
table.

## Resize a column

To resize a column, perform one of the following actions:

- Position the mouse pointer over the right boundary of the column. When the pointer icon changes
  from a hand to an arrow, click and drag left or right.
- Right-click the column header, click Formatting, click Set
  Width, and enter the width in pixels.

## Display and hide columns

To hide a column in a table, right-click the column name in the Values area of the
Component Configuration pane and select Hide. The column name is grayed.

To display a hidden column in a table, right-click the column name in the Values area of
the Component Configuration pane and select Show.

## Freeze a column

In large tables, you can freeze one or more columns to prevent them from scrolling horizontally
out of view. When you freeze a column, the column moves to the far-left edge of the table and is
locked in that position. As you scroll the table to the right, the frozen column stays in place. You
can freeze more than one column.

To freeze a column, perform one of the following actions:

- Select the column, and then select the Freeze icon on the
  Data tab.
- Right click the column header, click Formatting, and click **Freeze
  Column**.

To unfreeze a column, right-click the column header, click Formatting, and click
Unfreeze Column.

## Sort rows in a table

You can sort a table by one or more columns. The sort can be in ascending or descending order. To
sort a table, use the Sort controls on the Data tab.

To sort a table by a single column, select the column and click the Ascending or
Descending icon.

To sort a table by multiple columns, click the Sort icon. The application displays a
dialog where you can select up to four columns to use for sorting.

## Zeroes in a table

You can use this filter to remove the zero values from your reports. To use this, navigate to an
editable report Data tab and then select Zeroes.

![](../../../resources/images/studio_images/zeroes.jpg)

Enter the report name, or choose the checkbox of the reports, and click OK. You can also
select All / None to select / deselect all reports .

To remove the zeroes filter applied on the reports, select the reports and click **Revert
All**.

## Hide the Total row

By default, tables display a Total row at the bottom. To hide a Total row, click
the Data tab, click Sum, and clear the Show Total Row option.

The Total row is smart enough to choose the appropriate action for the columns in a table. It
sums only numeric columns. Also, calculated columns display the result of the totals. For example,
assume you have the table shown below:

![](../../../resources/images/studio_images/studioimages/reports/rep330.png)

The Cost per Server column is calculated by dividing the total cost by the number of
servers. The Cost per Server value in the Total row is calculated as well based on 5 servers
with a total cost of $300: $300/5 = $60. The Total row displays a value of $60 instead of $150.

## Display the Totals column

By default, tables do not display a Totals column. To display the column, click Sum
on the Data tab and check the Show Total Column option.

## Display the Other row

If there are many rows in a table, and you want to limit the number of rows displayed, you can
add an Other row. To add the row, click Sum on the Data tab and check the
Show Other Row option. The Other row is displayed at the bottom of the table. It shows the
total for the entire table minus the values displayed on the current page of the table.
