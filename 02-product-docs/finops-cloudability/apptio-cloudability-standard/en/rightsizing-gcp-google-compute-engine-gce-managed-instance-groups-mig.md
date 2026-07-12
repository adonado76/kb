---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "GCP Google Compute Engine (GCE) Managed Instance Groups (MIG)"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "GCP Google Compute Engine (GCE) Managed Instance Groups (MIG)"
source_path: "SSVCLNQ/product/rightsizing-for-gcp-gce-mig.html"
images:
  - "03-media/apptio-cloudability-standard/mig-help-image-2.jpg"
  - "03-media/apptio-cloudability-standard/edit-icon.jpg"
  - "03-media/apptio-cloudability-standard/mig-help-image2.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# GCP Google Compute Engine (GCE) Managed Instance Groups (MIG)

You can use the Rightsizing dashboard to view the resource optimization recommendations for Google Cloud Platform (GCP) Google Compute Engine (GCE) Managed Instance Groups (MIG). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Learn about Rightsizing in Cloudability

Learn about Autoscale Action for Rightsizing

Before you begin

To view the GCP GCE MIG dashboard, make sure that the following requirements are met:

- You have connected Cloudability to the correct GCP accounts.
- You are using GCP Managed Instance Groups.

Learn about Connect Google Cloud

Currently, this feature has the following limitations:

- GCE MIG recommendations are unavailable for mixed instance types. The dashboard shows these MIGs without any actionable recommendations.
- The recommendations exclude spot instances. The dashboard only shows on-demand instances.

Access the GCP GCE MIG dashboard

To access the GCP GCE MIG dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the GCP tab, and then select the GCE MIG subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand or Effective . The On-Demand cost basis is selected by default.

If your organization has enabled Custom Pricing in Cloudability , the relevant custom rates will be applied to the cost basis calculations.

- On-Demand : The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability
- Effective : The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. n other words, the Effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended new instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures, if applicable.

Use the On-Demand cost basis if you are looking to remove the unpredictable nature of commitment-based discounts from your analysis and to maximize the number of recommendations provided to you. Use the Effective cost basis if you prefer to base your recommendations on the historical True Cost of running your instances and to take a conservative approach.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Account dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days . For most users, 10 days is the recommended time period because it captures the most recent performance trends and is more predictive of future resource use.

Apply Options

You can also set page-level options to include or exclude certain recommendations.

Apply filters

You can add filters to include or exclude data based on one or more conditions.

Add a filter

To add a filter:

1. Select Add Filter from the toolbar.
1. In the Add Filter menu, choose a Dimension .
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

Select the filter icon that appears when you hover over Filters .

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

For GCE, spend is determined by instance usage.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of all your GCE MIG resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource Name: The MIG resource name.
- Account Name: The MIG account name
- Region : The MIG region.
- Data Source: The source or APM providing the data.
- Min Instance Count : The minimum number of instances observed.
- Max Instance Count: The maximum number of instances observed.
- Idle: The time spent below 2% CPU on a scale of 1-100.
- Cost: The total cost of all running instances in the MIG
- Current: The current MIG resource type. (for single type MIGs)
- New: The top recommended MIG resource type.
- Action: Recommendation for the resource. The recommendation can be one of the following Recommendation Description Terminate Terminate your resource because it is predominantly idle. Autoscale Set up autoscaling for the resource. No Action No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel.
- Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

In addition to the information provided in the GCE details panel, the MIG details panel shows the following information:

- Instance Count : The observed minimum and maximum instance count
- Action (Autoscale) : When the recommended action for an MIG is Autoscale , the recommended minimum and maximum instance count configuration is shown in parentheses next to the text. For more information on how autoscale recommendations are used, refer to Autoscale Action for Rightsizing .
- Risk : Characterizes the likelihood to reach capacity limits for a given recommendation, based on scaling up to larger number of instances with lower individual capacity.

- Disk metrics are not used for autoscaling recommendations.
- For GPU-based MIGs, support is only for a2 machine-based homogenous MIGs.
