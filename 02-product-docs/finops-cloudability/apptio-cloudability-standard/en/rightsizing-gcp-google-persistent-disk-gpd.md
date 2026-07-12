---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "GCP Google Persistent Disk (GPD)"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "GCP Google Persistent Disk (GPD)"
source_path: "SSVCLNQ/product/rightsizing-for-gpd.html"
images:
  - "03-media/apptio-cloudability-standard/rightsizing-gcp-gpd.jpg"
  - "03-media/apptio-cloudability-standard/edit-icon.jpg"
  - "03-media/apptio-cloudability-standard/rightsizing-gcp-gpd-details.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GCP Google Persistent Disk (GPD)

You can use the Rightsizing dashboard to view the resource optimization recommendations for Google Persistent Disk (GPD) resources. The dashboard shows rightsizing, terminate, and no action recommendations.

Rightsizing in Cloudability

Before you begin

To view the GPD dashboard, make sure that the following requirements are met:

Enable the correct permissions. Navigate to Settings > Vendor Credentials > GCP , and ensure that the Advanced Features column has a green check mark for each project.

Install the Cloud Monitoring agent to improve the quality of recommendations. This is optional but recommended.

Access the GPD dashboard

To access the GPD dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the GCP tab, and then select the GPD sub tab to view recommendations for Google Persistent Disk.

Customize the dashboard

You can set the following options to customize your dashboard.

All costs for GPD are currently shown using the On-Demand Cost Basis.

The On-Demand cost basis provides a direct comparison between the resource listed in the Current column and the resource recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Committed Use Discounts.

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

- Total Spend: Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your GPD resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource ID : The ID of the resource.
- Resource Name : The GPD resource name.
- Account Name : The GPD account name.
- Data Source : The GCE data source.
- Idle : The percent of hours with zero IOPS.
- State : The state can be Attached , Unattached , or Deleted .
- Cost : The total cost of the GCE resource for the selected timeline.
- Type :The current GPD resource type.
- Size :The current GPD resource type.
- New Type : The top recommended GPD resource type.
- New Size : The top recommended GPD resource size (in GiB).
- Action : Recommendation for the resource. The recommendation can be one of the following. Recommendation Description Rightsize Resize to the resource type specified in the New column. Terminate Terminate your resource because it is predominantly idle. No Action No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel.
- Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .
