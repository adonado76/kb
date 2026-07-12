---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Analyze a plan or forecast"
breadcrumb: []
source_path: "planning/analyze-plan-forecast.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Analyze a plan or forecast

The Summary page provides chart visualizations of direct and indirect expenses, and (if enabled)
charges incurred by labor headcount data. See [Analyze labor headcount](analyze-labor-headcount.htm "(Opens in a new tab or window)"). These charts can be customized and are
interactive.

![](../../resources/images/it%20planning_images/icon_video.png):

Watch this video from Apptio Education Services: [View Budget
Summary](https://community.apptio.com/videos/1602 "(Opens in a new tab or window)").

Or see all [Apptio planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)").

## Open the Summary page and select a layout

1. In the plan menus at the top right, select a plan, a Cost Object category, and a cost object or
   cost object group.

   [Learn more about
   navigating in Planning](navigate-apptio-planning.htm#Toolbar)

   Note: Cost Center Owners can only edit their assigned Cost Centers.
   See [Manage Cost Object Permissions
   reference data](manage-cost-object.htm "(Opens in a new tab or window)").
2. Select the required view from the navigation menu under Planning.
3. If your view includes tabs, select a tab.

   Optionally, apply a different layout to the page by
   selecting a layout option from the upper right.

   The current plan title and status appear at
   the top of the page. Click Plan Settings to set Summary page options:
4. Use the Filter, All, OpEx, and CapEx options at the top right of the
   page to set display options. See also [Filter line-item tables](filter-line-item.htm "(Opens in a new tab or window)").Note: Filters will apply to all charts, but
   do not apply to the KPIs.

## Tree Map chart

This chart displays a proportional representation of positive values for the Group By selection.
See [Group and view values by data dimensions](#Analyzeaplanorforecast__Groupandviewvaluesbydatadimensions). Click a group (block) to
load the details of that group into the Plan Trend chart.

- The Tree Map can be color-coded, with colors representing a comparison of each group to set
  budget targets, or to another plan or version of a plan (see Analyze a plan or
  forecast and [Set
  financial targets)](set-financial-targets.htm "(Opens in a new tab or window)").
- The legend in the Variance % shows the percentage under target (blue tones) or over target (red
  tones) for each group. If no targets are set, the Tree Map appears gray. The Tree Map will also
  appear gray when comparing the current plan to another plan with no variance present (see [Compare versions or plans](#Analyzeaplanorforecast__Compareversionsorplans)).

![](../../resources/planning_images/itp_summary_treemap.png)

## Plan Trend chart

This chart displays time-phased data for all or a selected group in the Tree Map chart. Click a
group (block) in the Tree Map chart to load the details of that group into the Plan Trend chart.
Click a bar in the Plan Trend chart to see the line-item details or hover over an area on a bar to
display the data for that area.

- Use the Plan Trend Dimension menu at the top of the chart to select a specific
  dimension.
- Click Months, Quarters, or Years to adjust the time period to display.
- Use the Plan Trend chart's adjuster at the bottom of the chart to scope the data summarized in
  the charts.
- If actuals have been imported or populated, click the Actuals label below the chart to
  show or hide a trend line of Actuals (available in the Months view only). To learn more, see
  [Import and publish
  actuals.](import-publish-actuals.htm "(Opens in a new tab or window)")

If Planning does not display data from the comparison plan or actuals, check if there is data for
the comparison plan or actuals in the fiscal periods in question.

![](../../resources/planning_images/itp_summary_plan-trend.png)

## Waterfall Compare chart

This chart only displays when you select a plan, target, or actuals from the Compare To
list. See [Compare versions of plans](#Analyzeaplanorforecast__Compareversionsorplans). The chart shows "puts and takes"
variance by group. See [Group and view values by data dimensions](#Analyzeaplanorforecast__Groupandviewvaluesbydatadimensions).

![](../../resources/planning_images/itp_summary_waterfall-chart.png)

The numbers in the previous image correspond to the following explanations:

- The current plan appears to the left of the chart, and the comparisons appear to the right.
- Click Flip Comparison to change the comparison order and color and reflect the
  appropriate under and over analysis for your charts.
- (1) X-axis - Displays the plan, target, or actuals being compared.
- (2) Gray bars - Represent the budget of the original plan being compared and the item
  that it is being compared to (plan, target, actuals, forecast). Combined, these two bars represent
  the total values. Everything in between these bars represents a positive or a negative change.
- (3) Blue and red bars - In the following example, these indicate that the actuals spent
  are lower than the total budget for the OpEx spend for the given department. The dollar and
  percentage values show the amount remaining in the budget. Note that depending on the variance
  legend setting, the percentage may indicate a negative or a positive value.
- (4) Gray line - In the following example, this indicates that the actuals spent are
  higher than the total budget for the OpEx department spend. The dollar values show the amount over
  budget for the actual. The percentage value is expressed as a negative number. It shows the
  percentage over budget. Hover over the bars to see the total amount in the original plan against
  those selected in the Compare To list.

## Compare versions or plans

You can use features on the Summary page to compare the financial data of one version of a
budget or forecast plan to another version of the same plan, or to compare one plan to another plan.
You can also compare a plan against target, if [targets have been set](set-financial-targets.htm "(Opens in a new tab or window)"). If your organization uses [Labor Planning](labor-planning.htm "(Opens in a new tab or window)"), Service Demand
Planning, or Project Financial Planning, you can also compare data between plans or versions. See
[Compare versions or
plans](compare-versions-plans.htm "(Opens in a new tab or window)") for more information.

## Group and view values by data dimensions

Use the Group By list to group chart data by a primary data attribute and dimensions. See
[Manage reference data](manage-reference-data.html "(Opens in a new tab or window)").
Grouping does not change the total financial (or labor headcount) values.

Tip: If [Service
Demand Planning is enabled](edit-company-profile.htm "(Opens in a new tab or window)"), you can view services that providers are consuming by grouping by
provider on the Business Unit, Summary page.

![](../../resources/planning_images/itp_sdc_summary_financial.png)

## Adjust the time period

Use the time period adjuster to scope summarized data:

![](../../resources/planning_images/itp_time-period-adjuster.png)

- The currently scoped time frame is indicated by the blue-shaded region. To adjust the time
  period, click and drag the left and right handles.
- KPI values on the Summary page are scoped to the time period set using the time period
  adjuster.
- The stacked bar chart for a plan spanning multiple years includes the following additional
  visualization options: actuals trend line and ability to aggregate data using different time periods
  (like a rolling four-quarter forecast).

## View delegated project costs

If Project Financial Planning Project Financial Planningis enabled, Project Owners can delegate
project costs to department and service owners. All of these owners can show or hide delegated costs
from their financials. See [Delegate project costs](pfp/delegate-project-costs.htm "(Opens in a new tab or window)").
