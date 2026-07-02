---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Filter line-item tables"
breadcrumb: []
source_path: "planning/filter-line-item.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Filter line-item tables

Apply a filter to the dimension or attributes columns on any line item table view.

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.htm#Toolbar)

   To view all cost objects, skip the last part of this
   step.
2. Select a view from the navigation menu under Planning.
3. If the view you selected includes tabs or sub-tabs, select the tabs you want.
4. At the upper right of the page, click Set Filters.
5. Select your filter options.

Note:

- The Set Filters button changes when a filter is applied.
- To exclude certain dimensions, select Exclude Selected.Use the
  Search values to filter option to display fewer than 200 filter options.
- The Select All and Select None options do not
  affect blank values.
- Click Update Filters.

Tip:

- Click Edit Filters to modify or remove your filters
- To refine filtering by expense type, click OpEx or CapEx at the upper right of the
  Summary or Ledger page

## KPI Filtering

By default, applying filter options does not affect the KPIs. Selecting the Apply Filters to
KPIs will allow KPIs to update with changes in filters.

## Apply Filters to KPIs

1. Navigate to the Expense view.
2. Select the gear icon next to the plan picker.
3. Enable Apply Filters to KPIs.

   ![](../../resources/images/it%20planning_images/kpi-filter.png)

   Note: This option is
   not available on other views such as the Summary view.

## Additional notes about Filters

- Filters are used to find the specific details or row(s) in the table.
- It is available on all Expenses and Summary pages. The summary page can be
  filtered to view specific information on the graphs.
- On clicking the Filters, all the available column names or Dimensions are shown as selectable
  labels in pane to choose on what Dimension(s) the filter is to be applied.
- On the filter pane - if the user clicks on a specific Dimension, all the available Dimension
  values in the table are shown as checkboxes to be able to choose specific value from that Dimension.
  For example, if the user clicks Dimension Location then all the values of location on the table are
  shown as a checkbox list. And, if a specific location checkbox is chosen, only the rows that matches
  the Location selected are shown. It is also possible to select the Dimension that has blank or no
  value using Blank value option.Multi-filtering is possible across different Dimensions.
- Filters also allows to exclude rows that may not be of interest. For example, if you do not want
  to view the Expenses for Location "Seattle", then choose "Seattle" from the Location Dimension and
  click Exclude Selected radio button.
- It is also possible to exclude multiple values at once - select multiple options from different
  Dimensions and click Exclude selected option on each Dimension.
- User can apply filtering combination of including certain Dimension values and excluding others
  at once.
- Select all the Dimension values by using Select All button.
- Remove all the Dimension values already selected by clicking the Select None button.
- The Remove Filter removes all the filter(s) applied on a Dimension selected. It
  de-selects the values that are already selected and defaults to Include selected.Remove
  All Filters removes all the filters applied across the Dimensions.
- If the filters applied on different combination of Dimensions does not yield results then "No
  Result shown. Some line items may be hidden" appears. The user can Edit filters, or remove
  all the filters applied by clicking the Remove All Filters button under the error
  message.
- A filter icon is shown on the table column header to let the user know filter is applied on that
  column(s).The number of Dimensions the filter is applied on is shown as numeric digit on the
  Filter button.
- To share the filtered results, select Actions > and then Export. Ensure to select
  Export Layout Only to get the .csv file that can be shared across.
- To view the KPI for filtered rows, select Settings gear icon next to the plan name and
  enable the Apply Filters to KPI option.
