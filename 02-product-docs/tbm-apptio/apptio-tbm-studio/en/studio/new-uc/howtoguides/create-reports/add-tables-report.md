---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Add Tables to Reports"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Basics"
source_path: "studio/new-uc/howtoguides/create-reports/add-tables-report.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Add Tables to Reports

**Objective:** Add a data table to display model data in a structured, row-and-column
format

**When to use:** When you need to show detailed data, enable drill-down analysis, or
present information that users will want to sort, filter, or export

**Time estimate:** 10–15 minutes

## Understanding the Component Configuration Panel

When you add a table, the Component Configuration panel appears. This panel has four areas
where you drag fields to build your table:

|  |  |  |
| --- | --- | --- |
| **Area** | **Purpose** | **What to Drag Here** |
| **Rows** | Defines the first column entries | Dimension fields (labels, categories) |
| **Columns** | Provides column headers | Time periods or a single dimension |
| **Values** | Displays the data in table cells | Metrics (Cost, Budget, Count) |
| **Filters** | Limits which data appears | Any field to restrict results |

**Steps**

1. Open your report and **check it out** if you haven't already.
2. Click the **Report** tab, then click **Table**. A placeholder table appears in the
   report, and the Ad Hoc Component Configuration panel opens.
3. At the top of the Configuration panel, select a **model object** from the dropdown
   list. This determines which tables and metrics are available.
4. In the **Project Explorer** (left panel), expand the **Tables** section to find
   dimension fields.
5. Drag a dimension field into the **Rows** area. For example, drag "Data Center" to
   create a table that shows one row per data center.
6. Expand the **Metrics** section in the Project Explorer.
7. Drag one or more metrics into the **Values** area. For example, drag "Cost" and
   "Budget" to show both values for each row.
8. (Optional) Add time-based columns by expanding the **Time** section and dragging a time
   field into the **Columns** area.
9. (Optional) Apply filters by dragging any field into the **Filters** area and
   right-clicking to select **Edit Filter**.

## Example: Building a Simple Cost Table

To build a table showing Cost and YTD Cost by Data Center:

- Select **Data Centers** as the model object
- From Tables > Data Centers Info, drag **Data Center** to **Rows**
- From Metrics, drag **Cost** to **Values**
- From Metrics, drag **YTD Cost** to **Values**

## Expected Results

- The table populates with data from your model
- Columns appear for each metric you added
- Rows appear for each unique value in your Rows field
- A Total row appears at the bottom by default

## Common Pitfalls

- **Too much data:** Tables with thousands of rows become slow and hard to use. Apply
  filters or consider using charts for high-level views.
- **Wrong model object:** If you don't see the fields you need, check that you selected
  the correct model object at the top of the Configuration panel.
- **Forgetting to update:** If you clear the Update Results Immediately option, click
  Update after making changes to see your data.

**Parent topic:** [Report Basics](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
