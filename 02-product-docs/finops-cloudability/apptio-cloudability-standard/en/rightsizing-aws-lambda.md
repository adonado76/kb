---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "AWS Lambda"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "AWS Lambda"
source_path: "SSVCLNQ/product/rightsizing-aws-lambda.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# AWS Lambda

Use the Rightsizing dashboard to see resource optimization recommendations for Amazon Web Services (AWS) Lambda. The dashboard shows both the rightsizing and idle (terminate) recommendations. You can view the recommendations across multiple accounts from a single dashboard.

Visit Rightsizing in Cloudability to learn more.

## Before you begin

- Enable the correct permissions which are: lambda:ListFunctions lambda:ListProvisionedConcurrencyConfigs
- Enable Lambda Insights enhanced monitoring. This allows Cloudability to retrieve memory metrics for your Lambda functions.
- Connect Cloudability to your correct AWS accounts.
- For customers with previously existing connections to AWS accounts: Create or download an updated AWS credential template in Cloudability and upload the new credential template to AWS Management Console.
- Visit the following pages to learn more: Enabling Lambda Insights Connect Amazon Web Services

## Explore the AWS Lambda dashboard

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

## Access the AWS Lambda dashboard

To access the AWS Lambda dashboard:

1. Open Cloudability. From the navigation menu, select Optimize > Rightsizing .
1. Select the AWS tab, then select the Lambda subtab.

## Customize the dashboard

You can set the following options to customize your dashboard:

1. Select Account : By default, the dashboard shows recommendations for all accounts. To view recommendations for a particular account, select the account name from the Select Account drop down menu.
1. Specify Timeline : You can choose to review spend across the last 10 days or the last 30 days. By default, the Timeline option is set to 10 days. For most users, 10 days is the recommended time period because it captures the most recent performance trends and is more predictive of future resource use.
1. Apply Filters : You can add filters to include or exclude data based on one or more conditions.

## Add filters with the filter option

To add a filter:

1. Select Add Filter from the toolbar.
1. In the Add Filter menu, choose a Dimension .
1. Select an Operator to provide a logical condition.
1. Choose a value to refine your filter.
1. Select Add Filter to apply the new filter to the page.

## Apply filters with links

You can also add filters by selecting the blue hyperlinked values in the main table. The filter rule is automatically applied to the Filters field. You can select only one value or parameter from each column at a time.

## View recommendation details

To view the recommendation details for a particular resource, select the More Options (3 dots) menu and select View Details .

- To view descriptions of the cost dimensions and metrics, visit to Glossary of cost dimensions and metrics .
- To view details of the utilization dimension and metrics, visit to Glossary of utilization dimensions and metrics .
