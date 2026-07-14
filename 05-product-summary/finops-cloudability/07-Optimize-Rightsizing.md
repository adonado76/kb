---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "07-Optimize-Rightsizing"
source_files_count: 24
last_updated: "2026-07-13"
---

# 07-Optimize-Rightsizing

## Rightsizing

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing
- **source_path:** SSVCLNQ/product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html
- **original_file:** optimize-rightsizing.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing-explorer.jpg

With Rightsizing, you can define the optimal cloud infrastructure best suited for your current and near-term needs in a way that balances risk and cost to minimize waste.

Using the Rightsizing dashboards, you can see cloud resource utilization over time. You can then view recommended scenarios for each resource to better inform your cloud rightsizing decisions.

There are two Rightsizing dashboards:

- Rightsizing: View rightsizing recommendations for your cloud services. Rightsizing Dashboard .
- Rightsizing ROI: View potential and realized savings for tickets synchronized with Jira Rightsizing using a Jira integration .

The Rightsizing dashboard displays the Explorer tab by default. The Rightsizing Explorer gives an overview of possible savings across all Cloud resources used by your company. You can use this dashboard to group, filter and navigate your rightsizing recommendations.

Rightsizing Explorer .

The additional tabs in Rightsizing are recommendations for specific cloud providers.

### Rightsizing FAQ

Why is the default recommendation time period 10 days?

10 days captures the most recent performance trends and is more predictive of future resource use.

How is Idle defined?

Idle is defined differently based on the resource type, but generally is represented as the following: Idle for Compute (for example EC2) is the time spent below 2% CPU on a scale of 1-100. Idle for Block Storage/ Disk (for example EBS) is the percent of hours with zero IOPS. Idle for Relational Storage/ Database (for example RDS) is based on the number of the active DB Connections/ Sessions at a given point in time.

How do you determine spend?

Spend is instance usage spend for Compute (For example EC2) and Relational Storage/ Database (For example RDS). Data Warehouse (For example Redshift) excludes data transfer. For Object & Block Storage (For example S3 & EBS), spend is determined by GB Months.

Why doesn't Total Spend in Rightsizing exactly match the values shown in Reporting / True Cost Explorer?

Rightsizing only lists resources for which it found at least one money-saving resource so it is likely these values will not match exactly.

Why do I see (not set) under State for EBS?

The account has insufficient permissions (ensure your policy is up to date with the latest permissions) or the resource was active for less than an hour ( the data does not appear in the Describe Data cache from AWS).

Why do I see N/A for lastAttachedTime for unattached EBS volumes?

Volumes will show the timestamp from their last attachment to EC2 instances and the volumeID. For volumes that have not been attached during the rightsizing window (the last 10 days by default), it will show N/A.

For EC2, do the recommendations take into account burst?

We use baseline performance for burstable resources (for example, T2 instance types) and do not account for the burst in determining the recommendations. This ensures we make conservative recommendations that won't result in resource clipping.

For EC2, how do you determine Network and Disk?

AWS does not report EC2 Network and Disk throughput limits. Furthermore, the throughput capacity will vary based on both workload (for example, sequential versus random read and write) and transfer (for example, data transfer within a region versus across regions). We use commonly observed limits across our customer portfolio to approximate capacity.

Why are Spot Instances excluded from rightsizing recommendations?

Our rightsizing engine takes into account your workload (utilization metrics) and the cost to run it (current instance type and on-demand price) and generates a list of recommendations from which you can choose to help save you money. Spot Instances, on the other hand, are already offered at steep discounts; applying rightsizing in these situations results in negligible savings. For this reason, we have chosen to exclude Spot Instances from rightsizing.

When we recommend that you move an EC2 instance type to an instance with no local storage, we incorporate into the recommendation that you add EBS and account for both in the savings.

How frequently are recommendations updated?

We update our rightsizing recommendations daily. You can access recommendations for resources 24 hours after the resource is created, provided that there is enough utilization data.

How does Cloudability determine rightsizing recommendations?

Rightsizing recommendations are generated using Cloudability ’s best-in-breed proprietary rightsizing algorithm. These recommendations vary for different CSPs (Cloud Service Providers) and services but typically the metrics being factored in are those shown in the graphs within the details pane of the recommendations. For example, compute recommendations would typically look at a combination of CPU, Network, Disk, Memory, and possibly a few other metrics and the utilization over the selected time periods to understand the best options.

What should I keep in mind when looking at rightsizing recommendations?

When looking at the rightsizing recommendations, you first need to understand the difference between the available Cost Basis options and which you intend to use. Secondly, use your due diligence when implementing a certain recommendation as Cloudability does not know the purpose of each resource. Your teams may have kept certain resources 'idle' or 'under-utilized' for a specific purpose but Cloudability may recommend to terminate or reduce the size of resources.

In Rightsizing section, can we set the look back period (timeline) to 60 days?

Currently, rightsizing in Cloudability only supports the look back period or timeline of 10 Days and 30 Days .

What are the various state values displayed in Azure disk rightsizing and what do they mean?

In Rightsizing recommendations for Azure disk, the state values are:

- ActiveSAS: The disk currently has an Active SAS Uri associated with it.
- ActiveSASFrozen: The disk is attached to a VM in hibernated state and has an active SAS URI associated with it.
- ActiveUpload: A disk is created for upload and a write token has been issued for uploading to it.
- Attached: The disk is currently attached to a running VM.
- Frozen: The disk is attached to a VM which is in hibernated state.
- ReadyToUpload: A disk is ready to be created by upload by requesting a write token.
- Reserved: The disk is attached to a stopped-deallocated VM.
- Unattached: The disk is not being used and can be attached to a VM.

See the following Azure documentation under "fields" for the latest values and their definitions https://learn.microsoft.com/en-us/dotnet/api/microsoft.azure.management.compute.models.diskstate?view=azure-dotnet-legacy#fields

Do rightsizing recommendations take into account the Cloud Service Provider (CSP) discounts due to hourly commits? If the recommendations are applied, does the hourly spend go down?

For AWS a custom cost metric must be in place. For Azure and GCP a pricing sheet is provided by these cloud service providers. So, custom pricing is not required. The hourly spends come into effect the next time after the cost and usage data is ingested and processed.

---

## Amazon Redshift

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Amazon Redshift
- **source_path:** SSVCLNQ/product/aws_redshift.html
- **original_file:** rightsizing-amazon-redshift.md
- **images:**
  - 03-media/apptio-cloudability-standard/Redshift-Rightsizing.jpg
  - 03-media/apptio-cloudability-standard/Redshift-Rightsizing-Details.jpg

You can use the Rightsizing dashboard to view resource optimization insights for Amazon Redshift clusters. The dashboard shows utilization metrics and identifies clusters with potential savings opportunities. You can view insights across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Before you begin

To view the Amazon Redshift dashboard, make sure that you have connected Cloudability to the correct AWS accounts.

Connecting with AWS - Customer Integration Guide

Access the Amazon Redshift dashboard

To access the Amazon Redshift dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the AWS tab, and then select the Redshift subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Select Account

By default, the dashboard shows insights for all accounts. To view insights for a particular account, select the account name from the Account dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days . For most users, 10 days is the recommended time period because it captures the most recent performance trends and is more predictive of future resource use.

Apply Filters

You can add filters to include or exclude data based on one or more conditions. To add a filter, select Add Filter from the toolbar and configure the dimension, operator, and value.

Redshift insights table

The dashboard contains an insights table, which provides an overview of Redshift clusters with optimization opportunities. The table includes the following columns:

By default, the data is sorted by the Priority Score column to help you identify clusters with the highest savings potential. To change the sort order, select the column name.

- Priority Score : The optimization priority ranking (0–100), where 100 represents the highest potential savings opportunity.
- Resource Name : The name of the Redshift cluster.
- Comment : User-provided notes or annotations for the cluster.
- Last Seen : The most recent date the cluster was detected.
- Class : The node type classification of the cluster.
- Account Name : The AWS account name.
- Node Count : The number of nodes in the cluster.
- Idle : The percentage of time CPU was below 2% during the selected timeline. Higher idle percentages indicate the cluster is rarely active.
- CPU : The average CPU utilization percentage for the cluster during the selected timeline. Low average CPU with minimal spikes suggests the cluster may be over provisioned.
- Storage : The percentage of allocated disk space in use. Near-zero storage utilization may indicate the cluster contains little or no data.
- Utilization : The combined CPU and storage utilization score. Lower scores indicate lower usage and higher optimization potential.
- Cost : The total cost of the cluster for the selected timeline.

Evaluate optimization opportunities

The Redshift dashboard provides utilization metrics to help you identify clusters with savings potential. By default, the table is sorted by the highest Priority Score to focus on clusters with the greatest optimization opportunities. Unlike some other service types, the Redshift insights page currently focuses on utilization advisories rather than explicit prescriptive actions. Review the utilization metrics and charts to determine the appropriate action.

