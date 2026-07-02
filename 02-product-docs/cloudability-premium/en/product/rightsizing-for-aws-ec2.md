---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "AWS EC2"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Rightsizing"
source_path: "product/rightsizing-for-aws-ec2.html"
images:
  - "images/edit-icon.jpg"
  - "images/rightsizing-aws-ec2-dashboard.jpg"
  - "images/rightsizing-aws-ec2-details.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS EC2

You can use the Rightsizing dashboard to view the resource optimization recommendations for
Amazon Web Services (AWS) Elastic Compute Cloud (EC2). The dashboard shows both the rightsizing and
idle (terminate) recommendations. You can view the recommendations across multiple accounts from a
single dashboard.

[Rightsizing
in Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Before you begin

To view the AWS EC2 dashboard, make sure that you have connected Cloudability to the correct AWS
accounts.

[Connecting with AWS - Customer
Integration Guide](../admin/aws-credentialing-standard-enterprise-home.html)

Access the AWS EC2 dashboard

To access the AWS EC2 dashboard, open the Cloudability home page, and from the left navigation
menu, select  Optimize > Rightsizing  . On the  Rightsizing  page, select the
 AWS  tab, and then select the  EC2  subtab.

![Rightsizing AWS EC2 Screenshot](../../../../03-media/cloudability-premium/images/rightsizing-aws-ec2-dashboard.jpg)

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be 
On-Demand  or  Effective  . The On-Demand cost basis is selected
by default.

Note:

If your organization has enabled  Custom Pricing  in Cloudability , the
relevant custom rates will be applied to the cost basis calculations.

- On-Demand:  The On-Demand cost basis provides a direct comparison
  between the instance listed in the  Current  column and the instance
  recommended in the  New  column based purely on  On-Demand Pricing 
  . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs).
  Note that the on-demand prices will reflect any custom pricing agreements that you have configured
  in Cloudability.
- Effective:  The Effective cost basis takes into account the historical
  impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current
  instance type over the reporting period. Like the Cost (Amortized) metric, it includes all
  associated upfront and recurring costs.   
   In other words, the Effective cost basis shows
  the effective cost of running your current instance. The cost figures for the recommended new
  instance type are based on the on-demand prices. This is because the new configuration may not
  benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently
  move away from RIs or SPs, your new overall rate will still be better. As a result, the overall
  savings reported using this methodology will sometimes be lower. Custom pricing will be applied to
  these figures, if applicable.

Use the On-Demand cost basis if you are looking to remove the unpredictable nature of
commitment-based discounts from your analysis and to maximize the number of recommendations provided
to you. Use the Effective cost basis if you prefer to base your recommendations on the historical
 True Cost  of running your instances and to take a conservative approach.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a
particular account, select the account name from the  Account  dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the
 Timeline  option is set to  10 days  . For most
users, 10 days is the recommended time period because it captures the most recent performance trends
and is more predictive of future resource use.

Apply Options

You can also set page-level options to include or exclude certain recommendations.

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
rule is automatically applied to the  Filters  field. You can select only one
value or parameter from each column at a time.

Remove a filter

To remove a filter:

1. Select the filter icon ![filter icon](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Select  X  next to the filter that you want to remove.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend  : Shows the total current allocated spend.
- Estimated Idle Savings  : Shows the estimated total savings for all
   Terminate  recommendations.
- Estimated Rightsize Savings  : Shows the estimated total potential
  savings achievable for all  Rightsize  recommendations.
- Estimated Optimized Spend  : Shows the estimated total spend after
  recommendations are applied.

Note:

For EC2, spend is determined by instance usage.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of EC2
resources for which recommendations have been identified. The table includes the following columns:

Note:

By default, the data is sorted by the  Cost Savings  column. To change
the sort order, just select the column name.

- Resource ID:  The EC2 resource ID.
- Resource Name  : The EC2 resource name.
- Account Name  : The EC2 account name.
- Data Source  : The EC2 data source.
- Idle  : The time spent below 2% CPU on a scale of 1-100.
- Cost  : The total cost of all running instances in EC2.
- Current  : The current EC2 instance type.
- New  : The top recommended EC2 instance type.
- Action  : Recommendation for the resource. The recommendation can be one
  of the following.

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the  New  column. |
| Terminate | Terminate your resource because it is predominantly idle. |
| Autoscale | Set up autoscaling for the resource. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |
| Incomplete Util Data | Ensure that your policy is up to date with the latest permissions. Otherwise, determine if the resource was active for less than an hour, as it may not appear in the  Describe Data  cache from AWS. |

Cost Savings  : The estimated 10- or 30-day cost savings amount.

Note:

When we recommend that you move an EC2 instance type to an instance with no local storage, we
incorporate into the recommendation that you add EBS and account for both in the savings.

Export recommendations to an Excel file

To export the recommendations to an excel file, select  Export  . Note
that the excel file will include several additional columns, such as region, operating system, unit
price, and others.

Recommendation details

To view the recommendation details for a particular resource, select  View Details
 from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

![recommendation details AWS EC2 screenshot  ](../../../../03-media/cloudability-premium/images/rightsizing-aws-ec2-details.jpg)

To view descriptions of the cost dimensions and metrics, refer to  [Glossary of cost dimensions and metrics](glossary-of-cost-dimensions-and-metrics.html) 
.

To view details of the utilization dimension and metrics, refer to  [Glossary of utilization dimensions and
metrics](glossary-of-utilization-dimensions-and-metrics.html)  .

**Parent topic:** [Rightsizing](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
