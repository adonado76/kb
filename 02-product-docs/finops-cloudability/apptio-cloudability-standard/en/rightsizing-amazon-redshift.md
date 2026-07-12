---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Amazon Redshift"
breadcrumb:
  - "Optimize"
  - "Rightsizing"
  - "Amazon Redshift"
source_path: "SSVCLNQ/product/aws_redshift.html"
images:
  - "03-media/apptio-cloudability-standard/Redshift-Rightsizing.jpg"
  - "03-media/apptio-cloudability-standard/Redshift-Rightsizing-Details.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Amazon Redshift

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
