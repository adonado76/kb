---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Map AWS tags to Apptio Schema"
breadcrumb: []
source_path: "configuration/mapawstoschema.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Map AWS tags to Apptio Schema

This article will help you map AWS cost allocation tags to your Apptio schema. Cost
allocation tags help you categorize and track your AWS costs.

When you apply tags to your AWS resources (such as Amazon EC2 instances or Amazon S3 buckets) and
activate the tags, AWS generates a cost allocation report as a comma-separated value (CSV file) with
your usage and costs aggregated by your active tags. You can apply tags that represent business
categories (such as cost centers, application names, or owners) to organize your costs across
multiple services.

Applies to: Apptio Costing Standard on TBM Studio 12.3.3 and later

## About this task

The following AWS resources provide background information about tags:

- [What Is a Tag?](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/billing-what-is.html "(Opens in a new tab or window)")
- [Tag Restrictions](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/allocation-tag-restrictions.html "(Opens in a new tab or window)")
- [Setting Up Your Monthly Cost Allocation Report](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/configurecostallocreport.html "(Opens in a new tab or window)")
- [AWS Billing and Cost Management](https://docs.aws.amazon.com/awsaccountbilling/latest/aboutv2/cost-alloc-tags.html "(Opens in a new tab or window)") (This site also provides a
  .pdf file of Amazon's billing and cost management information.)

Recommended tags

Not all AWS tags are required for Apptio. The following list is recommended as a guide for the
data that will be important in your Costing Standard implementation.

| **Tag** | **Description** | **Value in Apptio** |
| --- | --- | --- |
| Application Name | Name of the application supported by the tagged resource | - Provide analytics to help understand cloud spend by apps consuming cloud services - Allocate spend to apps to calculate TCO |
| Application Environment (Prod, Dev, Test, DR) | Environment supported by the tagged resource | Provide analytics to help understand cloud spend by app environment built on cloud services |
| Application Tier (Web server, Business Logic, Database) | App tier of the tagged resource | Provide analytics to help understand cloud spend by app tier built on cloud services |
| Cost Center | Cost center responsible for operating the tagged resource | - Provide analytics to help understand cloud spend by cost center consuming cloud services - Allocate and showback/chargeback spend to IT customers |
| System Owner | Individual responsible for operating the tagged resource | - Provide analytics to help understand cloud spend by cost center consuming cloud services - Allocate and showback/chargeback spend to IT customers |
| Project | Project associated with the tagged resource | - Provide analytics to help understand cloud spend by cost project driving cloud services - Allocate spend to IT projects |

**Parent topic:** [Costing Standard](../home.html)

## For the monthly Cost Allocation report

### Procedure

1. Navigate to TBM Studio.
2. Select the **AWS Cost Allocation Bill Master Data** and check it out.

   ![](../../resources/images/ct_images/check-out-aws-master.png)
3. In the transform pipeline, click the **Append** step, then click **Edit** on AWS
   Cost Allocation Raw.

   A dialog opens, allowing you to map columns from the raw AWS Cost Allocation Raw to the Apptio
   AWS Cost Allocation Bill Master Data table.
4. Complete the mappings for the following columns that are relevant to your organization's
   AWS tags and payer/linked account structure: 

   **IMPORTANT Be sure to click **Save**after completing the mappings.**
   - Business Unit (defaulted to Payer Account)
   - Department (defaulted to Linked Account)
   - Team
   - System Owner
   - Cost Center
   - Application
   - Environment
   - Project
   - Purpose
5. Click **Save**, then check in your work.