Export insights to an Excel file

To export the insights to an Excel file, select Export . The Excel file includes several additional columns, such as region, node configuration, and cost breakdown.

Recommendation details

To view utilization details for a particular cluster, select View Details from the More Options (3 dots) menu. The details panel displays CPU and storage utilization charts for the selected timeline.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

---

## Autoscale Action for Rightsizing

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Autoscale Action for Rightsizing
- **source_path:** SSVCLNQ/product/rightsizing-autoscale-action.html
- **original_file:** rightsizing-autoscale-action.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing-autoscale-instance-to-asg.jpg

One challenge in resource optimization is correctly sizing for workloads that exhibit widely fluctuating and spiking workloads. As illustrated by large swings in the utilization metric data (CPU, network, memory, and GPU), this scenario is typically addressed by over-provisioning the resource to accommodate the highest peaks in these workloads, resulting in excess cloud spend.

To better fit compute resources to these highly elastic workloads, we are enhancing the Autoscale recommendation. The Autoscale action recommends converting a single instance to an Auto Scaling Group (ASG). Instead of a single high-capacity instance, the ASG comprises multiple, smaller instances that are spun up and down to meet this elastic workload's demands. If your workload can accommodate scaling across multiple machines, this is a cost-effective option.

Using the Autoscale Recommendation

The details pane shows the list of recommended actions. When an Autoscale action is selected, the minimum and maximum instance counts will be displayed. We model target tracking on CPU, network, memory (if available), GPU (if available) utilization data to derive these instance counts. The recommendation is for an ASG ranging from 1 to 4 of type c4.4xlarge instances in the example below.

Looking at the CPU and Memory charts above, notice the legend on the right represents the number of instances. In this example, the yellow dotted line moves between 1 and 3, indicating this range is sufficient to cover the workload. When determining the maximum instance count, we recommend the instance count that matches the original instance’s memory size. Specifically, the current c4.4xlarge has 30 GiB, while the recommended c4.xlarge instance has 7.5 GiB memory. The original has four times as much memory, so we recommend a maximum instance count that matches the upper bound. Recall that you will not be charged for instances in an ASG that are not active, so this is a cost-effective option.

Read this to learn more about ASG target tracking scaling policies and implementation details.

Considerations

Here is a list of issues to consider at this time:

The risk is set to a minimum of 1 as not all workloads are appropriate for ASGs.

Members of the existing Auto Scaling Group are excluded from this type of recommendation.

Only Amazon EC2 (Elastic Cloud Compute) is supported at this time.

Burstable instance, families (T2, T3, T3a, and T4g) are excluded.

EC2 target tracking dynamic scaling policies are triggered by either CPU utilization, Network In/Out bytes, or Application Load Balancer request counts by default. Optionally, other Cloudwatch or custom metrics can be used as triggers, with additional configuration.

---

## AWS EBS

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > AWS EBS
- **source_path:** SSVCLNQ/product/rightsizing-for-aws-elastic-block-store.html
- **original_file:** rightsizing-aws-ebs.md
- **images:**
  - 03-media/apptio-cloudability-standard/ebs-final.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/ebs-details-final.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Amazon Web Services (AWS) Elastic Block Store (EBS). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Before you begin

To view the AWS EC2 EBS dashboard, make sure that you have connected Cloudability to the correct AWS accounts.

Connecting with AWS - Customer Integration Guide

Access the AWS EC2 EBS dashboard

To access the AWS EC2 EBS dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the AWS tab, and then select the EBS subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Only the On-Demand Cost Basis is supported for EBS.

The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.

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

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsizing Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

Rightsizing recommendations table

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource ID : The volume ID.
- Resource Name : The volume name.
- Account Name : The AWS account name.
- Idle : The percent of hours with zero IOPS.
- State : The state can be Attached , Unattached , or Deleted .
- Cost : The total cost of the volume.
- Type :The volume type.
- Size : The volume size (in GiB).
- New Type : The top recommended volume type.
- New Type : The top recommended volume type.
- New Size : The top recommended volume size (in GiB).
- Action : Recommendation for the resource. The recommendation can be one of the following.

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New column. |
| Terminate | Terminate your resource because it is predominantly idle. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

- Last Billing Date : The last date for which the cost data is available.
- Last Attached Date : The last date the volume state was attached.
- Last Attached ID : The last instance ID to which the volume was attached.
- Type : The volume type.
- Size : The volume size.
- Throughput : The maximum volume throughput.
- IOPS : The maximum volume IOPS.
- Risk (under recommendations) : Characterizes the likelihood to reach capacity limits for a given recommendation.
- Utilization Metrics : The utilization metrics displayed for EBS volumes are based on the following parameters.

| Parameter | Description |
| --- | --- |
| Throughput (MB/S) | Throughput Max (blue line) : The maximum MB/S of throughput utilized in the indicated hour. Capacity (red line) : The throughput capacity in MB/S in the indicated hour. Recommended (yellow dashed line) : The recommended throughput capacity in MB/S in the indicated hour. |
| IOPS (Count) | IOPS Max (blue line) : The maximum IOPS utilized in the indicated hour. Capacity (red line) : The IOPS capacity in the indicated hour. Recommended (yellow dashed line) : The recommended IOPS capacity in the indicated hour. |

---

## AWS EC2

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > AWS EC2
- **source_path:** SSVCLNQ/product/rightsizing-for-aws-ec2.html
- **original_file:** rightsizing-awsec2.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing-aws-ec2-dashboard.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/rightsizing-aws-ec2-details.jpg

## AWS EC2

You can use the Rightsizing dashboard to view the resource optimization recommendations for Amazon Web Services (AWS) Elastic Compute Cloud (EC2). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Before you begin

To view the AWS EC2 dashboard, make sure that you have connected Cloudability to the correct AWS accounts.

Connecting with AWS - Customer Integration Guide

Access the AWS EC2 dashboard

To access the AWS EC2 dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the AWS tab, and then select the EC2 subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand or Effective . The On-Demand cost basis is selected by default.

If your organization has enabled Custom Pricing in Cloudability , the relevant custom rates will be applied to the cost basis calculations.

- On-Demand: The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.
- Effective: The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. In other words, the Effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended new instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures, if applicable.

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
1. In the Add Filter menu, choose a Dimension .
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter rule is automatically applied to the Filters field. You can select only one value or parameter from each column at a time.

Remove a filter

1. Select the filter icon .
1. Select X next to the filter that you want to remove.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

For EC2, spend is determined by instance usage.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of EC2 resources for which recommendations have been identified. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource ID: The EC2 resource ID.
- Resource Name : The EC2 resource name.
- Account Name : The EC2 account name.
- Data Source : The EC2 data source.
- Idle : The time spent below 2% CPU on a scale of 1-100.
- Cost : The total cost of all running instances in EC2.
- Current : The current EC2 instance type.
- New : The top recommended EC2 instance type.
- Action : Recommendation for the resource. The recommendation can be one of the following.

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New column. |
| Terminate | Terminate your resource because it is predominantly idle. |
| Autoscale | Set up autoscaling for the resource. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |
| Incomplete Util Data | Ensure that your policy is up to date with the latest permissions. Otherwise, determine if the resource was active for less than an hour, as it may not appear in the Describe Data cache from AWS. |

Cost Savings : The estimated 10- or 30-day cost savings amount.

When we recommend that you move an EC2 instance type to an instance with no local storage, we incorporate into the recommendation that you add EBS and account for both in the savings.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

---

## AWS EC2 Autoscaling Group (ASG)

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > AWS EC2 Autoscaling Group (ASG)
- **source_path:** SSVCLNQ/product/rightsizing-for-aws-autoscaling-groups.html
- **original_file:** rightsizing-aws-ec2-autoscaling-group-asg.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing-aws-ec2_asg_dashboard.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/recommendations-aws-autoscaling.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Amazon Web Services (AWS) Elastic Compute Cloud (EC2) Auto Scaling Groups (ASG). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Autoscale Action for Rightsizing

Before you begin

To view the AWS EC2 ASG dashboard, make sure that the following requirements are met:

You have connected Cloudability to the correct AWS accounts.

You are using AWS AutoScaling Groups.

The aws:autoscaling:groupName tag is included in the Cost and Usage Report (CUR) files provided to Apptio and the updated files have been ingested.

Connecting with AWS - Customer Integration Guide

Currently, this feature has the following limitation:

- The recommendations exclude spot instances. The dashboard only shows on-demand instances.

Access the AWS EC2 ASG dashboard

To access the AWS EC2 ASG dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the AWS tab, and then select the EC2 ASG subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand or Effective . The On-Demand cost basis is selected by default.

Refer to learn more.

- On-Demand: The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.
- Effective: The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. In other words, the Effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended New instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures, if applicable.

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

1. Select the filter icon .
1. Select X next to the filter that you want to remove.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

