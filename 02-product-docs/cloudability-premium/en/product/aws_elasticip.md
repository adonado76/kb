---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "AWS ElasticIP"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Rightsizing in Cloudability Premium"
  - "Rightsizing"
source_path: "product/aws_elasticip.html"
images:
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS ElasticIP

You can use Cloudability’s recommendations to identify unattached Amazon Web Services (AWS)
ElasticIP addresses. The dashboard terminate recommendations for ElasticIP addresses determined to
be unattached from an instance and unused. You can view the recommendations across multiple accounts
from a single dashboard.

[Rightsizing in Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

## Before you begin

To view the AWS EC2 EBS dashboard, make sure that you have connected Cloudability to the correct
AWS accounts.

[Connecting with AWS - Customer Integration Guide](../admin/aws-credentialing-standard-enterprise-home.dita "(Opens in a new tab or window)")

## Accessing AWS Elastic IP Recommendations

To access the AWS EC2 EBS dashboard, open the Cloudability home page, and from the left
navigation menu, select **Optimize** >**Rightsizing**. On the **Rightsizing** page, select
the **AWS** tab, and then select the**Elastic IP** subtab.

## Understanding your Recommendations

Note: Only the On-Demand Cost Basis is supported for ElasticIP Addresses.

The On-Demand cost basis provides a direct comparison between the instance listed in
the **Current** column and the instance recommended in the **New** column based purely
on **On-Demand****Pricing**. As ElasticIP addresses do not support commitments, only the On
Demand cost basis is available, which does not include any potential impact from Reserved Instances
(RIs) or Savings Plans (SPs). Note that the on-demand prices will reflect any custom pricing
agreements that you have configured in Cloudability.

**Select Account**

By default, the dashboard shows recommendations for all accounts. To view recommendations for a
particular account, select the account name from the Account dropdown.

**Specify Timeline**

You can choose to review spend across the last **10 days** or the last 30 days. By default,
the **Timeline** option is set to 10 days. For an idle ElasticIP recommendation, the resource is
recommended to be terminated if it is unattached for at least the last half of the lookback period.

**Apply Filters**

You can add filters to include or exclude data based on one or more conditions.

**Add a filter**

To add a filter:

1. Select **Add Filter** from the toolbar.
2. In the **Add Filter** menu, choose a **Dimension**.
3. Select an **Operator** to provide a logical condition.
4. Choose a value to refine your filter.
5. Select **Add Filter** to apply the new filter to the page.

**Apply filters with links**

You can also add filters by selecting the blue hyperlinked values in the main table. The filter
rule is automatically applied to the **Filters** field. You can select only one value or
parameter from each column at a time.

**Remove a filter**

To remove a filter:

1. Select the filter icon. ![](../../../../03-media/cloudability-premium/images/edit-icon.jpg)
2. Select X next to the filter that you want to remove.

## Key Performance Indicators

You can view the following Key Performance Indicators (KPIs) on your Rightsizing dashboard:

- **Total****Spend**: Shows the total current spend on the ElasticIP resources with
  recommendations
- **Estimated Idle****Savings**: Shows the estimated total savings for
  all Terminate recommendations.
- **Estimated Rightsizing****Savings**: Shows the estimated total potential savings
  achievable for all Rightsize recommendations. As Elastic IP addresses only support terminate
  recommendations, this is expected to show 0.
- **Estimated Optimized****Spend**: Shows the estimated total spend after recommendations
  are applied. As Elastic IP addresses only support terminate recommendations, this is expected to
  show 0.

## Rightsizing Recommendations Table

The dashboard contains a rightsizing recommendations table, which provides an overview of your
AWS ElasticIP resources. The table includes the following columns:

Note: By default, the data is sorted by the Cost Savings column. To change the sort order, just
select the column name.

- **Resource****ID**: The volume ID.
- **Resource****Name**: The volume name.
- **Account****Name**: The AWS account name.
- **Idle**: The percent of hours with zero IOPS.
- **State**: The state can be Attached , Unattached , or Deleted .
- **Cost**: The total cost of the volume.
- **Type**:The volume type.
- **Size**: The volume size (in GiB).
- **New****Type**: The top recommended volume type.
- **New****Type**: The top recommended volume type.
- **New****Size**: The top recommended volume size (in GiB).
- **Action**: Recommendation for the resource, currently only terminate recommendations are
  available for ElasticIP addresses.

**Cost****Savings**: The estimated 10- or 30-day cost savings amount.

**Export recommendations to an Excel file**

To export the recommendations to an excel file, select Export . Note that the excel file will
include several additional columns, such as region, operating system, unit price, and others.

**Recommendation details**

To view the recommendation details for a particular resource, select View Details from the More
Options (3 dots) menu.

The EBS details panel shows the following information:

- **Last Billing****Date**: The last date for which the cost data is available.
- **Last Attached****Date**: The last date the volume state was attached.
- **Last Attached****ID**: The last instance ID to which the volume was attached.
- **Type**: The volume type.
- **Size**: The volume size.
- **Throughput**: The maximum volume throughput.
- **IOPS**: The maximum volume IOPS.
- **Risk (under recommendations)**: Characterizes the likelihood to reach capacity limits for
  a given recommendation.
- **Utilization****Metrics**: The utilization metrics displayed for EBS volumes are based
  on the following parameters.

**Parent topic:** [Rightsizing](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
