---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Compare versions or plans"
breadcrumb: []
source_path: "planning/compare-versions-plans.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Compare versions or plans

You can compare the financial data of one version of a budget or forecast plan to another version
of the same plan, or compare one plan to another plan. On the Summary page, you can also compare a
plan against target if targets have been set. See [Set financial targets](set-financial-targets.htm "(Opens in a new tab or window)") for more information. If your
organization practices [Labor
Planning](labor-planning.htm "(Opens in a new tab or window)"), Service Demand Planning, or Project Financial Planning, you can also compare data
between plans or versions.

## Comparison Alignment Method

Comparing plans supports two alignment methods mentioned below. Users need to select one of the
alignment methods when comparing plans using Add Comparison from the Expenses table or Comparison
Shortcuts.

- Plan Start Year - two plans are compared by aligning the starting year of both plans.

  For
  example, if Plan A is a two-year plan with fiscal years 2019 and 2020, and Plan B is a two-year plan
  with fiscal years 2020 and 2021, then this comparison method will compare fiscal year 2019 of Plan A
  to fiscal year 2020 of Plan B.
- Matching Fiscal Year - two plans are compared by aligning matching fiscal years between two
  plans.

  For example, if Plan A is a two-year plan with fiscal years 2019 and 2020, and Plan B is a
  two-year plan with fiscal years 2020 and 2021, then this comparison method will compare fiscal year
  2020 of Plan A to fiscal year 2020 of Plan B.

## Set up comparison shortcuts

Comparison shortcuts can set a *compare* shortcut from their current plan to up to four
other plans. In addition, the admin can also choose to show the comparison plan by default. The
comparison plan the admin chooses is the default for all users of the application. All users can
toggle the comparisons on or off in the COMPARE TO menu.

1. From the ![](../../resources/images/icons/icon-options_23x20.png) options, select
   Compare Shortcuts.

   [Learn
   more about navigating in IT Planning](navigate-apptio-planning.htm#Toolbar)
2. In the Manage Compare Shortcuts window, set up your comparison options.

   ![](../../resources/planning_images/compare%20version%20plans/manage-compare-window.png)
3. Select OK.

Note: Only users with the ManagePlan permission, for example Admin or Budget Process Owner,
can access the Manage Compare Shortcuts menu.

Comparisons shortcuts are applied only to quarters
and years.

Comparison shortcuts for Multi-year plans greater than 4+ years are not
supported.

## Compare versions or plans in a table

Once you set up your comparison shortcuts, then from the left navigation, select Planning,
and then select Expenses. The Compare to option appears with the new shortcuts you
created:

![](../../resources/planning_images/compare%20version%20plans/compare-to-options-2.png)

Note: The YTD FY columns are available only on the Forecast plans. So the YTD comparison will also
be available only on the forecast plans.

The YTD FY column comparisons will now be available in the comparisons saved in the Comparison
Shortcut.

- Variance (Var): This is the time-scaled financial value from the active plan (or version)
  minus the same time-scaled financial value from the comparison plan (or version). The chronological
  order of the compared plans is not a factor in the delta calculation.
- Variance percentage (Var %): This is the time-scaled financial value from the active plan
  (or version) divided by the same time-scaled financial value from the comparison plan (or version)
  presented as a percentage.

Note:

- When working with a plan spanning multiple years, version headings are displayed with a green
  background, and plans with a purple background (see [Plan for multiple years](plan-multiple-years.htm "(Opens in a new tab or window)")).
- Comparisons are not supported on the Contracts or Assets line item tables.
- If a plan comparison is present, a layout must contain at least one grouped column. If none is
  specified, the default grouping is Cost Object and Account.

If your organization does labor planning in Apptio planning applications, click Headcount
to see labor comparisons. See [Labor
planning](labor-planning.htm "(Opens in a new tab or window)"). The Headcount tab is available for Departments only.

## Compare versions or plans on the Summary page

1. From the left navigation menu, select Planning, and then select a Expenses.
2. From the Summary tab, select Compare to.
3. Select the plan you want to compare to.

## Expand or collapse quarter or year columns

To simplify plan comparisons, you can expand data or collapse the data to show quarterly and
annual totals only.

![](../../resources/planning_images/compare%20version%20plans/collapse-and-expand.png)

## View the Year-to-date comparison

View the year-to-date (YTD) column that represents the year-to-date sum of the actuals in your
forecast by adding the YTD column to the table. See [Customize, save, and share table layouts](customize-save-share.htm "(Opens in a new tab or window)") for more information.
The YTD FY column comparisons are also available in the plan comparisons created using the
Comparison Shortcut. So the users no more need to manually click the Add Comparison option from the
YTD column, the comparison will be available in the comparisons saved in the Comparison
Shortcut.

## Plan comparison limits

You can do comparisons on a per period, per quarter, or per annum basis. There is a limit to the
number of comparisons you can do in a single plan.

For example:

- A 1-year plan with 12 periods, 4 quarters, and 1 annual comparison is a total of 17
  comparisons.
- A 5-year plan with 4 quarters and 5 annuals comparisons is a total of 9 comparisons.

The following table shows the maximum number of comparisons supported for each plan length:

| Plan Length | Maximum Comparisons |
| --- | --- |
| 1 | 22 |
| 2 | 19 |
| 3 | 15 |
| 4 | 11 |
| 5 | 9 |
| 6 | 7 |