For EC2, spend is determined by instance usage.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of all your EC2 ASG resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource ID: The account ID plus the ASG name.
- Resource Name : The ASG name.
- Account Name : The AWS account name.
- Data Source : The source or APM (such as Cloudwatch) providing the data.
- Min Instance Count : The minimum number of instances observed.
- Max Instance Count : The maximum number of instances observed.
- Idle : The time spent below 2% CPU on a scale of 1-100.
- Cost : The total cost of all running instances in the ASG.
- Current : The ASG instance type. For ASGs with multiple types, the column will show multiple .
- New : The top recommended ASG instance type.
- Action : Recommendation for the resource. The recommendation can be one of the following.

| Recommendation | Description |
| --- | --- |
| Terminate | Terminate your resource because it is predominantly idle. |
| Autoscale | Set up autoscaling for the resource. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

In addition to the information provided in the EC2 details panel, the ASG details panel shows the following information:

Instance Count : The observed minimum and maximum instance count.

Action (Autoscale) : When the recommended action for an ASG is Autoscale , the recommended minimum and maximum instance count configuration is shown in parentheses next to the text. For more information on how autoscale recommendations are used, refer to Autoscale Action for Rightsizing .

Risk : Characterizes the likelihood to reach capacity limits for a given recommendation, based on scaling up to larger number of instances with lower individual capacity.

Utilization Metrics : The utilization metrics displayed for ASGs are based on the following parameters:

| Parameter | Description |
| --- | --- |
| CPU Total (%) | CPU Total (blue line) : The normalized percentage of maximum CPU utilization in the indicated hour, based on the maximum instance count for the entire ASG in the time window of 10 or 30 days. For example, if an ASG contained 5 instances and all 5 instances utilized 100% CPU, then the CPU Total (%) will show 100%. If 1 instance utilized 100% CPU, while the other 4 instances utilized 0% CPU, then the CPU Total (%) will show 20%. Instance Count (red line) : The total number of instances running for this ASG in the indicated hour. Recommended (yellow dashed line) : The recommended normalized percentage of CPU utilization allocation for the entire ASG in the indicated hour. Recommended instance count (yellow line, displayed on hover) : The total number of instances recommended for this ASG in the indicated hour. |
| Network Total (Bits/s) | Network Total (blue line) : The total number of bits per second utilized based on the maximum instance count for the entire ASG in the indicated hour. Instance Count (red line) : The total number of instances running for this ASG in the indicated hour. Recommended (yellow dashed line) : The recommended network allocation for the entire ASG in the indicated hour. Recommended instance count (yellow line, displayed on hover) : The total number of instances recommended for this ASG in the indicated hour. |
| Memory Total (%) | Memory Total (blue line) : The normalized percentage of maximum memory utilization in the indicated hour, based on the maximum instance count for the entire ASG in the time window of 10 or 30 days. For example, if an ASG contained 5 instances and all 5 instances utilized 100% memory, then Memory Total (%) will show 100%. If 1 instance utilized 100% memory, while the other 4 instances utilized 0% memory, then Memory Total (%) will show 20%. Instance Count (red line) : The total number of instances running for this ASG in the indicated hour. Recommended (yellow dashed line) : The recommended normalized percentage of memory utilization allocation for the entire ASG in the indicated hour. Recommended instance count (yellow line, displayed on hover) : The total number of instances recommended for this ASG in the indicated hour. |
| GPU Total (%) | GPU Total (%): This is handled in the same manner as CPU Total (%) . |
| GPU Memory Total (%) | GPU Memory Total (%): This is handled in the same manner as CPU Memory Total (%) |

Disk metrics are not used for autoscaling recommendations.

---

## AWS ElasticIP

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > AWS ElasticIP
- **source_path:** SSVCLNQ/product/aws_elasticip.html
- **original_file:** rightsizing-aws-elasticip.md
- **images:**
  - 03-media/apptio-cloudability-standard/edit-icon.jpg

You can use Cloudability’s recommendations to identify unattached Amazon Web Services (AWS) ElasticIP addresses. The dashboard terminate recommendations for ElasticIP addresses determined to be unattached from an instance and unused. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

### Before you begin

To view the AWS EC2 EBS dashboard, make sure that you have connected Cloudability to the correct AWS accounts.

Connecting with AWS - Customer Integration Guide

### Accessing AWS Elastic IP Recommendations

To access the AWS EC2 EBS dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the AWS tab, and then select the Elastic IP subtab.

### Understanding your Recommendations

The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . As ElasticIP addresses do not support commitments, only the On Demand cost basis is available, which does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Account dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days. For an idle ElasticIP recommendation, the resource is recommended to be terminated if it is unattached for at least the last half of the lookback period.

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

1. Select the filter icon.
1. Select X next to the filter that you want to remove.

### Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current spend on the ElasticIP resources with recommendations
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsizing Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations. As Elastic IP addresses only support terminate recommendations, this is expected to show 0.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied. As Elastic IP addresses only support terminate recommendations, this is expected to show 0.

### Rightsizing Recommendations Table

The dashboard contains a rightsizing recommendations table, which provides an overview of your AWS ElasticIP resources. The table includes the following columns:

- Resource ID : The volume ID.
- Resource Name : The volume name.
- Account Name : The AWS account name.
- Idle : The percent of hours with zero IOPS.
- State : The state can be Attached , Unattached , or Deleted .
- Cost : The total cost of the volume.
- Type :The volume type.
- Size : The volume size (in GiB).
- New Type : The top recommended volume type.
- New Type : The top recommended volume type.
- New Size : The top recommended volume size (in GiB).
- Action : Recommendation for the resource, currently only terminate recommendations are available for ElasticIP addresses.

Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The EBS details panel shows the following information:

- Last Billing Date : The last date for which the cost data is available.
- Last Attached Date : The last date the volume state was attached.
- Last Attached ID : The last instance ID to which the volume was attached.
- Type : The volume type.
- Size : The volume size.
- Throughput : The maximum volume throughput.
- IOPS : The maximum volume IOPS.
- Risk (under recommendations) : Characterizes the likelihood to reach capacity limits for a given recommendation.
- Utilization Metrics : The utilization metrics displayed for EBS volumes are based on the following parameters.

---

## AWS Lambda

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > AWS Lambda
- **source_path:** SSVCLNQ/product/rightsizing-aws-lambda.html
- **original_file:** rightsizing-aws-lambda.md
- **images:** []

Use the Rightsizing dashboard to see resource optimization recommendations for Amazon Web Services (AWS) Lambda. The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Visit Rightsizing in Cloudability to learn more.

### Before you begin

- Enable the correct permissions which are: lambda:ListFunctions lambda:ListProvisionedConcurrencyConfigs
- Enable Lambda Insights enhanced monitoring. This allows Cloudability to retrieve memory metrics for your Lambda functions.
- Connect Cloudability to your correct AWS accounts.
- For customers with previously existing connections to AWS accounts: Create or download an updated AWS credential template in Cloudability and upload the new credential template to AWS Management Console.
- Visit the following pages to learn more: Enabling Lambda Insights Connect Amazon Web Services

### Explore the AWS Lambda dashboard

The dashboard contains a rightsizing recommendations table, which provides an overview of your Lambda resources. The table includes the following columns:

- Resource ID : The function ID.
- Resource Name : The function name.
- Account Name : The AWS account name.
- Last Ran : The date the function last ran.
- Cost : The total cost of the function.
- Current Memory : The amount of currently configured memory.
- New Memory : The top recommended configured memory.
- Cost Savings : The amount of cost savings identified.
- Action : Recommendation for the resource. The recommendation can be one of the following:

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New Memory column. |
| Terminate | Terminate your resource because it is predominantly idle. |
| No Action | No action is recommended by default.. However, additional recommendations with higher risk levels may be available in the Details panel. |

### Access the AWS Lambda dashboard

To access the AWS Lambda dashboard:

1. Open Cloudability. From the navigation menu, select Optimize > Rightsizing .
1. Select the AWS tab, then select the Lambda subtab.

### Customize the dashboard

You can set the following options to customize your dashboard:

1. Select Account : By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Select Account drop down menu.
1. Specify Timeline : You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days. For most users, 10 days is the recommended time period because it captures the most recent performance trends and is more predictive of future resource use.
1. Apply Filters : You can add filters to include or exclude data based on one or more conditions.

### Add filters with the filter option

To add a filter:

1. Select Add Filter from the toolbar.
1. In the Add Filter menu, choose a Dimension .
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

### Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter rule is automatically applied to the Filters field. You can select only one value or parameter from each column at a time.

### View recommendation details

To view the recommendation details for a particular resource, select the More Options (3 dots) menu and select View Details .

- To view descriptions of the cost dimensions and metrics, visit to Glossary of cost dimensions and metrics .
- To view details of the utilization dimension and metrics, visit to Glossary of utilization dimensions and metrics .

---

