---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Azure SQL"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "Azure SQL"
source_path: "SSVCLNQ/product/rightsizing-for-azure-sql.html"
images:
  - "03-media/apptio-cloudability-standard/azure-sql-1.jpg"
  - "03-media/apptio-cloudability-standard/edit-icon.jpg"
  - "03-media/apptio-cloudability-standard/azure-sql-2.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Azure SQL

You can use the Rightsizing dashboard to view the resource optimization recommendations for Azure SQL. The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Before you begin

To view the Azure SQL dashboard, make sure that you have connected Cloudability to the correct Azure accounts.

Connect Microsoft Azure

Access the Azure SQL dashboard

To access the Azure SQL dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the Azure tab, and then select the SQL subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Account dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days . For most users, 10 days is the recommended time period because it captures the most recent performance trends and is more predictive of future resource use.

Apply Filters

You can add filters to include or exclude data based on one or more conditions.

Add a filter

To add a filter:

1. Select Add Filter from the toolbar.
1. In the Add Filter menu, choose a Dimension .
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter rule is automatically applied to the Filters field. You can select only one value or parameter from each column at a time.

Remove a filter

To remove a filter:

1. Select the filter icon .
1. Select X next to the filter that you want to remove.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of SQL resources for which recommendations have been identified. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Server : The name of the server.
- Resource Name : The SQL resource name.
- Instance Type : The SQL solution type.
- Account Name : The Azure account name.
- Resource Group : The group the SQL resource belongs to.
- Idle : Based on the number of the active DB connections/ sessions at a given point in time.
- Cost : The total cost of the SQL solution for the selected timeline.
- Current : The current resource type.
- New : The top recommended resource type
- Action : Recommendation for the resource. The recommendation can be one of the following. Recommendation Description Rightsize Resize to the resource type specified in the New column. Terminate Terminate your resource because it is predominantly idle. No Action No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel.
- Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .
