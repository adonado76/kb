---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Waterfall Charts"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Charts"
source_path: "studio/new-uc/reference/report-studio-reference/waterfall-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Waterfall Charts

**Applies to:** TBM Studio 12.2 and later

Waterfall charts (also called bridge charts) show the cumulative effect of sequential positive
and negative values on an initial value. They excel at explaining variances, such as how costs
changed from budget to actual or from one period to another.

**Understanding Waterfall Chart Components**

- Base Values: The beginning and ending whole columns (and optionally intermediate period columns
  such as quarters).
- Intermediate Steps: Floating columns between base values showing positive (upward) or negative
  (downward) contributions.
- Unexplained Column: Represents any variance not accounted for by defined intermediate steps.
- Explanation Table: A configurable table below the chart where intermediate steps are defined.

**Creating a Waterfall Chart**

1. On the Report tab, click the Waterfall icon.
2. In the Waterfall Configuration panel, select a model object from the dropdown.
3. From the Metrics section, drag a modeled metric into the Values area (this creates the beginning
   value).
4. Drag a second metric into the Metrics area (this creates the ending value).
5. To change time periods, right-click the time period and click Shift, then enter a positive or
   negative number.

**Adding Intermediate Steps**

Intermediate steps explain the variance between base values. They must be added in the Production
environment:

1. Switch to the Production environment.
2. Open the report with the waterfall chart.
3. Click Add Explanation at the bottom of the intermediate steps table.
4. Enter a label in the Step column, a positive or negative value in the Value column, and a
   description in the Explanation column.
5. Reorder steps by right-clicking and selecting Move Up or Move Down.

Note: Explanations are stored in the IT Planning database. If this database is not installed,
explanations cannot be added.

**Waterfall Chart Options (Waterfall Tab)**

- Show table: Displays the explanation table below the chart. Clearing this hides the table from
  viewers.
- Show detailed rows: Displays intermediate steps associated with specific slicer values at the
  bottom of the step table (read-only).
- Explanation in Tooltips: Shows the Explanation field text when hovering over bars.
- Number: Format numbers displayed in the waterfall chart.
- Colors: Customize colors for increase bars, decrease bars, and total bars.

Important: Waterfall chart values are always displayed in the base currency set for the
project. Multi-currency is not supported for waterfall charts.

**Parent topic:** [Report Components: Charts](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