## AWS RDS

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > AWS RDS
- **source_path:** SSVCLNQ/product/rightsizing-for-aws-rds.html
- **original_file:** rightsizing-aws-rds.md
- **images:**
  - 03-media/apptio-cloudability-standard/aws-rds-dashboard.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/rightsizing-aws-rds.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Amazon Web Services (AWS) Relational Database Service (RDS). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Before you begin

To view the AWS RDS dashboard, make sure that you have connected Cloudability to the correct AWS accounts.

Connecting with AWS - Customer Integration Guide

Access the AWS RDS dashboard

To access the AWS RDS dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the AWS tab, and then select the RDS subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand or Effective . The On-Demand cost basis is selected by default.

If your organization has enabled Custom Pricing in Cloudability , the relevant custom rates will be applied to the cost basis calculations.

- On-Demand : The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.
- Effective : The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. In other words, the Effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended new instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures, if applicable.

Use the On-Demand cost basis if you are looking to remove the unpredictable nature of commitment-based discounts from your analysis and to maximize the number of recommendations provided to you. Use the Effective cost basis if you prefer to base your recommendations on the historical True Cost of running your instances and to take a conservative approach.

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

- Select the filter icon .
- Select X next to the filter that you want to remove.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of RDS resources for which recommendations have been identified. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Cluster ID : The cluster ID.
- Resource Name : The instance name.
- Engine : The database engine.
- Role : The IAM role.
- Account Name : The AWS account name.
- Idle : Based on the number of the active DB connections/sessions at a given point in time.
- Cost : The total cost of the instance.
- Current : The current instance type.
- New : The top recommended instance type.
- Action : Recommendation for the resource. The recommendation can be one of the following.

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New column. |
| Terminate | Terminate your resource because it is predominantly idle. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

---

## AWS S3

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > AWS S3
- **source_path:** SSVCLNQ/product/rightsizing-amazon-s3.html
- **original_file:** rightsizing-aws-s3.md
- **images:**
  - 03-media/apptio-cloudability-standard/s3-storage-classes.jpg
  - 03-media/apptio-cloudability-standard/s3-rightsizing-recommendations-grid.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/s3-rightsizing-details-pane.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Amazon Web Services (AWS)Simple Storage Service (S3). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

AWS S3 overview

Amazon Web Services (AWS) S3 is a storage service that is organized around buckets. The buckets are top-level containers. You can use these buckets to store individual objects that are associated with a storage class and also organize individual objects hierarchically within folders.

Buckets

You can have up to one thousand buckets per account. Within each bucket, you can store up to five terabytes of individual objects. Costs are incurred at the rate for the object’s storage class and factor by the allocated storage space (GB per month), duration, number of operations (read, write, lists, delete), and volume of data transferred (egress).

Storage Classes

Storage classes are tailored based on access patterns and durability needs, ranging from frequent to infrequent (archival) storage. Only an object, not a bucket, is associated with a storage class.

The AWS S3 storage classes differ in price, performance, availability, and minimum size and duration requirements. Depending on the storage class you use, addition fees can be incurred for monitoring, storage class transitioning, early delete, and restoration fees.

By default, S3 objects are created in the highest-priced Standard storage class. To manually optimize individual objects, you need to identify the rates for each storage class by region, collect the past access patterns and operations, then evaluate each of the alternatives considering all the trade-offs.

Before you begin

To view the AWS S3 dashboard, make sure that you have connected Cloudability to the correct AWS accounts.

Connecting with AWS - Customer Integration Guide

Access the AWS S3 dashboard

To access the AWS EC2 dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the AWS tab, and then select the S3 subtab.

Only buckets with incurred costs greater than zero will be displayed.

Each day Cloudability analyzes your AWS S3 cost, usage, and utilization metrics for the past 30 days. Rightsizing produces bucket-level insights and optimization recommendations. Spend is determined by GB Months.

Customize the dashboard

You can set the following options to customize your dashboard.

Only the On-Demand Cost Basis is supported for S3.

The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.

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
- Estimated Rightsizing Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your S3 resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Bucket Name : The S3 bucket name.
- Account Name : The AWS account name.
- Size : The size of all objects within the bucket.
- Objects : The number objects within the bucket.
- Requests : The number of requests (read, write, list) done via the console or API.
- Cost : The cost incurred for the past 30-days for the objects within the bucket.
- Current : The derived storage class for the bucket. When 100% of all objects are in the same storage class, that storage class will be displayed. If a bucket consists of objects within multiple storage classes, then MIXED will be displayed. Clicking the details will display the relative distribution across these classes.
- New : The recommended optimal storage class for all objects within the bucket.
- Action : Recommendation for the resource. The recommendation can be one of the following

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New column. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

The S3 details panel shows the following information:

Recommendations

Shows one or more recommendations, ranked by cost savings and risk (0-5).

- Savings: Estimated savings percent for the 10- or 30-day period.
- Cost Savings : Estimated savings amount.
- Storage Class : Recommended storage class.
- Action : Recommended action.
- Risk : On a scale of 0-5, the number of storage class transitions from frequent to infrequent access.

Charts

- Storage Size (Bytes) : Displays the storage size amount by storage class. The possible values include the following: Standard Intelligent FA (Intelligent Tiering - Frequent Access) Intelligent IA (Intelligent Tiering = Infrequent Access) Infrequent Access One Zone Glacier Deep Archive Reduced Redundancy
- Requests (Read/Write/Count) : Displays read and write requests performed against the bucket. This chart provides valuable insights into the usage category of the bucket such as mostly reads, balanced read-writes, or write oriented.
- Number of Objects (Count) : The graph shows the number of objects in the bucket over the time period.
- Data Transferred (Bytes) : Amount of egress to the internet (or data transferred across regions).
- Data Transitions (Bytes) : Amount of data transitioned across storage classes (excludes Standard).
- Early Deletion (Bytes) : Amount of storage incurring an early deletion fee.

Taking action on recommendations

Storage classes

To transition the storage class of objects in bulk, you have two options:

- Object Life Cycle Management You can enable a life cycle management rule at the bucket level to transition all contained objects to the recommended storage class based on the object creation date. For more information about object life cycle management, refer to Managing the lifecycle of objects .
- S3 Batch Operations If you prefer a programmatic route, you can leverage S3 Batch Operations to change the storage class of all or selected objects within one or more buckets. For more information about batch operations, refer to https://aws.amazon.com/blogs/aws/new-amazon-s3-batch-operations/ .

Intelligent Tiering

Intelligent Tiering is a hybrid storage class service that monitors each object’s access patterns and attributes. Based on this data, the service will automatically transition objects between the Standard and Infrequent Access storage class for a per-object monitoring fee in addition to the storage class-specific rates.

Bucket level rightsizing helps you to identify which buckets will benefit from this service. Although most objects are created in the Standard class initially, as your S3 buckets become optimized over time, additional incremental optimization recommendations such as Infrequent Access or even Glacier may be recommended.

For more information, refer to https://aws.amazon.com/s3/storage-classes/ .

---

## Azure Blob Storage

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Azure Blob Storage
- **source_path:** SSVCLNQ/product/rightsizing-for-azure-blob-storage.html
- **original_file:** rightsizing-azure-blob-storage.md
- **images:** []

You can use the Rightsizing dashboard to view optimization recommendations for Azure Blob Storage. The dashboard shows both rightsizing and idle recommendations, and you can view recommendations across multiple subscriptions from a single dashboard.

Rightsizing in Cloudability

Azure Blob Storage overview

Azure Blob Storage is Microsoft Azure's object storage solution, organized around containers. Containers are top-level entities within storage accounts. You can use containers to store blobs that are associated with an access tier and organize them hierarchically within virtual directories.

Containers

Within each container, you can store an unlimited number of blobs. Costs are based on the blob's access tier, allocated storage (GB per month), operations (read, write, list), retrieval operations for Cool, Cold, and Archive tiers, re-hydration operations for Archive, and data transfer volume (egress).

Access tiers

Access tiers are designed for different access patterns and durability needs, ranging from frequently accessed data to infrequently accessed archival storage. Blobs in the same container can be assigned to different access tiers.

Azure Blob Storage access tiers differ in price, performance, availability, and minimum storage duration requirements. Depending on the access tier, additional fees can apply for retrieval operations and for early deletion when blobs are deleted, overwritten, or moved before the minimum storage duration is met.

By default, Azure blobs are created in the Hot access tier. To manually optimize individual blobs, you must identify regional rates for each access tier, collect historical access patterns and operations data, and evaluate the trade-offs, including early deletion fees.

Before you begin

To view the Azure Blob Storage dashboard, make sure that you have connected Cloudability to the correct Azure subscriptions and have Azure Monitor and diagnostic settings configured.

Azure Monitor and diagnostic settings are required for Azure Blob Storage rightsizing recommendations. Last Access Time tracking must be explicitly enabled on storage accounts for access-pattern-based recommendations. For information about connecting Azure to Cloudability, see Connect with Microsoft Azure .

Access the Azure Blob Storage dashboard

