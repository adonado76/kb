---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "AWS Linked Account Credentialing"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
  - "AWS Linked Account Credentialing"
source_path: "SSVCLNQ/admin/aws-credentialing-standard-enterprise-linked.html"
images:
  - "03-media/apptio-cloudability-standard/AWS-linked1.png"
  - "03-media/apptio-cloudability-standard/clip_image002_1065401583.png"
  - "03-media/apptio-cloudability-standard/clip_image003_1276902897.png"
  - "03-media/apptio-cloudability-standard/AWS-linked2.png"
  - "03-media/apptio-cloudability-standard/clip_image002_1795777736.png"
  - "03-media/apptio-cloudability-standard/clip_image003_-445731613.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# AWS Linked Account Credentialing

After configuring your consolidated account for data ingestion, Cloudability will display linked accounts under the Consolidated account in a few hours, but they don't contain any AWS API data yet.

AWS API data is required to get utilisation and commitments data which enables the Optimization features (e.g.. Rightsizing) in Cloudability.

To enable access to AWS API endpoints for each linked account, Cloudability generates CloudFormation templates for you to upload to AWS. This can be done via Automation (recommended) or manually for every linked account.

Automated Credentialing of Linked Accounts

We recommend using automation as this simplifies the credentialing process - especially when you have a significant number of linked accounts.

Before you begin:

- Familiarize yourself with AWS Stacksets
- Ensure you have the IAM role in your AWS - AWSCloudFormationStackSetAdministrationRole – this ensures linked accounts can have the permissions pushed to them.
- Ensure you have checked the “Automated credentialing of Linked Accounts” during the Consolidated Account Credentialing process previously.
- Familiarize yourself with AWS Credentialing using Bulk Actions

In Cloudability – Navigate to the linked account

- Navigate to Settings > Vendor Credentials > AWS.
- Click your mouse cursor on the … of a linked account (not consolidated account)
- Select the pencil icon to open the Edit a Credential panel.
- Add AWS SCP Enabled Region (Optional): In the event you have applied AWS Service Control Policy / policies (SCP) which restrict access in some AWS regions, indicate your allowed region; example us-east-2. If not, this can be left blank. This helps Cloudability to make verification calls to the allowed region specified. Currently Cloudability supports addition of a single SCP region.
- Click Save .
- Select Download.

In AWS - Upload the CloudFormation template to the AWS Management Console

Complete the following steps to Upload the CloudFormation template to the AWS Management Console as a StackSet.

1. In the AWS Management Console , in your Consolidated Account in the search bar enter 'CloudFormation'
1. Select it.
1. From the left-hand side of the AWS CloudFormation page, select Create Stack Set. Under Choose a template, do the following: Leave default parameters for permissions and prerequisites Select Upload a template file. Select Choose file and upload the template you downloaded from Cloudability.
1. Select Next.
1. From the Specify StackSet details page, do the following: Enter a StackSet Name (for example, ' Cloudability '). Verify the populated Parameters. Select Next.
1. Scroll through the Configure StackSet options page and check the “I acknowledge that AWS CloudFormation might create IAM resources with customized names” and click Next. Scroll to specify regions and Add specific regions OR Click Add all regions Click Next
1. Select Submit.

Your new stack initially has a status of CREATE_IN_PROGRESS. When the status changes to CREATE_COMPLETE , check in StackSets the status of your linked accounts that have a status of Succeeded, and any which do not - you will need to manually validate as to why if you have failures.

In Cloudability - Verify the linked account credential

This can be done via bulk actions or manually.

Bulk Verification via UI: AWS Credentialing using Bulk Actions

Manual Verification via UI:

- Navigate to Settings > Vendor Credentials and edit each linked account, Click on Save and then Select Verify Credential for every linked account. A green tick ( ) indicates success whereas a red exclamation ( ) indicated errors that need to be followed up.

Manual Credentialing AWS Linked accounts

This is only applicable if the previous “Automated credentialing of Linked accounts” was left unchecked during the Consolidated Account Credentialing process

In Cloudability – Navigate to the linked account

- Navigate to Settings > Vendor Credentials > AWS .
- Click your mouse cursor on the … of a linked account (not consolidated account)
- Select the pencil icon to open the Edit a Credential panel.
- Add AWS SCP Enabled Region (Optional):
- In the event you have applied AWS Service Control Policy / policies (SCP) which restrict access in some AWS regions, indicate your allowed region; example us-east-2. If not, this can be left blank. This helps Cloudability to make verification calls to the allowed region specified.
- Select Save
- Select Download .

In AWS - Upload the CloudFormation template to the AWS Management Console

Complete the following steps to Upload the CloudFormation template to the AWS Management Console as a Stack. This will have to be done in every linked account.

1. In the AWS Management Console , working in the linked account you are credentialing, in the search bar enter 'CloudFormation' .
1. Select it.
1. From the AWS CloudFormation page, select Create Stack (with new resources (standard))
1. Under Specify template , do the following: Select Upload a template file Select Choose file and upload the template you downloaded from Cloudability. Select Next .
1. From the Specify stack details page, do the following: Enter a Stack name (for example, 'Cloudability') Verify the populated Parameters . Select Next .
1. Scroll through the Configure stack options page and check the “I acknowledge that AWS CloudFormation might create IAM resources with customized names” and click Next
1. From the Review page, Select Submit .

In Cloudability – Verify the linked account credential

This can be done via bulk actions or manually.

Bulk Verification via UI: AWS Credentialing using Bulk Actions

Manual Verification via UI:

- Navigate to Settings > Vendor Credentials and click on the … and select Re-Verify. A green tick ( ) indicates success whereas a red exclamation ( ) indicated errors that need to be followed up. This process will need to be repeated for every manually credentialed Linked account.
