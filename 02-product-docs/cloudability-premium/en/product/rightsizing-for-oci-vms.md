---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "OCI Virtual Machines (VMs)"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Rightsizing"
source_path: "product/rightsizing-for-oci-vms.html"
images:
  - "images/edit-icon.jpg"
  - "images/oci-vm-dashboard.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# OCI Virtual Machines (VMs)

You can use the Rightsizing dashboard to view the resource optimization recommendations for
Oracle Cloud Infrastructure (OCI) Virtual Machine (VM) resources. The dashboard shows both the
rightsizing and idle (terminate) recommendations.

[Rightsizing
in Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Before you begin

To view the OCI VM dashboard, make sure that you have connected Cloudability to the correct OCI
tenancies. You need to validate credentials for both the parent tenancies and the child tenancies.

[Connect Oracle Cloud](../admin/connect-oracle-cloud.html)

Access the OCI VM dashboard

To access the OCI Virtual Machine dashboard, open the Cloudability home page, and from the left
navigation menu, select  Optimize > Rightsizing  . On the 
Rightsizing  page, select the  OCI  tab, and then select the
 VM  subtab.

![oci dashboard screenshot](../../../../03-media/cloudability-premium/images/oci-vm-dashboard.jpg)

Customize the dashboard

You can set the following options to customize your dashboard.

All costs for VMs are currently shown only using the On-Demand Cost Basis.

Select Account

By By default, the dashboard shows recommendations for all accounts/tenancies. To view
recommendations for a particular account, select the account name from the  Account
 dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the
Timeline option is set to 10 days. For most users, 10 days is the recommended time period because it
captures the most recent performance trends and is more predictive of future resource use.

Apply Filters

You can add filters to include or exclude data based on one or more conditions.

Add a filter

To add a filter:

1. Select Add Filter from the toolbar.
2. In the Add Filter menu, choose a Dimension.
3. Select an Operator to provide a logical condition.
4. Choose a value to refine your filter.
5. Select Add Filter to apply the new filter to the page.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter
rule is automatically applied to the  Filters  field. You can select only one value or
parameter from each column at a time.

Remove a filter

To remove a filter:

1. Select the filter icon ![Notes Icon](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. Select X next to the filter that you want to remove.

Apply Options

You can also set page-level options to include or exclude certain recommendations.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend: Shows the total current allocated spend.
- Estimated Idle Savings: Shows the estimated total savings for all
  Terminate  recommendations.
- Estimated Rightsize Savings: Shows the estimated total potential savings
  achievable for all Rightsize recommendations.
- Estimated Optimized Spend: Shows the estimated total spend after
  recommendations are applied.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your
VM resources. The table includes the following columns:

Note:

By default, the data is sorted by the  Cost Savings  column. To change the sort order,
just select the column name.

- Resource ID : The VM resource ID.
- Resource Name: The VM resource name.
- Account Name : The VM account name.
- Data Source : The VM data source
- Idle : The time spent below 2% CPU on a scale of 1-100.
- Cost : The total cost of the VM resource for the selected timeline.
- Current :The current VM resource type.
- New : The top recommended VM resource type
- Action: Recommendation for the resource. The recommendation can be one of
  the following.

  | Recommendation | Description |
  | --- | --- |
  | Rightsize | Resize to the resource type specified in the  New  column. |
  | Terminate | Terminate your resource because it is predominantly idle. |
  | No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |
- Cost Savings: The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select  Export  . Note that the excel
file will include several additional columns and data.

Recommendation details

To view the recommendation details for a particular resource, select  View Details 
from the More Options (3 dots) menu.

To view descriptions of the cost dimensions and metrics, refer to  [Glossary of cost dimensions and metrics](glossary-of-cost-dimensions-and-metrics.html) 
.

To view details of the utilization dimension and metrics, refer to  [Glossary of utilization dimensions and
metrics](glossary-of-utilization-dimensions-and-metrics.html)  .

**Parent topic:** [Rightsizing](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