To access the Azure Blob Storage dashboard, open the Cloudability home page. From the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the Azure tab, and then select the Blob Storage subtab.

Only containers with incurred costs greater than zero are displayed.

Each day, Cloudability analyzes your Azure Blob Storage cost, usage, and utilization metrics for the previous 30 days. Rightsizing produces container-level insights and optimization recommendations. Spend is determined by GB-months.

Idle resources or allocated storage volumes containing negligible or no data are also displayed in the Rightsizing dashboard.

Customize the dashboard

You can use the following options to customize your dashboard.

Select Subscription

By default, the dashboard shows recommendations for all subscriptions. To view recommendations for a particular subscription, select the subscription name from the Subscription dropdown.

Apply filters

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

To remove a filter: Select X next to the filter that you want to remove.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your Azure Blob Storage resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Container Name : The Azure Blob Storage container name.
- Storage Account Name : The Azure storage account name.
- Resource Group : The Azure resource group that contains the storage account.
- Subscription : The Azure subscription identifier.
- Size : The size of all blobs within the container.
- Blobs : The number of blobs within the container.
- Operations : The number of operations (read, write, list) performed by using the portal or API.
- Cost : The cost incurred during the previous 30 days for the blobs in the container.
- Current : The derived access tier for the container. If 100% of blobs are in the same access tier, that tier is displayed. If a container contains blobs in multiple access tiers, MIXED is displayed. Select the details to view the relative distribution across these tiers.
- New : The recommended optimal access tier for all blobs within the container.
- Action : The recommendation for the resource. The recommendation can be one of the following:

| Recommendation | Description |
| --- | --- |
| Rightsize | Move to the access tier specified in the New column. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels might be available in the details panel. |

Export recommendations to an Excel file

To export recommendations to an Excel file, select Export . The Excel file includes additional columns such as region, location, and confidence score.

Recommendation details

To view recommendation details for a resource, select View Details from the More Options menu.

The Azure Blob Storage details panel shows the following information:

Recommendations

One or more recommendations are shown, ranked by cost savings and risk (0-5).

- Savings: Estimated savings percent for the 30-day period.
- Cost Savings : Estimated savings amount (net of early deletion fees).
- Access Tier : Recommended access tier.
- Action : Recommended action.
- Risk : On a scale of 0-5, the number of access tier transitions from frequent to infrequent access.
- Payback Period : Time to recover early deletion fees (if applicable).
- Confidence Score : Recommendation confidence (0-100%) based on data completeness and Last Access Time availability.

Charts

- Storage Size (GB) : Displays the storage size amount by access tier. The possible values include the following: Hot Cool Cold Archive Smart Tier
- Operations (Read/Write Operations Count) : Displays the count of read and write operations performed against the container. This chart provides valuable insights into the usage category of the container such as mostly reads, balanced read-writes, or write oriented.
- Number of Blobs (Count) : The graph shows the number of blobs in the container over the time period.
- Data Transferred (GB) : Amount of egress to the internet (or data transferred across regions).
- Retrieval Volume (GB) : Amount of data retrieved from Cool, Cold, or Archive tiers.
- Rehydration Events (Count) : Number of Archive tier rehydration operations by priority (Standard/High).
- Early Deletion (GB/Month) : Amount of data deleted from tiers where there is a minimum retention period.

Taking action on recommendations

Access tiers

To transition the access tier of blobs or configure container-level storage optimization, you have several options:

- Lifecycle Management You can configure lifecycle management rules at the storage account level to automatically transition blobs to the recommended access tier based on blob age, last modified time, or other conditions. For more information about lifecycle management, see Azure Blob Storage lifecycle management .
- Smart Tier Enable Smart Tier on containers to automatically transition blobs between Hot, Cool, and Cold access tiers based on access patterns, eliminating the need for manual lifecycle rules. For more information about Smart Tier, see Azure Blob Storage access tiers .

Understanding Smart Tier

Smart Tier is a container-level feature that automatically transitions blobs between access tiers based on access patterns. When enabled, Smart Tier monitors each blob's access patterns and automatically moves blobs between Hot, Cool, and Cold access tiers for a monitoring fee in addition to the tier-specific rates.

Container-level rightsizing helps you identify which containers can benefit from this feature. New blobs start in the Hot tier. Smart Tier automatically moves them to the Cool tier after 30 days of inactivity and to the Cold tier after 90 days of inactivity. Accessing a blob moves it back to the Hot tier and resets the cycle.

Smart Tier does not support the Archive tier. For long-term archival data, use manual tier selection or lifecycle policies. Blobs smaller than 128 KiB remain in the Hot tier and are exempt from monitoring fees.

Smart Tier charges a monitoring fee of $0.04 per 10,000 blobs per month for blobs larger than 128 KiB. There are no early deletion fees or retrieval charges for Smart Tier transitions. All access operations are billed at Hot tier pricing.

For more information, see Smart tiering for Azure Blob Storage .

Understanding early deletion fees

Azure Blob Storage charges early deletion fees when blobs are deleted, overwritten, or moved before the minimum storage duration is met for Cool (30 days), Cold (90 days), or Archive (180 days) tiers. These fees are prorated based on the remaining days in the minimum duration period.

Cloudability recommendations account for early deletion fees when calculating projected savings and payback periods. Recommendations with significant early deletion fees display a payback period, which indicates how long it takes to recover the one-time costs through ongoing savings.

For more information about early deletion fees, see Azure Blob Storage access tiers .

Last Access Time tracking

Last Access Time tracking must be explicitly enabled on Azure storage accounts to provide access-pattern-based recommendations. When Last Access Time is unavailable, Cloudability uses last modified time for time-based analysis that is similar to lifecycle policies, but the resulting recommendations are less accurate.

Recommendations that are based on last modified time have lower confidence scores (70-89%) than recommendations that are based on Last Access Time (90-100%). The recommendation details indicate whether Last Access Time tracking is enabled.

For more information about enabling Last Access Time, see Move data based on last accessed time .

---

## Azure Compute

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Azure Compute
- **source_path:** SSVCLNQ/product/rightsizing-for-azure-compute.html
- **original_file:** rightsizing-azure-compute.md
- **images:**
  - 03-media/apptio-cloudability-standard/azure-compute-1.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/azure-compute-2.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Microsoft Azure Compute. The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Before you begin

To view the Azure Compute dashboard, make sure that you have connected Cloudability to the correct Azure accounts.

Connect Microsoft Azure

Access the Azure Compute dashboard

To access the Azure Compute dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the Azure tab, and then select the Compute subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand or Effective . The On-Demand cost basis is selected by default.

If your organization has enabled Custom Pricing in Cloudability , the relevant custom rates will be applied to the cost basis calculations.

- On-Demand : The On-Demand cost basis provides a direct comparison between the instance listed in the Curren t column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability
- Effective : The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. In other words, the Effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended new instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures, if applicable.

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

The dashboard contains a rightsizing recommendations table, which provides an overview of Compute resources for which recommendations have been identified. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource Name : The Compute resource name.
- Account Name : The Compute account name.
- Resource Group : The Compute resource group.
- Data Source : The Compute data source.
- Idle : The time spent below 2% CPU on a scale of 1-100.
- Cost: The total cost of all running instances in Compute.
- Current : The current Compute instance type.
- New : The top recommended Compute instance type.
- Action : Recommendation for the resource. The recommendation can be one of the following

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New column. |
| Terminate | Terminate your resource because it is predominantly idle. |
| Autoscale | Set up autoscaling for the resource. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

---

## Azure Compute Scale Sets

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Azure Compute Scale Sets
- **source_path:** SSVCLNQ/product/azure_compute_scale_sets.html
- **original_file:** rightsizing-azure-compute-scale-sets.md
- **images:**
  - 03-media/apptio-cloudability-standard/edit-icon.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Microsoft Azure Compute managed via Scale Sets. The dashboard shows rightsizing and idle (terminate) recommendations for both homogenous and heterogenous Scale Sets. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

### Before you begin

To view the Azure Compute dashboard, make sure that you have connected Cloudability to the correct Azure accounts.

Connect Microsoft Azure

### Access the Azure Compute Dashboard

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

### Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

### Rightsizing recommendations table

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

---

## Azure Disk

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Azure Disk
- **source_path:** SSVCLNQ/product/rightsizing-for-azure-disks.html
- **original_file:** rightsizing-azure-disk.md
- **images:**
  - 03-media/apptio-cloudability-standard/azure-disk-1.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/azure-disk-2.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Azure Disk. The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Before you begin

To view the Azure Disk dashboard, make sure that you have connected Cloudability to the correct Azure accounts.

Connect Microsoft Azure

Access the Azure Disk dashboard

To access the Azure Disk dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the Azure tab, and then select the Disk subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

Only the On-Demand Cost Basis is supported for Disk.

The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.

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

