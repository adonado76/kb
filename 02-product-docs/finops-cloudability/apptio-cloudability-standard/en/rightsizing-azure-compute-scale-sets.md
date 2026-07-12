---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Azure Compute Scale Sets"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "Azure Compute Scale Sets"
source_path: "SSVCLNQ/product/azure_compute_scale_sets.html"
images:
  - "03-media/apptio-cloudability-standard/edit-icon.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Azure Compute Scale Sets

You can use the Rightsizing dashboard to view the resource optimization recommendations for Microsoft Azure Compute managed via Scale Sets. The dashboard shows rightsizing and idle (terminate) recommendations for both homogenous and heterogenous Scale Sets. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

## Before you begin

To view the Azure Compute dashboard, make sure that you have connected Cloudability to the correct Azure accounts.

Connect Microsoft Azure

## Access the Azure Compute Dashboard

To access the Azure Compute dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the Azure tab, and then select the Compute Scale Sets subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand or Effective . The On-Demand cost basis is selected by default.

Note:

If your organization has enabled Custom Pricing in Cloudability , the relevant custom rates will be applied to the cost basis calculations.

- On-Demand : The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability
- Effective : The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. In other words, the Effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended new instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures, if applicable.

Note:

Use the On-Demand cost basis if you are looking to remove the unpredictable nature of commitment-based discounts from your analysis and to maximize the number of recommendations provided to you. Use the Effective cost basis if you prefer to base your recommendations on the historical True Cost of running your instances and to take a conservative approach.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Account dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days . For most users, 10 days is the recommended time period because it captures the most recent performance trends and is more predictive of future resource use.

Apply Options

You can also set page-level options to include or exclude certain recommendations.

Apply Filters

You can add filters to include or exclude data based on one or more conditions.

Add a filter

To add a filter:

1. Select Add Filter from the toolbar.
1. In the Add Filter menu, choose a Dimension.
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter rule is automatically applied to the Filters field. You can select only one value or parameter from each column at a time.

Remove a filter

To remove a filter:

1. Select the filter icon .
1. Select X next to the filter that you want to remove.

## Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

## Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of Compute resources for which recommendations have been identified. The table includes the following columns:

Note:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource Name : The ScaleSet resource name.
- Account Name : The account name where the resources are running
- Resource Group : The Compute resource group.
- Data Source : The data source used for relevant utilization data
- Idle : The time spent below 2% CPU on a scale of 1-100.
- Cost: The total cost of all running instances in Compute.
- Current : The current Compute instance type. For heterogenous scalesets, a value of “Mixed” will populate the Current field
- New : The top recommended Compute instance type.
- Action : Recommendation for the resource. The recommendation can be one of the following

| Recommendation | Description |
| --- | --- |
| Recommendation | Description |
| Rightsize | Resize to the resource type specified in the New column. |
| Terminate | Terminate your resource because it is predominantly idle. |
| Autoscale | Set up autoscaling for the resource. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

Parent topic:

Rightsizing in Cloudability
