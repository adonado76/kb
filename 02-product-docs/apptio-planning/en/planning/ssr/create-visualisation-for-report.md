---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Create a visualization for a report"
breadcrumb: []
source_path: "planning/ssr/create-visualisation-for-report.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Create a visualization for a report

Complete the following steps to create a visualization in Apptio BI using data from
Planning. You can customize the visualization in a variety of ways, including selecting the
visualization type (bar chart, line graph, and more), filtering data, and selecting a time
period.

For more information, see [Create
custom reports](../../../apptio_bi/self-service-reporting_user_guide/create-a-self-service-report.html).

## Procedure

1. In Enhanced Access Administration, open Apptio BI.

   If this is your first time opening Apptio BI, you will see an introduction screen

   ![Apptio introduction screen](../../../resources/images/it%20planning_images/pastedimage_22.png)
2. Select Create New Report.
3. Select Add Visualization in the top-right corner.

   The Add Visualization page opens.
4. In the Data Sources and Measures section, select a data source for the
   visualization.

   The following data sources are unique to ITP, and they correspond to different expense tabs.

   To view the data from the Other expense tab, select the Planning Financial data source and filter
   for "Line Item Type" dimension equals "Other" value.

   | Data Source | Associated ITP Expense Tab | Associated ITP Expense Sub-Tab |
   | --- | --- | --- |
   | Planning Asset | Assets | Existing, Planned |
   | Planning Financial Summary | All | Planning |
   | Planning Contract | Contracts | Planning Financial Summary |
   | Planning Labor | Labor | Existing, Planned |
   | Labor Activity | Labor | Existing, Planned |
5. In the Plan Name section, select the plan to use for your visualization.

   All
   active plans in Planning are listed. Archived or deleted plans will not appear.
6. Select the dimensions and metrics you wish to use.

   For more information, see[Overview](it-planning-data-self-service-reporting.html "Apptio BI allows users to build and share their own custom reports using data from a variety of applications, including Planning. With Planning data available in Apptio BI, users can now create a custom report that summarizes Planning department labor, asset, contract, and financial data all together.")
7. Select a visualization type.
8. Select a date range.

   Up to 1 year’s worth of plan can be displayed at a time. Planning visualizations include the
   following options in addition to the standard Apptio BI options:
   - Next Year
   - # Years Future, where # is the number of year in the future for a plan with multiple years, up
     to a maximum of 7 years. For example, if the current year is 2020 and the plan starts in 2020 and
     lasts 7 years, then the date range would include “2 Years Future” to display 2022’s plan, “3 Years
     Future” to display 2023’s plan, …. “7 Years Future” to display 2027’s plan.
   - Note: In ITP Labor data source, only This Month and Last Month options are supported
     for the following visualization types: KPI, Bar, Pie.
9. In View By, select a timeframe.

   In ITP Labor data
   source, only Monthly view by option is supported.
10. Optional: Select a filter.

    In the Planning Labor data source, you can use "Is Existing Resource" dimension to filter to view
    only existing (=true) vs planned (=false) labor sub-tab data.
11. Optional: Edit the name of the visualization.

    As a best practice, add the data source as a prefix to the visualization name.
12. When you’re done, click Save Report.

    After saving your visualization, you will view your report which contains the visualization. Add
    additional visualizations as needed. You can also share the report with other members of your
    organization. For information on sharing, see [Manage
    reports](../../../apptio_bi/self-service-reporting_user_guide/manage-self-service-reports.html).

    Note:

    The Compare To option is not currently supported.

    To display every line item in Apptio BI as it appears in Planning, add a column with a unique
    value to the visualization (ex: the employee name in the Labor data source).

    Labor Amount is not available via the Planning Labor data source. To see the labor amount, select
    Planning Financials as the data source, then filter for the Line Item Type value of Labor.

## Example

The following information is an example of a configuration used to create a table visualization
using Planning Financials as the data source. Note that needed options change based on the
visualization type.![Example of a configuration used to create a table visualization using Planning Financials as the data source](../../../resources/images/it%20planning_images/pastedimage_1.png)
