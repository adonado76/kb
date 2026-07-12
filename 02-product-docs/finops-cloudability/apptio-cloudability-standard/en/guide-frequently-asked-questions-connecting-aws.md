---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Frequently Asked Questions for Connecting with AWS"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connecting with AWS - Customer Integration Guide"
  - "Frequently Asked Questions for Connecting with AWS"
source_path: "SSVCLNQ/admin/aws-credentialing-standard-enterprise-faq.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Frequently Asked Questions for Connecting with AWS

- I don’t see any cost data after completing the account credentialing steps, what should be done? Verify the correct billing files are in your S3 bucket Navigate to your S3 bucket shown on the AWS Billing and Cost Management page , found under Cost and Usage Analysis – Data Exports. When selected, you should see the prefix you created previously, you can click into it and browse into the billing exports Make sure you see files similar to the following: <BillingReportName>.csv.gz <BillingReportName>-Manifest.json If you don’t see files like these, then you need to ensure your Cost and Usage report is enabled for resource IDs and tags. For more information, see Configure consolidated account credentials .

- I recently turned on the AWS Cost and Usage report and credentialed in Cloudability. How long will it take to see the Cost and Usage data? It may take up to 24 hours for your first Cost and Usage report to generate in AWS. For more information, please refer: https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=ts-cloudability-cloudability-cost-usage-data-availability-in-reporting

- Can I use linked accounts credentialing directly instead of Consolidated account credentialing? Cloudability only supports consolidated billing and not billing at a linked account level. Programmatic Billing Access rolls up to the consolidated account, so linked accounts don’t receive the necessary files in the S3 Bucket. You need to add the consolidated account with Programmatic Billing Access enabled to Cloudability.

- How do I update to the latest CloudFormation template? This can be done using Cloudability Manage AWS credentials Keep your AWS credentials up to date in Cloudability with the following instructions. Regenerate a Cloud Formation template To regenerate the Cloud Formation template to reconfigure your AWS access, do the following: In Cloudability , navigate to Settings > Vendor Credentials > AWS . Note: The Vendor Credentials page requires admin permissions to access it. Save and download the current CloudFormation template In AWS navigate to CloudFormation à Stacks Find out which stack he has previously run in order to install the previous Cloudability CloudFormation template. Select the same stack and click the update stack button Select ' make a direct update ' , select replace existing template and upload a template file. Upload the new CloudFormation template file. On successful update, re-verify the account.

- Here’s how you can update to the latest version for all of your organization's payer and linked accounts. Consolidated accounts (need S3 bucket access): see Configure consolidated account credentials Linked accounts (do not need S3 bucket access): see Set up access to AWS API

- Which formats are supported for AWS CUR files ? Cloudability supports AWS Legacy CUR and CUR 2.0 in both the formats. gzip - text/csv Parquet - Parquet
- Is migration to CUR 2.0 necessary? For new AWS accounts, CUR 2.0 is the default option. For your existing accounts, migration is recommended for access to newer AWS billing capabilities.
- How to switch from Legacy CUR to CUR 2.0? This can be achieved by a couple of ways:

- Option 1: Create the CUR 2.0 export same as Legacy CUR The simplest way is to create a CUR 2.0 export in the same bucket with the same export name and same export prefix as legacy CUR. If this is chosen, there are no additional steps required to be performed in Cloudability UI. In the next data pull Cloudability will automatically start reading from CUR 2.0. Option 2: Create a new CUR 2.0 and update credentials In AWS: Create a new CUR 2.0 export in AWS Management Billing with a new name. Use the same bucket (which was used for Legacy CUR) for the export or create a new one. Create the export as per the steps above under the Consolidated Account Credentialing. In Cloudability: Select the consolidated account for which CUR 2.0 is configured. Click Edit: Update the S3 bucket name (if it's a new one) Update the cost and usage report name (if it's a new one) Update the cost and usage prefix. (if it's a new one) Download the Cloud formation template (CFT). Note: This is only required if you create a new bucket. If you haven't created a new bucket skip the download of CFT, Click Save and Verify Credential. In AWS: Upload and run the CFT as a stack. In Cloudability Select the same management account Click Edit Click Save Verify Credential Once you have switched from Legacy CUR to CUR 2.0, you’ll need to reconfigure the tags in Cloudability. Note: Cloudability looks for the manifest file in the below location: Legacy CUR - <Cost and Usage report prefix>/<Cost and Usage report Name>/YYYYMMDD-YYYYMMDD/<Cost and Usage report Name>-Manifest.json CUR 2.0 - <Cost and Usage report prefix>/<Cost and Usage report Name>/metadata/BILLING_PERIOD=YYYY-MM/<Cost and Usage report Name>-Manifest.json The data export that you create as per the cloudability steps by default will load the data in the above location. If any historical data is fetched then cloudability expects the manifest files in the above location.

- Will there be any change to historical data reporting with migration of CUR formats? No there is no impact on historical data which was fetched as part of legacy CUR.
- Does Cloudability supports custom CUR files? No we don't support custom CUR files , changing the CUR files can have multiple impacts on the system based on the change.
- Can we ingest historical cost data in Cloudability? If yes, how far back data can be ingested? Yes, we can. Please check with IBM Cloudability Support teams on how to bring in Historical data.

- Does Cloudability supports encryption on S3 buckets? Yes, Customers can configure server-side encryption with Amazon S3 managed keys (SSE-S3) on their S3 buckets. Cloudability doesn't support encryption using KMS or customer provided encryption keys. Can FOCUS format be used instead of CUR for integration if AWS Data? Cloudability supports both FOCUS and AWS CUR. However for AWS data we recommend using CUR file.
- Where Can I find Cloudability's Vendor Credentials APIs for AWS Vendor Credentials End Point (AWS)
