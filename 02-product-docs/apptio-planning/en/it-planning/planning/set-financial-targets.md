---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Set Targets"
breadcrumb:
  - "Planning"
  - "Working with Plans"
source_path: "it-planning/planning/set-financial-targets.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Set Targets

You can set financial **targets** in Apptio Planning to define spending goals or
limits for **OpEx**, **CapEx**, and **Headcount** at the **department level**.
Targets establish top-down financial expectations that can be compared against bottom-up plan
data throughout planning and forecasting cycles.

Targets provide a way to align plan submissions with organizational financial goals. They can
be used to:

- Communicate budget ceilings or funding limits to departments and cost centers.
- Compare planned versus targeted spend for specific categories (such as OpEx, CapEx, or
  Labor).
- Support iterative planning cycles by showing where adjustments are needed before
  submission or approval.

Targets are typically established by Finance or IT Planning leaders early in the budgeting
cycle and distributed to planners for reference within their planning views.

## Who Can Set Targets

- **Admins** or **Budget Process Owners** can set targets for any **department**
  or **group department** within the plan.
- **Group Cost Center Owners** can set targets for their **subordinate
  departments**, allowing for distributed ownership and accountability.

This structure ensures flexibility in how targets are managed across the
organization—either centrally or at different levels of the departmental hierarchy.

## Setting Targets

1. Navigate to the **Targets** page from the left navigation menu.
2. Select the **Target Type** — **OpEx**, **CapEx**, or **Labor**.
3. In the table, enter the target amount for **All Departments**, then allocate it down
   to lower-level departments using the **Department** dropdown.
4. Alternatively, you can begin by entering targets at the **leaf department** level and
   allocate totals upward.
5. The **Remainder** row displays any remaining unassigned amount.

Note: Targets can only be defined for the first year of the plan.

## Viewing and Comparing Targets

Once targets are established, they appear in several areas of the plan:

- **KPI Comparisons:** Display **Plan vs. Target** and **Variance** metrics,
  allowing you to quickly assess how current plans align with defined targets.
- **Summary Page:** Compare plan data to targets using the **treemap** and
  **waterfall** charts, which use color coding to indicate whether variances are
  positive or negative.

To view comparisons to targets on the Summary page, ensure the following:

- **Group By:** Department
- **Compare To:** Targets
- **Date Range:** Set to the first year of the plan
- **View:**OpEx, CapEx, or Headcount