1. Select the filter icon
1. Select X next to the filter that you want to remove.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your Azure Disk resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource Name : The disk resource name
- Account Name : The Azure account name.
- Resource Group : The resource group which the volume belongs to.
- Idle : The percent of hours with zero IOPS.
- State : The disk state.
- Cost : The total cost of thedisk resource for the selected timeline.
- Type : The current disk resource type.
- Size : The resource size (in GiB).
- New Type : The top recommended disk resource type.
- New Size : The top recommended disk resource size (in GiB).
- Action : Recommendation for the resource. The recommendation can be one of the following. Recommendation Description Rightsize Resize to the resource type specified in the New column. Terminate Terminate your resource because it is predominantly idle. No Action No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel.
- Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

---

## Azure SQL

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Azure SQL
- **source_path:** SSVCLNQ/product/rightsizing-for-azure-sql.html
- **original_file:** rightsizing-azure-sql.md
- **images:**
  - 03-media/apptio-cloudability-standard/azure-sql-1.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/azure-sql-2.jpg

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

---

## GCP Google Cloud Storage (GCS)

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > GCP Google Cloud Storage (GCS)
- **source_path:** SSVCLNQ/product/rightsizing-for-gcp-cloud-storage.html
- **original_file:** rightsizing-gcp-google-cloud-storage-gcs.md
- **images:** []

You can use the Rightsizing dashboard to view the resource optimization recommendations for Google Cloud Storage (GCS). The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Rightsizing in Cloudability

Google Cloud Storage overview

Google Cloud Storage (GCS) is a storage service that is organized around buckets. The buckets are top-level containers. You can use these buckets to store individual objects that are associated with a storage class and also organize individual objects hierarchically within folders.

Buckets

Within each bucket, you can store unlimited individual objects. Costs are incurred at the rate for the object's storage class and factor by the allocated storage space (GB per month), number of operations (read, write, list), retrieval operations (for Nearline, Coldline, and Archive), and volume of data transferred (egress).

Storage Classes

Storage classes are tailored based on access patterns and durability needs, ranging from frequent to infrequent (archival) storage. Only an object, not a bucket, is associated with a storage class.

The GCS storage classes differ in price, performance, availability, and minimum storage duration requirements. Depending on the storage class you use, additional fees can be incurred for retrieval operations (accessing data from Nearline, Coldline, or Archive classes).

By default, GCS objects are created in the Standard storage class. To manually optimize individual objects, you need to identify the rates for each storage class by location, collect the past access patterns and operations, then evaluate each of the alternatives considering all the trade-offs.

Before you begin

To view the GCS dashboard, make sure that you have connected Cloudability to the correct GCP accounts and have Resource Level Billing (RLB) enabled.

Detailed Billing (also known as Resource Level Billing) is required for GCS rightsizing recommendations. For information about enabling Detailed Billing in your GCP configuration, see Connect with Google Cloud .

Access the Google Cloud Storage dashboard

To access the GCS dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the GCP tab, and then select the GCS subtab.

Only buckets with incurred costs greater than zero will be displayed.

Each day Cloudability analyzes your GCS cost, usage, and utilization metrics for the past 30 days. Rightsizing produces bucket-level insights and optimization recommendations. Spend is determined by GB Months.

Customize the dashboard

You can set the following options to customize your dashboard.

Select Account

By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Account dropdown.

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

To remove a filter: Select X next to the filter that you want to remove.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your GCS resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Bucket Name : The GCS bucket name.
- Account Name : The GCP account name.
- Size : The size of all objects within the bucket.
- Objects : The number objects within the bucket.
- Requests : The number of requests (read, write, list) done via the console or API.
- Cost : The cost incurred for the past 30-days for the objects within the bucket.
- Current : The derived storage class for the bucket. When 100% of all objects are in the same storage class, that storage class will be displayed. If a bucket consists of objects within multiple storage classes, then MIXED will be displayed. Clicking the details will display the relative distribution across these classes.
- New : The recommended optimal storage class for all objects within the bucket.
- Action : Recommendation for the resource. The recommendation can be one of the following

| Recommendation | Description |
| --- | --- |
| Rightsize | Resize to the resource type specified in the New column. |
| No Action | No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel. |

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, location type, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The GCS details panel shows the following information:

Recommendations

Shows one or more recommendations, ranked by cost savings and risk (0-5).

- Savings: Estimated savings percent for the 10- or 30-day period.
- Cost Savings : Estimated savings amount.
- Storage Class : Recommended storage class.
- Action : Recommended action.
- Risk : On a scale of 0-5, the number of storage class transitions from frequent to infrequent access.

Charts

- Storage Size (Bytes) : Displays the storage size amount by storage class. The possible values include the following: Standard Nearline Coldline Archive Autoclass
- Operations (Class B/ Class A Operations Count) : Displays the count of Class A and Class B Operations performed against the bucket. This chart provides valuable insights into the usage category of the bucket such as mostly reads, balanced read-writes, or write oriented.
- Number of Objects (Count) : The graph shows the number of objects in the bucket over the time period.
- Data Transferred (Bytes) : Amount of egress to the internet (or data transferred across regions).
- Data Transitioned (Bytes) : Amount of ingress data from the internet (or data transferred across regions).
- Earyl Deletion (Bytes/Month) : Amount of data deleted from tiers where there is a minimum retention period.

Taking action on recommendations

Storage classes

To transition the storage class of objects or configure bucket-level storage optimization, you have several options:

- Object Lifecycle Management You can configure lifecycle management rules at the bucket level to automatically transition objects to the recommended storage class based on object age, creation date, or other conditions. For more information about object lifecycle management, refer to https://cloud.google.com/storage/docs/lifecycle .
- Autoclass Enable Autoclass on buckets to automatically transition objects between storage classes based on access patterns, eliminating the need for manual lifecycle rules. For more information about Autoclass, refer to https://cloud.google.com/storage/docs/autoclass .

Understanding Autoclass

Autoclass is a bucket-level feature that automatically transitions objects between storage classes based on access patterns. When enabled, Autoclass monitors each object's access patterns and automatically moves objects between Standard, Nearline, Coldline, and Archive storage classes for a per-object monitoring fee in addition to the storage class-specific rates.

Bucket level rightsizing helps you to identify which buckets will benefit from this feature. Although most objects are created in the Standard class initially, as your GCS buckets become optimized over time, additional incremental optimization recommendations such as Nearline, Coldline, or even Archive may be recommended.

For more information, refer to https://docs.cloud.google.com/storage/docs/autoclass .

---

## GCP Google Compute Engine (GCE)

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > GCP Google Compute Engine (GCE)
- **source_path:** SSVCLNQ/product/rightsizing-for-gce.html
- **original_file:** rightsizing-gcp-google-compute-engine-gce.md
- **images:**
  - 03-media/apptio-cloudability-standard/edit-icon.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Google Compute Engine (GCE) virtual machine resources. The dashboard shows both the rightsizing and idle (terminate) recommendations.

Rightsizing in Cloudability

Before you begin

To view the GCE dashboard, make sure that the following requirements are met:

Enable the correct permissions. Navigate to Settings > Vendor Credentials > GCP , and ensure that the Advanced Features column has a green check mark for each project.

Install the Cloud Monitoring agent to improve the quality of recommendations. This is optional but recommended.

Access the GCE dashboard

To access the GCE dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the GCP tab, and the select the GCE sub tab to view recommendations for Google Compute Engine.

Customize the dashboard

You can set the following options to customize your dashboard.

Specify Cost Basis

Cost Basis determines how recommendations are calculated. Cost basis can be On-Demand or Effective . The On-Demand cost basis is selected by default.

If your organization has enabled Custom Pricing in Cloudability , the relevant custom rates will be applied to the cost basis calculations.

