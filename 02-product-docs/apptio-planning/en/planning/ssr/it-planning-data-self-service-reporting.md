---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Apptio BI overview"
breadcrumb: []
source_path: "planning/ssr/it-planning-data-self-service-reporting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Apptio BI overview

Apptio BI allows users to build and share their own custom reports using data from a
variety of applications, including Planning. With Planning data available in Apptio BI, users can
now create a custom report that summarizes Planning department labor, asset, contract, and financial
data all together.

To learn more about Apptio BI, see [Apptio BI](../../../apptio_bi/home.html).

Note:

Although multi-currency functionality is supported, Apptio BI is currently only available in
English.

## Prerequisites

An administrator must grant you permission to access Apptio BI. If you do not have access, see
[Apptio BI](../../../apptio_bi/home.html). The following Enhanced Access
AdministrationRoles were given view access to Apptio BI:

- Admin
- Cost Center Owner
- Budget Process Owner

Data shown in Apptio BI adheres to the same view permissions configured in Planning.

If Planning data sources do not appear in Apptio BI, work with your Customer Service Manager to
register Planning as a data source to Apptio BI. See here: How to Register Planning as a Data Source
to Apptio BI.

## Available data

Expense data from all active plans in Planning is available for use in Apptio BI. To view a list
of active plans, select Plans from the Planning menu (see [Find your way around Planning](../navigate-apptio-planning.html)). To
review the data that will be available for a given plan, select a department, then select Expenses
from the View menu. Data on the Summary, Labor, Contracts, and Assets tabs will be available for
reporting. Data from the Summary tab is available by selecting ITP Financials as a data source.

When creating a visualization in Apptio BI, you are prompted to select specific dimensions and
metrics of your data to include. Note that dimensions in Apptio BI are distinct from the “[reference data dimensions](../navigate-apptio-planning.html)” in Planning.
Dimensions available for reporting correspond to expense columns in Planning. Metrics correspond to
the values listed for each period.

To view a list of dimensions for reporting, complete the following steps:

1. In the Plan menu, select a plan.

   See [Find your way around Planning](../navigate-apptio-planning.html).
2. From the left navigation menu, select Planning > Expenses.
3. In the Plan section menu, select a department.
4. Navigate to any of the following tabs: Summary, Labor, Contracts, and Assets.
5. Click the drop-down arrow on a column name, then click Show/Hide Columns…
6. The dimensions available correspond to this list of columns, regardless of whether that column
   is shown or hidden.

In Apptio BI, a report is a collection of visualizations. When you create a new report, it will
be empty. You can add visualizations to the report to display data.

Custom columns are supported for use in reporting.

Remember:

- Apptio BI will report against your Planning production environment.
- Apptio BI requires Planning 2.76 or later.
- Multi-currency is supported.

Note:

- Sensitive labor data (like Base Compensation) are not exposed to Apptio BI.
- ITP DataSources in Apptio BI shows only data for Department cost object type. Project data is currently not supported.
- PFP related data like delegated cost dimensions are not exposed to Apptio BI until PFP is supported.
- Actuals spend data from Spend Management.

## Download the data list

For the list of dimensions and metrics available from Planning in Apptio BI: [download as a .xslx file](../../../resources/multimedia/itp%20-%20ssr%20integration/it%20planning%20data%20exposed%20to%20self%20service%20reporting_2020_12_08.xlsx).
