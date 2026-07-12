---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connecting with AWS - Customer Integration Guide"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
source_path: "SSVCLNQ/admin/aws-credentialing-standard-enterprise-home.html"
images:
  - "03-media/apptio-cloudability-standard/curP.png"
  - "03-media/apptio-cloudability-standard/curP1.png"
  - "03-media/apptio-cloudability-standard/AWS-VC.png"
  - "03-media/apptio-cloudability-standard/clip_image001_1499665667.png"
  - "03-media/apptio-cloudability-standard/clip_image002_-1577046812.png"
  - "03-media/apptio-cloudability-standard/AWSp.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connecting with AWS - Customer Integration Guide

Overview

This guide walks you through the process of securely connecting your AWS environment to IBM Cloudability. Once connected, you’ll gain access to the FinOps capabilities within Cloudability.

Prerequisites

Before you begin, ensure you have access to:

- AWS console
- Admin (or similar) privileges in AWS for S3 creation and IAM permissions
- Admin access to the Cloudability Vendor Credentials

- Management Account Credentialing
- Linked Account Credentialing

AWS Management Account Credentialing

- Bringing in Cost and Usage data for credentialed AWS Management Account(s).
- Syncing the linked accounts under the AWS Management Account(s).

Let’s get started with the Credentialing process:

1. AWS Console - Create an AWS Cost and Usage report From the AWS Management Console , select your account name at the top right and select Billing and Cost Management . From the Billing & Cost Management Dashboard page, select Data Exports (under Cost and Usage Analysis) . Select Create .

- gzip - text/csv
- Parquet - Parquet

Here are the steps required to configure either of the CUR files.

- Cloudability supports data exports created at a Management Account level.

| Steps in AWS | Legacy CUR | CUR 2.0 |
| --- | --- | --- |
| Create Export > Export Details | Legacy CUR Export | Standard Data Export |
| Create Export > Data table content settings | Select Include resource IDs . Split cost allocation data should be unchecked . Select Refresh automatically in data refresh settings. | Select CUR 2.0 . Select Include resource IDs . Split cost allocation data should be unchecked Select Hourly for Report data time granularity. Column Selection – Leave as default (all columns) |
| For Data export delivery options, select the following. | Select Hourly for Report data time granularity. Select either of: Overwrite existing data export file Create new data export file Report Data Integration options should not be selected. Ensure that the compression type is set to gzip or parquet | Ensure that the compression type is set to gzip- text/cs or parquet-parquet. Select either of: Overwrite existing data export file Create new data export file |
| For Data export storage settings. | Your Cost and Usage report files will reside in this bucket. You can; Enter a pre-existing S3 bucket and prefix or Select Configure . If Configure is selected Select Create a Bucket (or select existing bucket if already created) Enter an S3 bucket name Select Region for creating a new bucket Click Create Bucket Add an s3 path prefix Add any tags (optional) Select Create Report | Your Cost and Usage report files will reside in this bucket. You can; Enter a pre-existing S3 bucket and prefix or Select Configure . If Configure is selected Select Create a Bucket (or select existing bucket if already created) Enter an S3 bucket name Select Region for creating a new bucket Click Create Bucket Add an s3 path prefix Add any tags (optional) Select Create |

Legacy CUR - <Cost and Usage report prefix>/<Cost and Usage report Name>/YYYYMMDD-YYYYMMDD/<Cost and Usage report Name>-Manifest.json

CUR 2.0 - <Cost and Usage report prefix>/<Cost and Usage report Name>/metadata/BILLING_PERIOD=YYYY-MM/<Cost and Usage report Name>-Manifest.json

![cur](../images/curP.png)

![cur](../images/curP1.png)

Please record the below details as these will be entered in Cloudability in the below steps:

1. PAYER ACCOUNT ID: AWS Management Account ID
1. S3 BUCKET NAME: The bucket that contains your Cost and Usage report created earlier
1. COST AND USAGE REPORT NAME created earlier
1. COST AND USAGE REPORT PREFIX created earlier

For details on moving from Legacy CUR to CUR 2.0 please check the FAQs.

- Split cost allocation data
- Include Capacity Reservation Columns and Granularity
- Manually Compatible discounts

2. AWS Console - Enable cost allocation tags

1. From the Billing & Cost Management Dashboard , navigate to Cost Allocation Tags .
1. Select the tags that you want to include. Note: Be mindful of camel case. For example: If you have "Name" or "name" as a tag key - both needs to be activated so they are written to CUR.
1. Select Activate .

You must have Cloudability Administrator rights to complete this procedure. If you don’t have administrator rights, contact your organization’s primary Cloudability administrator for assistance.

In Cloudability, navigate to Settings > Vendor Credentials > Add Datasource and select > AWS .

1. Under Credentials , enter the following: Payer Account ID (Mandatory) S3 Bucket Name (Mandatory): The bucket that contains your Cost and Usage report Cost and Usage Report Name (Mandatory) Cost and Usage Report Prefix (Mandatory) AWS SCP Enabled Region (Optional) In the event you have applied AWS service Service control Control Policy (SCP) which restrict access in some AWS regions, indicate your allowed region; for example: us-east-2. If not, this can be left blank. This helps Cloudability to make verification calls to the allowed region specified. Currently, Cloud ability supports addition of a single SCP region. Automated Credentialing of Linked Account(s) (Recommended) We recommend the use of Automated credentialing of AWS linked accounts if you have a significant number of linked accounts. Utilising this will simplify your Credentialing process now and for future addition of new accounts. To use the Cloudability Automated credentialing of linked accounts feature, additional work needs to be performed in Cloudability and AWS which includes downloading a CloudFormation Template from a linked account and deploying it as a StackSet (ensuring the correct IAM role is in place for linked accounts to inherit IAM permissions). This is covered in detail in Linked account credentialing.
1. Select Save .
1. Select Generate Template .
1. Select Download .
1. An AWS CloudFormation template will be downloaded locally – save this in a secure place for your next step as this will need to be uploaded into the AWS console.

4. AWS Console - Upload the CloudFormation template to the AWS Management Console

1. In the AWS Management Console , search for 'CloudFormation' and select it.
1. From the AWS CloudFormation page, select Create Stack (with new resources (standard)) .
1. Under Specify template , do the following: Select Upload a template file . Select Choose file and upload the template you downloaded from Cloudability. Select Next .
1. From the Specify stack details page, do the following: Enter a Stack name (for example, 'Cloudability'). Verify the populated Parameters . Select Next .
1. Scroll through the Configure stack options page and check the “I acknowledge that AWS CloudFormation might create IAM resources with customized names” and click Next.
1. From the Review page, select Submit .

Your new stack initially has a status of CREATE_IN_PROGRESS . When the status changes to CREATE_COMPLETE , you can verify your credential in Cloudability. You may need to refresh the CloudFormation page in the UI to confirm this.

5. Cloudability - Verify the Account Credential

1. In Cloudability, navigate to Settings > Vendor Credentials > AWS .
1. Click on the … next to the account being credentialed and select Re-Verify. A green tick ( ) indicates success where as a red exclamation ( ) indicated errors.

![aws](../images/AWSp.png)

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and AWS tags within Cloudability.
- Pricing data would also be pulled in.
- Cloudability will also display the linked accounts.

As a next step you will need to credential the Linked accounts.

AWS Linked Account Credentialing

AWS Obtaining Memory Metrics for EC2 Instances - Windows & Linux

AWS FAQ