- On-Demand : The On-Demand cost basis provides a direct comparison between the instance listed in the Current column and the instance recommended in the New column based purely on On-Demand Pricing . It does not include any potential impact from Reserved Instances (RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing agreements that you have configured in Cloudability.
- Effective : The Effective cost basis takes into account the historical impact of Reserved Instances (RIs) and Savings Plans (SPs) to calculate the cost for the current instance type over the reporting period. Like the Cost (Amortized) metric, it includes all associated upfront and recurring costs. In other words, the Effective cost basis shows the effective cost of running your current instance. The cost figures for the recommended new instance type are based on the on-demand prices. This is because the new configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures, if applicable.

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

The dashboard contains a rightsizing recommendations table, which provides an overview of your GCE resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource Name : The GCE resource name.
- Account Name : The GCE account name.
- Region : The GCE region
- Data Source : The GCE data source.
- Idle : The time spent below 2% CPU on a scale of 1-100.
- Cost : The total cost of the GCE resource for the selected timeline.
- Current :The current GCE resource type.
- Current :The current GCE resource type.
- New : The top recommended GCE resource type.
- Action : Recommendation for the resource. The recommendation can be one of the following. Recommendation Description Rightsize Resize to the resource type specified in the New column. Terminate Terminate your resource because it is predominantly idle.
- Cost Savings : The estimated 10- or 30-day cost savings amount.

.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns, such as region, operating system, unit price, and others.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

The following figure shows a sample recommendation details panel.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

---

## GCP Google Compute Engine (GCE) Managed Instance Groups (MIG)

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > GCP Google Compute Engine (GCE) Managed Instance Groups (MIG)
- **source_path:** SSVCLNQ/product/rightsizing-for-gcp-gce-mig.html
- **original_file:** rightsizing-gcp-google-compute-engine-gce-managed-instance-groups-mig.md
- **images:**
  - 03-media/apptio-cloudability-standard/mig-help-image-2.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/mig-help-image2.jpg

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

---

## GCP Google Persistent Disk (GPD)

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > GCP Google Persistent Disk (GPD)
- **source_path:** SSVCLNQ/product/rightsizing-for-gpd.html
- **original_file:** rightsizing-gcp-google-persistent-disk-gpd.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing-gcp-gpd.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/rightsizing-gcp-gpd-details.jpg

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

---

## OCI Virtual Machines (VMs)

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > OCI Virtual Machines (VMs)
- **source_path:** SSVCLNQ/product/rightsizing-for-oci-vms.html
- **original_file:** rightsizing-oci-virtual-machines-vms.md
- **images:**
  - 03-media/apptio-cloudability-standard/oci-vm-dashboard.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg

You can use the Rightsizing dashboard to view the resource optimization recommendations for Oracle Cloud Infrastructure (OCI) Virtual Machine (VM) resources. The dashboard shows both the rightsizing and idle (terminate) recommendations.

Rightsizing in Cloudability

Before you begin

To view the OCI VM dashboard, make sure that you have connected Cloudability to the correct OCI tenancies. You need to validate credentials for both the parent tenancies and the child tenancies.

Connect Oracle Cloud

Access the OCI VM dashboard

To access the OCI Virtual Machine dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . On the Rightsizing page, select the OCI tab, and then select the VM subtab.

Customize the dashboard

You can set the following options to customize your dashboard.

All costs for VMs are currently shown only using the On-Demand Cost Basis.

Select Account

By By default, the dashboard shows recommendations for all accounts/tenancies. To view recommendations for a particular account, select the account name from the Account dropdown.

Specify Timeline

You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days. For most users, 10 days is the recommended time period because it captures the most recent performance trends and is more predictive of future resource use.

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

Apply Options

You can also set page-level options to include or exclude certain recommendations.

Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- Total Spend : Shows the total current allocated spend.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : Shows the estimated total spend after recommendations are applied.

Rightsizing recommendations table

The dashboard contains a rightsizing recommendations table, which provides an overview of your VM resources. The table includes the following columns:

By default, the data is sorted by the Cost Savings column. To change the sort order, just select the column name.

- Resource ID : The VM resource ID.
- Resource Name : The VM resource name.
- Account Name : The VM account name.
- Data Source : The VM data source
- Idle : The time spent below 2% CPU on a scale of 1-100.
- Cost : The total cost of the VM resource for the selected timeline.
- Current :The current VM resource type.
- New : The top recommended VM resource type
- Action : Recommendation for the resource. The recommendation can be one of the following. Recommendation Description Rightsize Resize to the resource type specified in the New column. Terminate Terminate your resource because it is predominantly idle. No Action No action is recommended by default, but additional recommendations with higher risk levels may be available in the Details panel.
- Cost Savings : The estimated 10- or 30-day cost savings amount.

Export recommendations to an Excel file

To export the recommendations to an excel file, select Export . Note that the excel file will include several additional columns and data.

Recommendation details

To view the recommendation details for a particular resource, select View Details from the More Options (3 dots) menu.

To view descriptions of the cost dimensions and metrics, refer to Glossary of cost dimensions and metrics .

To view details of the utilization dimension and metrics, refer to Glossary of utilization dimensions and metrics .

---

## Rightsizing Explorer

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Rightsizing Explorer
- **source_path:** SSVCLNQ/product/rightsizing-explorer.html
- **original_file:** rightsizing-explorer.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing-explorer-with-effective-cost.jpg
  - 03-media/apptio-cloudability-standard/download_button.jpg

Rightsizing Explorer dashboard enables you to group, filter and navigate all of your rightsizing recommendations, allowing you to better understand your opportunities and focus your efforts to maximize returns.

The Rightsizing Explorer is in Optimize > Rightsizing > Explorer , and it is the default page for Rightsizing.

Rightsizing preferences are applied when recommendations are generated. The Rightsizing Explorer works with the recommendations after they are generated. Due to grouping, Cloudability recommend that you adjust your minimum savings amount to a lower setting if you are using the Rightsizing Explorer.

Supported services

The services that are currently supported are:

- AWS: EC2, EBS, S3, RDS, Lambda Note: Cloudability only generates 30 day recommendations for AWS S3. When a 10day timeframe is selected in the Rightsizing Explorer – 30 day recommendations for S3 are displayed.
- Azure: Compute, Disk, SQL
- GCP: GCE, GPD
- OCI: VM

Navigate the Rightsizing Explorer

The most efficient way to use the Rightsizing Explorer is to filter first, find, and then focus:

1. Apply filters to remove the largest amount of results first, such as Accounts, Vendors, Services. You can select Sankey nodes to quickly add filters
1. Remove any unnecessary dimensions from the menu. Add additional dimensions one-at-a-time to go deeper and discover additional trends.
1. Select a node to view the individual recommendations matching the node attributes.
1. Filter the table further by selecting specific values in the columns.

Dimensions

Dimensions are used in the Sankey diagram to split and group your rightsizing recommendations. When you add a dimension to the Sankey diagram, it creates a set of nodes with the values of that dimension. The size of the node corresponds to the total amount of savings from individual recommendations with that dimensions value.

Dimensions are set though the menu bar at the top of the Sankey diagram.

- Add: Select Edit Dimensions and use the checkbox next to the required dimension to add. For performance, Cloudability recommend that you do not add multiple dimensions too quickly because you may hit rate limiting.
- Remove: Select Edit Dimensions and use the checkbox next to the required dimension, or select the delete button next to the dimension.
- Re-order: The order of dimensions can be changed on the Sankey diagram by changing the order in the menu. Select and hold the dots next to the dimension name, then drag it to the new position.

Learn about Glossary of cost dimensions and metrics

Learn about

Glossary of utilization dimensions and metrics

Recommendations

View recommendations

When you want to focus on a specific node and see the individual recommendations for that dimension:

1. Select the node on the Sankey diagram.
1. Select View recommendations . The recommendations table is shown below the Sankey diagram, listing the recommendations for the node that you selected. To download a copy of this data, select .

Configure the table

- To order the columns in the table as required, select and hold on the column title then drag it to the desired location.
- To sort the data based on a column, select the column header.

1. Select the three dots to the right of the recommendation
1. Select either Open Details or Create Ticket .

You can view the details of recommendations and create tickets to action them.

Use Case

A customer using many Windows instances has a large number of disk rightsizing recommendations. They are all small savings and it would not make sense to rightsize any of them individually. Grouping the results by disk size reveals that they are all exactly 100 gigabytes which is the default boot volume. The customer makes one change to their boot image and receives the benefits over time. By changing the default template to a lower size, all newly built environments have no recommendations.

Rightsizing FAQ

Why are Spot Instances excluded from rightsizing recommendations?

Our rightsizing engine takes into account your workload (utilization metrics) and the cost to run it (current instance type and on-demand price) and generates a list of recommendations from which you can choose to help save you money. Spot Instances, on the other hand, are already offered at steep discounts; applying rightsizing in these situations results in negligible savings. For this reason, we have chosen to exclude Spot Instances from rightsizing.

How frequently are recommendations updated?

We update our rightsizing recommendations daily. You can access recommendations for resources 24 hours after the resource is created, provided that there is enough utilization data.

---

## Rightsizing for Kubernetes Containers

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Rightsizing for Kubernetes Containers
- **source_path:** SSVCLNQ/product/k8s-container-rightsizing.html
- **original_file:** rightsizing-kubernetes-containers.md
- **images:**
  - 03-media/apptio-cloudability-standard/kubernetes-rightsizing-dash-new.png
  - 03-media/apptio-cloudability-standard/edit-icon.jpg
  - 03-media/apptio-cloudability-standard/containers-summary-kpis.jpg
  - 03-media/apptio-cloudability-standard/cloudy-vertical-elipsis.jpg
  - 03-media/apptio-cloudability-standard/rightsizing-recommendation-detail.jpg

With Cloudability rightsizing for Kubernetes containers, you can view recommendations for optimizing your Kubernetes container deployments based on the previous 10 or 30 days of resource usage.

Learn about Rightsizing in Cloudability

Learn about Cloudability Container Cost Allocation

Visit the blog to learn about using 10 or 30 days of resource usage to generate recommendations.

Before you begin

To use Rightsizing for GCP, make sure you have:

- Provisioned your Kubernetes clusters by deploying the opensource agent.

Learn about Kubernetes cluster provisioning

Accessing the Containers dashboard

From the Cloudability home menu, navigate to Optimize > Rightsizing > Containers .

You can select Workloads or the Clusters toggle to choose the type of recommendations.

Your resources are sorted by cost savings by default. The resources at the top of the list have the highest potential savings.

Select Export to download the recommendations as a spreadsheet. Additional account information is included such as region, operating system, tags available per resource, and the Effective Rate for current and new resource types.

The dashboard displays the following:

Cost basis

- On-Demand : Savings values based purely on on-demand pricing. While custom pricing is included, the potential impact from commitments (Reserved Instances (RIs) or Savings Plans (SPs)) is not included.
- Effective : The effective cost of running your current configuration. This takes into account the historical impact of commitments in a similar manner to the Cost (Amortized) metric, where all associated upfront and recurring costs are included. For the recommended New instance type, cost figures are based on the on-demand prices because the New configuration may not benefit from RIs or SPs. This comparison is the more conservative option. Even if you inadvertently move away from RIs or SPs, your new overall rate will still be better. As a result, the overall savings reported using this methodology will sometimes be lower. Custom pricing will be applied to these figures if applicable.

Filters

As with the container cost allocation functionality, you can leverage account-based views to filter recommendations down to a subset of your organization's accounts.

To add a filter:

1. Select Add Filter from the toolbar.
1. In the filter overlay choose a Dimension.
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

To remove a filter:

1. Select the filter icon .
1. Select X next to the filter that you want to remove.

Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. Your filters are added to the Filter Configurator.

Only one value or parameter from each column can be selected at a time.

KPIs

Summary Key Performance Indicators (KPIs) are displayed depending on the views and filters you have selected.

Summary KPIs include:

- Total Spend : The total current allocated spend across all containers instrumented in the Cloudability platform.
- Estimated Idle Savings : Shows the estimated total savings for all Terminate recommendations.
- Estimated Rightsize Savings : Shows the estimated total potential savings achievable for all Rightsize recommendations.
- Estimated Optimized Spend : The estimated total spend across all displayed containers after recommendations are applied.

Rightsizing containers adjusts the cost allocation for the containers and pods with that container specification but ordinarily does not affect your bill. Rightsizing the container specification makes capacity available in your deployment, which organizations can either use for other workloads or to rightsize the underlying compute instance. Rightsizing the underlying compute instance will have a positive impact on an organization's bill.

Viewing recommendation details

To view the details for a particular resource, select > View Details .

Within the Details pane, Cloudability displays at least one recommendation, with the lowest risk option being the default selection.

Each option includes request and limit recommendations for memory and CPU for a given container specification. Graphs for individual resources display the current resource allocation (in red) and consumption (in blue) along with the recommended settings (in yellow).

---

## Rightsizing Preferences

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Rightsizing Preferences
- **source_path:** SSVCLNQ/product/rightsizing-preferences.html
- **original_file:** rightsizing-preferences.md
- **images:**
  - 03-media/apptio-cloudability-standard/preferences-screenshot_VM.jpg
  - 03-media/apptio-cloudability-standard/preferences-screenshot_S3.jpg

Navigate to Settings > Rightsizing Preferences .

Compute (VM) Preference

This preference tab allows you to set up global preferences for rightsizing recommendations.

| Field Name | Description |
| --- | --- |
| Generations and Instances | Options for excluding non-current instance types or to recommend only within existing instance family (e.g. to ensure continued coverage with existing commitments / reservations) when generating rightsizing recommendations. |
| Processor Architecture | Choose to exclude specific processor types from rightsizing recommendations and allow cross -architecture recommendations. Ensure workload compatibility before switching the processor type. |
| Capacity Reduction | Options for including recommendations that would result in a reduction in resource capacity (e.g. reducing total available memory) if utilization metrics for the dimension are not provided. |
| Cost Saving Threshold | Optional setting for determining the minimum savings recommendations must be predicted to achieve in order to be included in those displayed. Minimum 30-Day Savings Amount - A value of zero indicates the setting will be ignored. |
| Resource Lifespan | Optional setting for eliminating recommendations for the resources that have been inactive for a specified period of time. A value of zero indicates the setting will be ignored. |

Enter data in the appropriate fields and select the Save button. The message Successfully saved preferences appears.

Multiple ways to filter rightsizing recommendations

In Cloudability, there are many ways to filter rightsizing recommendations. First, you can filter the recommendations by using the global preferences available under Settings > Rightsizing Preferences page. Another way to filter using the options available on the rightsizing pages themselves under Optimize > Rightsizing. There are additional filtering options provided in the 'details' pane for the recommendations themselves.

Object Storage (S3) Preferences

This preference tab allows you to exclude specific classes for Object Storage for Rightsizing Recommendations.

1. select "Add Value" button.
1. Add a value (storage class) to the input field
1. Continue to add as may values to exclude as needed

- Standard
- Intelligent Tiering
- Standard Infrequent Access
- Once Zone Infrequent Access
- Glacier Instant Retrieval
- Glacier Flexible Retrieval
- Glacier Deep Archive

---

## Snoozing Rightsizing Recommendations

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing > Snoozing Rightsizing Recommendations
- **source_path:** SSVCLNQ/product/rightsizing-snoozing-recommendations.html
- **original_file:** rightsizing-snoozing-recommendations.md
- **images:**
  - 03-media/apptio-cloudability-standard/snooze_rs1.jpg
  - 03-media/apptio-cloudability-standard/snooze_rs2.jpg
  - 03-media/apptio-cloudability-standard/snooze_rs3.jpg
  - 03-media/apptio-cloudability-standard/snooze_rs4.jpg
  - 03-media/apptio-cloudability-standard/snooze_rs5.jpg

If needed, you can snooze rightsizing recommendations for specific resources when it has been determined that no action is to be taken on the resource at this time. This can help enhance efficiency when reviewing and actioning rightsizing recommendations by hiding these recommendations.

Before you begin

In order to snooze rightsizing recommendations, you’ll need the proper administrative permissions.

Roles and permissions in Cloudability

Access the Rightsizing dashboard

To access the Rightsizing dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Rightsizing . The Rightsizing dashboard displays the Explorer tab by default, however snoozing capabilities are available for services under the vendor tabs as well.

Snoozing recommendations

To start snoozing recommendations, click Snooze Mode toggle in the upper right corner of the Rightsizing page to turn on Snooze Mode.

Once the snooze mode is enabled, multiple methods will be available to snooze recommendations.

Method (bulk)

1. here will now be a Snooze All button in the upper right corner of the recommendations table.
1. The recommendations table will now also show an additional column (containing checkboxes) as the first column in the table.
1. To snooze recommendations, either: Click Snooze All button to snooze all recommendations for the resources in the table. Check the checkbox of the recommendations you wish to snooze and click Snooze Selected (x) button to snooze just the recommendations for the selected resources.
1. A modal will appear allowing you to choose a duration for how long the recommendations will be snoozed. Click Submit to snooze the recommendations or Cancel to cancel out.

Method (individual)

1. Click ellipses for a recommendation to open the recommendation sub-menu.
1. To snooze recommendations, either: Click Snooze sub-menu item. Click View Details sub-menu item and at the top of the Details Pane in the upper right corner, click Snooze icon.
1. A modal will appear allowing you to choose a duration for how long the recommendation will be snoozed. Click Submit to snooze the recommendations or Cancel to cancel out.

Un-snoozing recommendations

To un-snooze recommendations:

1. Click Options dropdown menu at the top of the Rightsizing page and select Show Snoozed Resources .
1. The recommendations table will now display the recommendations that are currently snoozed. .
1. To un-snooze recommendations for a resource, follow the same processes used to snooze recommendations: Click Un-Snooze All button to un-snooze all recommendations for the resources in the table. Check the checkbox of the recommendations you wish to un-snooze, and click on the Un-Snooze Selected (x) button that appears to un-snooze just the recommendations for the selected resources. Click ellipses for a snoozed recommendation to open the recommendation sub-menu, and click Un-snooze option to un-snooze the recommendations. Click ellipses for a snoozed recommendation to open the recommendation sub-menu, click View Details sub-menu item, and at the top of the Details Pane in the upper right corner, click Un-snooze icon.

Editing the duration of snoozed recommendations

To edit the duration of snoozed recommendations:

1. Click Options dropdown menu at the top of the Rightsizing page, and select Show Snoozed Recommendations
1. The recommendations table will now display the recommendations that are currently snoozed.
1. Click ellipses for a snoozed recommendation to open the recommendation sub-menu.
1. In the sub-menu, select the option to Edit Snooze (editing a snooze duration can also be done from the Details Pane with the edit snooze icon in the upper right corner).
1. A modal will appear allowing you to choose a duration for how long the recommendation will be snoozed. Click Submit to snooze the recommendations or Cancel to cancel out.

---
