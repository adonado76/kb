---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Plan for multiple years"
breadcrumb: []
source_path: "it-planning/planning/plan-multiple-years.html"
images:
  - "resources/planning_images/itp_multi-year-line-items.png"
  - "resources/planning_images/itp_time-period-adjuster.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Plan for multiple years

Use multiple-year planning features to plan and track your IT financials in a continuous,
multi-year time horizon. You can support long-range plans and rolling forecasts across fiscal year
boundaries.

Apptio Planning applications support plans spanning up to six years. A plan spanning multiple
years helps you do the following:

- Better understand the financial impact of projected labor resource, contracts, and assets over
  multiple years (see [Manage
  assets](manage-assets.html)).
- Forecast with up to 12 months (or four full quarters) of actuals to support rolling forecasts
  (see [Budget planning and
  forecasting](budget-planning-forecasting.html)).

## About the time period adjuster

Use the time period adjuster to scope summarized data. It looks like this:

![image](../../../../../03-media/apptio-planning/resources/planning_images/itp_time-period-adjuster.png)

Here's how the time period adjuster works:

- The currently scoped time frame is indicated by the blue-shaded region. To adjust the time
  period, click and drag the left and right handles.
- KPI values on the Summary view are scoped to the time period set using the time period
  adjuster.
- The stacked bar chart for a plan spanning multiple years includes the following additional
  visualization options: actuals trend line, and ability to aggregate data using different time
  periods (like a rolling four quarter forecast).

## Multiple-year features in tables

When working in line-item tables, you can adjust how much of a plan that spans multiple years is
visible. See [Customize, save,
and share table layouts.](customize-save-share.html)

- Adjust the time-scaled data to show or hide months, quarters, or specific fiscal years.
- Show or hide specific fiscal year columns.
- The time-scaled data in the following example is set to show (1) the current quarter's months
  and quarterly total, (2) the current year's remaining quarters, and (3) the out years' fiscal year
  totals.

![image](../../../../../03-media/apptio-planning/resources/planning_images/itp_multi-year-line-items.png)

You can save your line-item table adjustments to a custom table layout. And, Budget Process
Owners and Admins can make a custom layout the default layout for other users. See [Create and share custom table
layouts](customize-save-share.html).

Resource planning values generated for labor, contracts, and assets (see [Labor planning)](labor-planning.html "Use labor planning features to incorporate resource-based costs into your overall budget planning process. Labor costs are always a major component, possibly the largest component, of your IT budgets. Now, you can itemize resource-based costs by labor-specific dimensions such as Type, Location, and Role, using consistent and centrally managed labor costing rules.") can extend throughout
the duration of a plan spanning multiple years. See [Labor planning.](labor-planning.html "Use labor planning features to incorporate resource-based costs into your overall budget planning process. Labor costs are always a major component, possibly the largest component, of your IT budgets. Now, you can itemize resource-based costs by labor-specific dimensions such as Type, Location, and Role, using consistent and centrally managed labor costing rules.") Resource planning can include the following:

- Current or planned labor costs with no end date, or an end date beyond the multi-year plan will
  extend throughout the plan (see [Create a labor plan](create-labor-plan.html)).
- Labor compensation adjustments that apply from the Adjustment Effective Date through the
  duration of the plan (see [Plan for labor compensation adjustments](plan-labor-compensation.html "Budget Process Owners or users with owner permissions for a Cost Object can account for planned adjustments to labor compensation rates. This can be done for current or planned labor. You can specify a percentage change to base compensation per labor resource, and the date at which the change will become effective.")). Labor compensation adjustments are annually
  recurring. For example, a 3% increase effective as of April 1 in the current year would result in a
  3% year-over-year increase.

KPI values in line-item tables are scoped to the current fiscal year only and labeled
accordingly. Line-item KPIs do not adjust based on what fiscal periods are visible or not.

When importing or exporting financials, Apptio Planning applications support up to 72 time
periods. Each time period is labeled P1 through P12, or P1 FYnnnn, where P1 represents the first
period of the fiscal year and nnnn represents the four-digit fiscal year. See [Enter or import line item data](enter-import-line.html "After a budget plan or forecast has been opened, budget owners receive an email notification and can begin to enter line-item data and submit plans. Department Owners, Service Owners, and Project Owners can enter or import their line-item data and submit their plans.") and
[Export and populate line-item
tables or layouts](export-populate-line.html).

When comparing two versions or plans, comparison columns are adjacent to the total columns. See
[Compare versions or
plans](compare-versions-plans.html). Green headers indicate version comparisons while purple headers indicate plan
comparisons.

TIPS:

- When creating a new plan, specify either a 1-year or 6-year plan (see [Create a budget plan or
  forecast](create-budget-plan.html)).
- When creating a new multi-year plan using a single-year plan, the first year data of the
  original plan is copied to the first year data of the new plan, even if the fiscal time periods of
  the original and new plan differ.
- When publishing a multi-year plan to Costing Standard, Apptio Planning applications will publish
  72 months of data in a single publish action (see [Integrate with Cost Transparency](integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio Planning application, you can integrate them to share data.")).
