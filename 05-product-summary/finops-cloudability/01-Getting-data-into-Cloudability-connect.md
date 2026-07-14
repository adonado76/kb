---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "01-Getting-data-into-Cloudability-connect"
source_files_count: 39
last_updated: "2026-07-13"
---

# 01-Getting-data-into-Cloudability-connect

## Connect Custom Data (FOCUS Ingress)

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Custom Data (FOCUS Ingress)
- **source_path:** SSVCLNQ/admin/connect-custom-data-focus-ingress.html
- **original_file:** cloudability-connect-custom-data-focus-ingress.md
- **images:**
  - 03-media/apptio-cloudability-standard/focus.jpg

## Connect Custom Data (FOCUS Ingress)

The FinOps Open Cost and Usage Specification ( FOCUS) is a community-driven effort to develop a standard schema for cloud, SaaS, and other billing data. The primary goal of the FOCUS specification is to make it easier to understand, report on, and manage cloud costs. The FOCUS specification is intended to be adaptable across a variety of cloud service providers and SaaS product sources and defines columns (dimensions and metrics), column-specific requirements, and attributes (spec-wide requirements).

You can bring any cost and usage data from additional data sources as long as it has been formatted into the FOCUS schema and adheres to the columns that are required, as defined by the specification.

- We don’t recommend using FOCUS for CSP data as the current cost data set which Cloudability gets natively (CUR/Azure exports/GCP Billing etc) is much more granular than the FOCUS dataset. Using FOCUS, we get only cost data, the current CSP integrations also bring in utilization data which is used in multiple Optimization use cases.
- If you have already credentialed your CSP account(s) via native connector, please don't use the same account to connect via the FOCUS connector.
- To ensure full compatibility and support, please follow the connection steps as described. Custom configurations are not supported. If you have questions, reach out to IBM Support .

The FOCUS Specifications can be found here with specific columns additionally here .

1. FOCUS version 1.0
1. FOCUS version 1.1

Steps for integration

Data Source Management

All the data that is uploaded to any of the storage services must be the entire month-to-date data.

Also, the data must follow a specific structure as:

<Root Directory>/<Optional_Sub_Directories>/<Vendor>/<Report_Period>/<Epoch Time Folder>/<prefix>-Manifest.json

The M in Manifest should always be capitalized.

- Root Directory : A prefix like AWS bucket name, Azure container name or GCS bucket name
- Optional Sub Directories : An optional field for customer. They may or may not have additional sub directories
- Vendor : A vendor name which would help in identifying the vendor type
- Report Period : Report Period for which the data is available. This must be in the formats YYYYMMDD-YYYYMM(+1)DD . For example, for report period 2023-02 the name would look like →20230201-20230301.
- Epoch Time Folder : This will be used to identify the latest drop for month-to-date data.
- Manifest : Metadata json file containing details of specific report period dataset.

All custom data sources via this capability needs to adhere to the FOCUS specifications.

```
{
		"compression": "GZIP",
		"content_type": "Parquet",
		"report_id": "uuid-f431e214843b3c19756368",
		"root_dir": "byod-input-prod",
		"all_report_keys": [
		"<complete/path/excluding/root_dir>/cost-and-usage-report-00001.snappy.parquet",
		"<complete/path/excluding/root_dir>/cost-and-usage-report-00002.snappy.parquet"
		],
		"updated_at": "2024-04-04T05:00:22Z",
		"focus_version": "1.0"
	}
```

File Content Type : JSON

| Header / Field | Header / Field definition | Value : Required / Optional |
| --- | --- | --- |
| compression | CSV : gzip Parquet : All that are supported by Java Hadoop frameworks. | Optional |
| content type | Parquet or CSV | Required |
| report ID | Randomly generated unique report identifier. | Optional |
| root_dir | S3 Bucket or Azure Directory or GCS bucket to fetch the report from. This will be dependent of the type of credentials chosen. | Required |
| all report keys | It is a nested JSON, that is the list of only new absolute file paths excluding the root directory. | Required |
| updated at | Last updated time of the report. | Optional |
| focus version | FOCUS version as per https://finops.dev/focus-spec The version must match the exact FOCUS Spec version. e.g. 1.0 or 1.1 | Required |

We support AWS Simple Storage Service , Google Cloud Storage and Azure Blob Storage as the storage services for housing FOCUS-aligned data.

1. In Cloudability, navigate to Settings > Vendor Credentials > Add Datasource > Other Data Sources .
1. Select Other Data Sources > Add a Credential > The Add other Datasources Account panel opens, click Next .
1. Click on Preferred Storage Provider and follow the prompts.

1. Enter Vendor for which the data needs to be ingested.
1. Enter the corresponding AWS Account ID where the files are located .
1. Enter AWS S3 bucket name under Root Directory .
1. Enter optional sub prefixes under Sub Directories .
1. Enter Manifest Prefix under Manifest Prefix .
1. Click Generate template .

For more information, refer to Connect Amazon Web Services.

1. Enter the Vendor for which the data needs to be ingested.
1. Enter Azure Billing Account ID where the files are located.
1. Enter Tenant ID .
1. Enter Subscription ID .
1. Enter the Resource Group name.
1. Enter the Storage Account name.
1. Enter Blob Container Name under Root Directory .
1. Enter optional sub directories under Sub Directories .
1. Enter Manifest Prefix under Manifest Prefix .
1. Click Generate template .

For more information, refer to Connect Microsoft Azure .

1. Enter the Vendor for which the data needs to be ingested.
1. Enter GCP Billing Account ID where the files are located.
1. Enter GCP GCS bucket name under Root Directory .
1. Enter optional sub prefixes under Sub Directories .
1. Enter Manifest Prefix under Manifest Prefix .
1. Click Generate template .

For more information, refer to Connect Google Cloud.

- Can I use FOCUS format to bring CSP data for AWS, Azure, GCP, OCI? We don’t recommend using FOCUS for CSP data as the current cost data set which Cloudability gets natively (CUR/Azure exports etc) is much more granular than the FOCUS dataset. Using FOCUS, we get only cost data, the current CSP integrations also bring in utilization data which is used in multiple Optimization use cases.

- What are the use-cases of using FOCUS for CSP data? FOCUS can be used for CSP datasets for regions or vendors which we don’t support natively in Cloudability. E.g. AWS China Ali Cloud Any other public cloud which Cloudability doesn’t support natively
- If I bring in other regions or vendor’s data, what are the pre-requisites? FOCUS data should be hosted in a bucket outside of the region which Cloudability doesn’t support e.g. Not in China but rather USA or EU or AU. Ensure that while credentialing provide the account details where the cost export files are hosted. Parquet files must only be compressed while being generated (Using hadoop, avro default compression techniques) and not explicitly compressed. The FOCUS manifest.JSON file must have the correct “report keys” which specify the exact report files to retrieve, including correct file extensions.

---

## Connect Databricks

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Databricks
- **source_path:** SSVCLNQ/admin/connect-databricks.html
- **original_file:** cloudability-connect-databricks.md
- **images:**
  - 03-media/apptio-cloudability-standard/Databricks-Service-Principle.png
  - 03-media/apptio-cloudability-standard/Databricks-Add-Service-Principle.png
  - 03-media/apptio-cloudability-standard/Databricks-Add-Service-Principle-permission.png
  - 03-media/apptio-cloudability-standard/Databrick-Runtime.png
  - 03-media/apptio-cloudability-standard/clip_image001_-1832790195.png
  - 03-media/apptio-cloudability-standard/clip_image002_-821243953.png

## Connect Databricks

You can connect your Databricks account to Cloudability to enable the ingestion of cost and usage data. This integration is intended to be used only for Databricks on AWS and Databricks on GCP. If you are using Azure Databricks, you will have sufficient data granularity in your Azure billing data.

It takes 24 hours before your initial cost and usage data appears in Cloudability

Prerequisites

- Should be a Cloudability administrator and have access to the Cloudabiliy’s Vendor Credentials page.

- Appropriate permissions to set up a Unity Catalog, enable a Workspace & System Schema and create a Service Principal User that will have access to the catalog, schema, and table.

- You should be a Databricks Account admin to manage OAuth credentials for the service principals.
- Databricks Account admin / Workspace admin can take actions in the databricks workspace console.

- Need to create a SQL Warehouse (SQL Warehouse should be serverless), that can be used by the Service Principal User to run the query
- Should be able to schedule the notebook to run once in 24 hours to pull Databricks costs and usage data
- For Scheduling the notebook, customer needs to create a compute machine which contains the spark configuration.
- Please check if you have a commitment contract or pay as you go contract for databricks, this would help Cloudability is showing the billing cost appropriately

Summary of the integration

This integration requires users to set up a Unity Catalog, enable a Workspace & System Schema and create a Service Principal User that will have access to the catalog, schema, and table. Users also need to create a SQL Warehouse, that can be used by the Service Principal User to run it, based on the notebook downloaded in the Credentials UI. This notebook must run once every day to pull Databricks costs and usage data. Cloudability does not have access to your custom discounts with Databricks, so we have added an option to input that information in the credentialing UI so that we can factor this discount into the costs we display.

Databricks recommends using a service principal identity for automated tools, jobs, and applications. We ask you to create one for this integration, as we are automating the process of usage and billing monitoring.

1. Set Up Unity Catalog. Click https://docs.databricks.com/en/data-governance/unity-catalog/get-started.html .
1. Enable a Workspace for Unity Catalog. Click https://docs.databricks.com/en/data-governance/unity-catalog/enable-workspaces.html .
1. Enable System Schema in Unity Catalog. Click https://docs.databricks.com/api/azure/workspace/systemschemas/enable
1. Create a Service Principal User at account level. Click https://docs.databricks.com/en/admin/users-groups/service-principals.html#add-service-principals-to-your-account-using-the-account-consol .
1. Add Service Principal to Unity Catalog Enabled Workspace. Click https://docs.databricks.com/en/admin/users-groups/service-principals.html#add-a-service-principal-to-a-workspace-using-the-workspace-admin-settings .
1. Grant Service Principal the privilege on the newly created catalog, schema and table. Click https://docs.databricks.com/en/data-governance/unity-catalog/manage-privileges/index.html#manage-privileges-in-unity-catalog .
1. Create an SQL warehouse, Click https://docs.databricks.com/en/compute/sql-warehouse/create.html . Note: SQL Warehouse should be serverless
1. Grant Service Principal the permission to use SQL Warehouse. Click https://docs.databricks.com/en/compute/sql-warehouse/create.html#manage-a-sql-warehouse .

- The high-level line item for AWS.

- The line items with detailed Databricks costs and AWS Marketplace listed as Seller.

You will need to set up filters or views to hide your Marketplace costs. Marketplace costs are excluded from billing.

Step 1 – Databricks Account Console

Create a Service Principal

1. As an account admin, log in to the account console.
1. Click User Management .
1. On the Service Principals tab, click Add Service Principal .
1. Enter a name for the service principal.
1. Click Add.
1. Select the credentials & secrets tab
1. Under OAuth Secrets , click Generate Secret .
1. Select the maximum number of days and select done.
1. Copy the displayed Secret and Client ID , and then click Done.

Step 2 – Databricks Workspace Console

1. Log in to the workspace.
1. Click User Management .
1. Select Settings .
1. Click Identity and access .
1. Click Manage in Service principals.
1. Click Add Service Principal.
1. Add the same service principal which was created above.

![](../images/Databricks-Add-Service-Principle.png)

1. Click SQL Warehouse .
1. For the warehouse to be used in querying, click on the warehouse.
1. Click Permissions .
1. Add Service Principal with the Can Use permission.

![](../images/Databricks-Add-Service-Principle-permission.png)

Step 3 – Cloudability

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource and select Databricks Download the notebook

Step 4 – Databricks Workspace Console

If the billing_data catalog exist, then please proceed with the below steps, if not please run the notebook downloaded from Cloudability and then proceed with the below steps.

1. Click on the catalog.
1. Click the catalog name, for which permissions need to be given.
1. Click Permissions .
1. Click Grant .
1. Select the Principals.
1. Select USE CATALOG , USE SCHEMA , and SELECT under Privileges .
1. Click Confirm.

1. Enter the details in Cloudability UI Databricks Account id Databricks client id Databricks secret Note: Copy client id and secret from the service principal Workspace URL without https – This is the workspace where you have applied the service principal Enter the Warehouse id which you have created in step 2 Select the subscription model Marketplace – Select marketplace if you have purchased Databricks via AWS or GCP marketplace Direct – Select this option if you have bought directly from Databricks Dependent CSP Select AWS or GCP where the infrastructure is hosted Select a payment model Committed contract Here we need the start date, end date discount % details of the commitments In case you have multiple commitment contracts, same can be added using the + button Pay as you go Share the pay as you go start date Click Save Click Verify .

A green tick ( ) indicates success whereas a red exclamation ( ) indicated errors

In the event that verification fails, please retry after 15 minutes.

After completion of this process, within 24 hours, you’ll start seeing your billing data and tags for databricks being populated within Cloudability.

Frequently Asked Questions

Does Cloudability support IP whitelisting for controlling the traffic to Databricks?

Yes, IP whitelisting is supported. Please contact IBM support for more details.

Does Cloudability supports Private links or Delta Sharing for Databricks?

No Private links or Delta Sharing are not yet supported for Databricks.

What to do in case the Scheduled notebook is not running?

Please ensure to configure a compute machine with Spark enabled

Is it possible to modify the Notebook?

It is recommended not to edit the notebook that is downloaded from Cloudability UI as various internal processes uses the configurations.

How to get Databricks Tags?

Cloudability supports Resource level custom tags

- These are part of the Databricks Billing data and no extra permissions are required within Cloudability for enabling these
- We do pass usage metadata, identity metadata and product features as Tags.Workspaceid will be visible as a tag key under cldy:databricks:workspaceid

What is the need to enter the discounts in UI?

Cloudability does not have access to your custom discounts with Databricks, so we have added an option to input that information in the credentialing UI so that we can factor this discount into the costs we display

What is the relevance of the dates while credentialing Databricks?

The dates mentioned during Credentials UI are used to fetch the data from Databricks.

Databricks APIs allow us to fetch the data for past 13 months, customers can choose any date within the past 13 months to fetch Databricks granular data.

---

## Connect Datadog - Utilization Data

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Datadog - Utilization Data
- **source_path:** SSVCLNQ/admin/connect-datadog.html
- **original_file:** cloudability-connect-datadog-utilization-data.md
- **images:**
  - 03-media/apptio-cloudability-standard/datadog-integration-readonly.jpg
  - 03-media/apptio-cloudability-standard/vc_ss10.jpg
  - 03-media/apptio-cloudability-standard/datadog-integration-azure.jpg

## Connect Datadog - Utilization Data

If you use Datadog to monitor your resources, you can take advantage of Cloudability 's Datadog integration to help you reduce wasted spend by optimizing your resource usage.

Cloudability fully supports Datadog multiple organizational accounts .

- AWS EC2
- Azure Compute
- GCP GCE

- European Union data residency (datadoghq.eu)
- Datadog multiple organizational accounts

Using an Application Performance Monitoring (APM) product like Datadog makes it easy to generate and collect the necessary resource utilization metrics (such as guest memory metrics, which can be difficult to instrument at scale) to get an accurate picture of how the resource is being utilized leading to an accurate rightsizing recommendation. Learn more about Datadog and its product offerings here .

- Improved recommendations: utilization data provided by Datadog offers higher precision, as metric sampling occurs at a higher frequency when compared to the native provider. As a result, we are able to leverage this increased precision to discover an additional 15-20% cost savings opportunities over the default platform metrics.
- Increased coverage: by completing the Datadog Azure integration you will benefit from easier and increased coverage of virtual machine resources, receiving rightsizing recommendations and corresponding cost savings opportunities.

Before you start

API and Application keys

- Datadog API key
- Application key

If you have multiple Datadog organizations, you need to create one API key and Application key per organization. Cloudability requires only a single API key and Application key per Datadog organizational account.'

- Administrator
- Standard
- Read-only

- Read-only keys prevent Cloudability from fetching metadata, such as key name, for the keys.
- Read-only keys prevent Cloudability from being able to perform de-dup. For example, in the case when a user adds multiple read-only keys from the same Datadog organizational account, we need only a single API and Application key per account, but we can't de-dup since read-only keys do not provide us access to the data necessary to perform that check. In other words, Cloudability does not know that these read-only credentials are from the same account.

If you add a read-only application key to your Cloudability credentials, metadata such as key name and owner are shown as Not available .

Steps for integration

We recommend to downgrade the Admin User to Read-Only User for the purposes of this integration, to follow the best practices of information security and privacy.

If you are already an Administrator and need to be the lead for this integration, invite yourself as a new user using a different email address than the one currently set as an Admin User and create the keys. Afterward, downgrade yourself to a Read-Only User.

Create new keys in Datadog

1. Invite a new member as an Admin User for the integration. See Datadog’s User Roles and Permission for more information.
1. Log in as the newly created Admin User.
1. Navigate to Integrations > APIs > New API key .
1. Create a new API key.
1. Go to the New application key section and create a new application key.

Add your Datadog keys to Cloudability

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > Datadog . The Add Datadog Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > Datadog . Select Add a Credential . The Add a Credential panel opens.
1. Select the Datadog tab.
1. Select Yes, I'm ready to confirm you have your Datadog keys.
1. Copy and paste the new API key and application key into the relevant field.
1. Input your API limit in Rate Limit . Note: This integration will require about 300 API requests per hour, as Cloudability needs to collect a month's data within 24 hours. 300 API requests per hour per organization is the default rate set on Datadog's side. If you use the Datadog API for other purposes, we highly recommend you contact Datadog Support to request an increase in the number of API requests you can make. In general, we recommend increasing it to between 600 and 900 API requests per hour per organization. This is a simple, free request to Datadog, and you can reference Cloudability in your request.

Cloudability lists all your Datadog credentials in the same page:

Cloudability integration with Datadog for Azure Compute

Once you have completed the integration steps above, complete the Datadog subscription integration for each subscription containing virtual machines. This procedure includes installing the Datadog Agent on each virtual machine.

Cloudability integration with Datadog for GCP GCE (Google Compute Engine)

For additional information on the setup and installation of Datadog on Google Cloud Platform, see https://docs.datadoghq.com/integrations/google_cloud_platform/#setup

How to confirm success

Within 24 hours after the Datadog Azure integration has been completed, you will see rightsizing recommendations informed by utilization metrics from Datadog. The Data Source column will now display Datadog if the recommendation was informed by utilization data from Datadog.

---

## Connect Datadog - Cost and Usage Data

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Datadog - Utilization Data > Connect Datadog - Cost and Usage Data
- **source_path:** SSVCLNQ/admin/connect-datadog-cost-usage_data.html
- **original_file:** data-connect-datadog-cost-usage.md
- **images:** []

## Connect Datadog - Cost and Usage Data

Summary of the Integration

Datadog allows us to go back and pull cost data for the past 15 months. If the invoice is finalized, then you will see costs attributed to the first of the month. If the invoice has not been finalized, you will see daily costs associated to the products and services you have purchased. This means that generally, you will see daily data for the current month and the last month, until the date that the invoice has been finalized.

The high-level line items per month for AWS

The line items with detailed Datadog costs and “AWS Marketplace” listed as “Seller”

You will need to set up filters or views to hide your Marketplace costs. Marketplace costs are excluded from billing.

Before you start

Before you begin, ensure the following:

- You are a Cloudability administrator.
- You have admin permissions in the Datadog console. We recommend an Admin to create a new user and downgrading that new user from Admin User to Read-Only user for the purposes of this integration. If you are an existing Datadog Administrator setting up this integration, we encourage you to create a new login through creation of a new user, using a different email address (different than the one used for your admin role). Downgrade this user to a Read-Only user.

Steps for integration

We recommend an Admin to create a new user and downgrading that new user from Admin User to Read-Only user for the purposes of this integration.

If you are an existing Datadog Administrator setting up this integration, we encourage you to create a new login through creation of a new user, using a different email address (different than the one used for your admin role). Downgrade this user to a Read-Only user.

Create new keys in Datadog

1. Invite a new member as an Admin User for the integration. See Datadog’s User Roles and Permission for more information.
1. Log in as the newly created Admin User.
1. Navigate to Integrations > APIs > New API key .
1. Create a new API key.
1. Go to the New application key section and create a new application key.

1. In Cloudability , navigate to Settings > Vendor Credentials .
1. Select the Datadog tab.
1. Select Yes, I'm ready to confirm you have your Datadog keys.
1. Copy and paste the new API key and application key into the relevant field.
1. Input your API limit in Rate Limit . to 300, which is the default rate limit. Note: Tags are not yet supported for Datadog In case you need IP whitelisting, the following IP ranges will give access to Cloudability : 185.115.88.0/22 103.195.128.0/22

---

## Connect Google Cloud

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Google Cloud
- **source_path:** SSVCLNQ/admin/connect-google-cloud.html
- **original_file:** cloudability-connect-google-cloud.md
- **images:**
  - 03-media/apptio-cloudability-standard/GCP1_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP2_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP3_Billing_Export.png
  - 03-media/apptio-cloudability-standard/GCP4_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP5_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP6_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP7_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP8_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP9_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP10_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP11_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP12_Billing_Export.jpg
  - 03-media/apptio-cloudability-standard/GCP13_Creds.png
  - 03-media/apptio-cloudability-standard/regenerate_cloudability_more_options.jpg
  - 03-media/apptio-cloudability-standard/setup_overview_guide_gcp-error-ok.jpg
  - 03-media/apptio-cloudability-standard/GCP14_Script.jpg
  - 03-media/apptio-cloudability-standard/GCP15_EditCredst.png

## Connect Google Cloud

Overview

This guide walks you through the process of connecting your Google Cloud Platform to IBM Cloudability. Cloudability supports

- GCP Standard Billing

- GCP Detailed Billing.

Once connected, you’ll gain access to the FinOps capabilities within Cloudability.

Prerequisites

- Cloudability uses IAM to create and manage custom roles

- Should have IAM permissions in GCP for creating a custom role

- Cloudability uses these custom roles with permissions specific to reading billing, commitments and pricing data. CloudabilityRole_Billing – for billing account CloudabilityRole_Buckets - for GCS bucket access CloudabilityRole_AdvancedFeatures – for projects

- Should have permissions to create a GCS bucket within GCP .
- The following permissions are required: bigquery.tables.export (export table data out of BigQuery) storage.buckets.getIamPolicy storage.buckets.get storage.buckets.list storage.multipartUploads.abort storage.multipartUploads.create storage.multipartUploads.list storage.multipartUploads.listParts storage.objects.create storage.objects.delete storage.objects.get storage.objects.list storage.objects.update

- Should be able to execute the GCP shell script in GCP console which will bind the role to Cloudability 's service account ( billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com ) as a member with the custom role at the billing-project level

- To be able to successfully run our script from within your cloud console, your gcloud user needs to be granted the following IAM permissions at the project level: iam.roles.create resourcemanager.projects.setIamPolicy resourcemanager.projects.getIamPolicy

- This gives customers complete control over, and visibility into, all actions taken by any entity assuming that role within their GCP projects.

- Admin access to the Cloudability Vendor Credentials

- Familiarity with GCP Organizations

- Familiarity with GCP Credentialing using Bulk Actions

- Access and ability to enable the Google Cloud Resource Manager API

Getting Started:

Cloudability’s GCP Credentialing process requires two main steps:

- GCP Billing Account Credentialing

- GCP Projects Credentialing (for Advanced features)

The GCP Billing Account Credentialing process involves a few steps which will require you to take actions in both GCP portal and Cloudability at various phases.

During this process Cloudability will use your billing Table ID and generate a script that contains gcloud IAM commands which will be required to be run in the GCP console.

- Check the IAM section of the appropriate project to determine whether you have these permissions.
- Enable the Google Cloud Resource Manager API
- Cloudability uses Google's Cloud Resource Manager API to test whether the necessary permissions have been granted to support the available features.
- Google's Cloud Resource Manager API provides many advantages at zero cost to you. You can read more about it at Resource Manager .
- A list of APIs made available via the Resource Manager can be found at Cloud Resource Manager API .

Credentialing the GCP Billing account

Step 1 - GCP Portal – Enable BigQuery export and Table ID

- In the GCP Console, under APIs & Services > Library , search for 'Cloud Resource Manager API' .
- From the Cloud Resource Manager API page, select ENABLE .
- Make sure that API enabled is ticked.

Working in the Google Console, type Billing in the search bar and when the results show select Billing accounts.

Select Billing export.

Select Edit Settings (based on the Type of Export you are putting in place.

Select the type of export you want to put in place – Standard or Detailed Billing – by clicking Edit Settings.

Select your Project where your Billing Data (likely your billing project) will be held and then click in Data Set and select Create a New Data Set.

Add a Dataset ID and click Create Data Set.

Select Save to complete the process.

- GCP Standard usage cost table name should be in this format gcp_billing_export_v1_<BILLING_ACCOUNT_ID> .

- GCP Detailed usage cost table name should be in this format gcp_billing_export_resource_v1_<BILLING_ACCOUNT_ID> .

Standard usage / Detailed usage cost table should have the below partitioning detail as mentioned in the below image.

After you have enabled the BigQuery export, it will take a few hours for the billing table to be created, after which you will be able to locate the Table ID.

You can find the billing Table ID by navigating to the project that contains the BigQuery export of your billing data, under Table info > Table ID .

You must specify a project and dataset to which the billing data will be exported, when you enable the BigQuery export for a Billing Account . A table is automatically created for you within the specified dataset. This table is referred to as the billing table and Cloudability’s Service Account must be able to read data from this table.

Create a storage bucket

A Storage bucket is required to copy data from the BQ table export into, for Cloudability to then retrieve this data.

Working in the Google Console ; type Cloud Storage in the Search bar and select it when it shows.

Click Create to create a Bucket.

Enter a name for your storage bucket (eg: cloudability-export and click Create).

When prompted keep defaults and click Confirm.

Bucket will be created.

Step 2 - Cloudability – Add Credentials details in Cloudability

Standard Billing with GCS

Once you’ve gathered the information listed above, you can enter it into Cloudability to update your GCP credential.

Cloudability will use this information to generate a Shell script. When the script is run from your Cloud Shell in the GCP Portal, it will create and grant rights for Cloudability via the custom role in order to provide access to the storage account.

- In Cloudability , navigate to
- Settings > Vendor Credentials > Add Datasource > GCP .
- Click Next
- Select GCP - the Add GCP Account panel opens.

Or

- Settings > Vendor Credentials > Ingress > GCP .
- Click Next
- Select GCP Standard Billing - t he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g. project:dataset.gcp_billing_export_v1_<BILLING_ACCOUNT_ID>
- Enter the GCS bucket name
- Enter Organization id (Recommended, helps in quick onboarding) GCP customers can quickly credential the projects in an automated way by using GCP organization . You will need to move any projects you created under "No organization" into your new organization resource. For instructions on how to move your projects, see Migrating projects into an organizational resource .
- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your next step as this will need to be uploaded into the GCP console

Standard Billing with BQ Streaming

- Settings > Vendor Credentials > Add Datasource > GCP .
- Click Next
- Select GCP - the Add GCP Account panel opens.

Or

- Settings > Vendor Credentials > Ingress > GCP .
- Click Next
- Select GCP Standard Billing - t he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g. project:dataset.gcp_billing_export_v1_<BILLING_ACCOUNT_ID
- Bucket name (Optional - can be left blank)
- Organization id (Recommended, helps in quick onboarding) GCP customers can quickly credential the projects in an automated way by using GCP organization . You will need to move any projects you created under "No organization" into your new organization resource. For instructions on how to move your projects, see Migrating projects into an organizational resource .

- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your next step as this will need to be uploaded into the GCP console

Detailed Billing with GCS (Recommended)

- Settings > Vendor Credentials > Add Datasource > GCP .
- Click Next
- Select GCP - the Add GCP Account panel opens.

Or

- Settings > Vendor Credentials > Ingress > GCP .
- Click Next
- Select GCP Detailed Billing - t he Add a Credential panel opens.
- Enter Complete table id which is combination of project, dataset, table e.g. project:dataset.gcp_billing_export_resource_v1_<BILLING_ACCOUNT_ID
- Enter the GCS bucket name .
- Enter the Detailed Billing Date . Note: This date indicates the month and the year from when you have detailed billing exports enabled. If you are doing this for the first time it is the current month as YYYY-MM.

- Organization id (Recommended, helps in quick onboarding) GCP customers can quickly credential the projects in an automated way by using GCP organization . You will need to move any projects you created under "No organization" into your new organization resource. For instructions on how to move your projects, see Migrating projects into an organizational resource .
- Click on generate setup script
- Click Download Script
- A GCP shell script template will be downloaded locally – save this in a secure place for your next step as this will need to be uploaded into the GCP console

Step 3 – Upload and run the GCP shell script

The script performs two steps: it first sets up a custom role within the billing project and then adds Cloudability’s Service Account as a member of the project, binding the custom role. This ensures that our Service Account can read data only from BigQuery tables within a billing project. We do not access BigQuery data in non-billing projects.

In case of GCS bucket, we follow the above process, export the BigQuery data into GCS via BigQuery export job and pull that data into Cloudability.

1. Custom roles setup

The script first creates custom roles within the billing project. The script attaches the permissions necessary to read billing data to the custom roles

## Example: Create billing custom role for my-billing-project-123 # Billing project ID is my-billing-project-123 gcloud iam roles create CloudabilityRole_Billing \ --project \ my-billing-project-123 \ --title \ "Cloudability Billing Role" \ --description \ "Allows Cloudability access to billing account data" \ --permissions \ bigquery.jobs.create,bigquery.tables.getData \ --stage=GA

2. Add Service Account as Member and Bind Custom role

Once the custom role has been created, the script adds Cloudability 's Service Account as a member of the billing project and binds the custom role to it.

## Example: Add Cloudability's Service Account as member of my-billing- project-123 # Billing project ID is my-billing-project-123 gcloud projects add-iam-policy-binding my-billing-project-123 \ --member serviceAccount:billing-data-service-acct@cloudability- credentials.iam.gserviceaccount.com \ --role 'projects/my-billing-project- 123/roles/CloudabilityRole_Billing'

3. GCS Bucket

If you are opting for GCP standard billing with GCS bucket or GCP detailed billing, a GCP GCS bucket must be configured. Cloudability will export data to this GCS bucket temporarily from the configured GCP BigQuery table to ingest this data to Cloudability. Once the data ingestion is complete Cloudability will delete the data from the bucket.

Note: Same GCP Payer Account IDs cannot be used in both standard and detailed billing at the same instance.

Run the script

Follow the below steps to run the script via the Cloud Shell within your cloud console. It does not matter from where within the Cloud Shell you run the script.

- Activate the Cloud Shell, select the icon and select Upload file . Choose the downloaded script from the file explorer and confirm.
- chmod +x <scriptname> to make the script executable
- Next, run the script in your Cloud Shell:

./ script-name

- Check for any errors. For example,

- If the script is successful, you will see a similar output to the following in your Cloud Shell:

Step 4 – Cloudability Verify credentials

- Select Verify Credentials .
- Select the refresh icon to update the status.

The green check-mark indicates that this billing account has been successfully credentialed.

You have now successfully added your billing account to Cloudability. We ingest data at regular intervals and your billing data will be available starting from the next ingest cycle. Upon the next ingest, we will also enumerate the projects associated with this billing account.

Lastly, if your organization has additional GCP billing accounts that you would like to add, then please repeat this process for each of those billing accounts.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and GCP labels within Cloudability.
- Retail Pricing data would also be pulled in, for enabling custom pricing please check Setting up Custom Pricing Support for GCP
- Cloudability will also display the projects.

As a next step you will need to credential the GCP projects.

GCP Projects Credentialing (Advanced features)

The purpose of this section is to help you walk through the process of credentialing your projects to enable Cloudability's Advanced Features. If your organization has multiple GCP projects, then this process must be repeated for each project for which you would like to enable Advanced Features.

Before you begin, make sure you’ve gone through the prerequisites

To credential your project:

- Add a new project credential, as described in Configure project-level credentials.
- Run the script, as described in Run the script .
- Familiarize yourself with GCP Credentialing using Bulk Actions

Add a new project credential

To enable Advanced Features for a GCP project:

- Navigate to Vendor Credentials , and select the GCP tab
- Select the Edit icon to open Edit a Credential panel.
- Select Update Credential.
- Select Download Script .
- If your browser prompts you with a warning, select Keep .

Run the script

For more information, see run the script section

How to confirm success

This can be done via bulk actions or manually.

- Bulk Verification via UI: GCP Credentialing using Bulk Actions

- Manual Verification via UI:

- Select Verify Credentials on each project .

- Select Details to verify that the project has the necessary permissions for Advanced Features. s

Frequently Asked Questions

The details provided on the Billing Export page differ from those on the BigQuery page for your Billing table.

Specifically, the Table ID on the BigQuery page is constructed using the Billing Project ID, while the Billing Export page lists the Billing Project Name. IDs are unique, while names are not.

Solution: Review prerequisites.

What to do if Project ID, Dataset, or Table ID is getting truncated?

Context: You enter your complete GCP Billing Table ID into and notice that there are errors. Additionally, when you edit the credential, you notice that the Project ID, Dataset, or Table ID are truncated. You might have retrieved or constructed your GCP Billing Table ID from the Billing Export page.

Solution: You must copy the complete Table ID from the BigQuery page for your Billing table.

How should I download updated template with latest permissions if there has been update of permissions?

Updated Template can be downloaded by editing the existing billing account and downloading the latest template for it. Once downloaded follow the credentialing steps mentioned after download of template.

[Script] Error: (gcloud.iam.roles.create) A resource in the project is a subject of conflict.

Context: This can occur when you have an existing role within your billing project with role_id CloudabilityRole_Billing. The error indicates that the script is unable to create a new role with role_id CloudabilityRole_Billing because one already exists.

Solution: Ignore this error.

[Script] Error: (gcloud.iam.roles.create) FAILED_PRECONDITION: You can't create a role with role_id (CloudabilityRole_Billing) where there is an existing role with that role_id in a deleted state.

Context: This can occur when you run the script after deleting an existing role from your billing project with role_id CloudabilityRole_Billing. The role could be in a deleted state and the script can't create a new role with that role_id. You can view the role's status (Enabled, Disabled, Deleted) in your cloud console.

Solution: Undelete the existing role with role_id CloudabilityRole_Billing from your billing project and re-run the script.

How to handle GCP Domain Restrictions?

If you have domain restrictions, then you might observe error messages. To overcome this, whitelist Cloudability to query the data by adding Cloudability 's GCP workspace customer id in their Organisation policy.

The domain is cloudability.com and the ID is C03n3dgoi

To view the complete SCUD enhancements in the Cloudability reporting UI for a GCP Payer account, which billing export should be used for credential setup?

The GCP Detailed Billing export is recommended, as it provides full visibility into over‑utilized and under‑utilized scenarios within Cloudability reporting.

How to migrate from GCP Standard Billing to GCP Detailed Billing?

- Set Up detailed billing in GCP Console
- If you have custom pricing , Configure the pricing export as well
- Credential the same account via detailed billing in Cloudability
- Verify the GCP account
- Once the projects are displayed , Enable advance features.

VPC Service Controls

Getting Recommendations Based on GPU Data

Prerequisites:

1. Each VM must have GPUs attached .

1. Each VM must have a GPU driver installed .

1. Each VM must have Python 3.6 or newer installed.

1. Each VM must have the packages required for creation of Python virtual environments installed.

- GCP Credentialing using Bulk Actions
- Permissions Reference - GCP
- Set up GCP Monitoring Agent for rightsizing
- Support for GCP Tags
- Setting up Custom Pricing Support for GCP
- Setting up Commitment Portfolio for GCP

---

## GCP Credentialing using Bulk Actions

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Google Cloud > GCP Credentialing using Bulk Actions
- **source_path:** SSVCLNQ/admin/gcp-credentialing-bulk-actions.html
- **original_file:** cloud-gcp-credentialing-using-bulk-actions.md
- **images:** []

## GCP Credentialing using Bulk Actions

Overview

Bulk Actions on Vendor Credentials screen allows admins to quickly complete the advance credentialing process within Cloudability.

1. Save multiple non credentialed accounts quickly
1. Bulk verify multiple accounts to complete the credentialing process in an easier and faster way.

Prerequisites

Instructions

Save New Credentials

1. This screen will not show up if there are no accounts configured using the GCP Organization ID

1. Select the accounts which are needed to be credentialed.
1. Click on Review Selection .
1. Click on Save.

1. Once Save is completed, the accounts will move to Unverified status.
1. Please download the GCP template from one of the accounts which was saved and apply it to the GCP accounts in the GCP console.
1. Once completed, please trigger verify credentials for the accounts selected in the previous step.

Verify Credentials

This screen displays all the accounts except the ones with Credentials Needed status (Red X).

1. Select the accounts which are needed to be verified.
1. Click on “Review Selection”
1. Click on Verify.

This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes.

---

## GCP Tags and Labels

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Google Cloud > GCP Tags and Labels
- **source_path:** SSVCLNQ/admin/gcp-tags.html
- **original_file:** cloud-gcp-tags-labels.md
- **images:**
  - 03-media/apptio-cloudability-standard/gcp-tags.png

## GCP Tags and Labels

- GCP Labels These are part of the GCP Billing data extract and no extra permissions are required within Cloudability for enabling these .Cloudability support below labels Resource labels Project labels System labels

- Resource

- Project
- System

- GCP Tags These are part of the GCP Billing data extract and no extra permissions are required within Cloudability for enabling these

GCP Tags are becoming popular tagging mechanism with large number of GCP customers for cost allocation and policy-based tagging. Cloudability now supports GCP Tags in addition to GCP Labels. Users can now use both of these in a variety of use cases.

For more information on GCP Tags, click https://cloud.google.com/resource-manager/docs/tags/tags-overview#inheritance

### Key changes for GCP Tag Mappings :

- Enhanced mapping options: You can now map costs using both GCP Tags (organization/folder level) and GCP Labels (resource level) for more comprehensive cost allocation.
- Hierarchical cost allocation: Map inherited tags to business units or departments, while using labels for project-specific allocations.
- Priority configuration: Set priority between GCP Tags and Labels in cases where both exist for the same cost dimension.

In order to use GCP Tags, customers would need to enable the GCP tags in GCP console. Once enabled, Cloudability while ingesting the billing data will also bring in the GCP Tags.

Once Ingested GCP Tags will appear as new tag dimensions in your Tag Mappings configuration in Tags and Labels page alongside existing GCP Labels. You will see them as below:

- cldy:gcp:tag:<tagkey> for direct tag assignments
- cldy:gcp:tag:<tag key>:inherited for inherited tags
- cldy:gcp:tag:<tagKey>:namespace for tag attachment level

![gcp tags](../images/gcp-tags.png)

GCP Tags then can be used in other features like Business Mappings, Views Tag explorer, Dashboards and reports to further drill down into various cost allocation scenarios.

### Troubleshooting

How do I prioritize between selection of GCP Labels vs GCP Tags?

GCP Tags and Labels both will be displayed in Cloudability's Tags and Labels page under the organize section. Currently the page follows a priority order based on the tags mentioned. If you already have GCP labels and want to give priority to GCP Tags then you'll need to remove the old GCP labels and add GCP tags as the first option, followed by labels. Once this is done, Reprocess is required to reflect this change in Cloudability reports and everywhere.

I have added a new GCP Tag, but I am unable to view the value associated with it in Cloudability, what might be the reason?

Please check the GCP Tag order as explained above. Please ensure that the GCP tags are given priority in the order of TAGS in the tags and labels page. In case of conflicts between GCP labels and GCP tags we'll check the priority order of Tags configured.

At the time of launch how many months of GCP tags would be available?

At the time of launch we'll start pulling the GCP tags data from the current month.

How can GCP tags be backfilled?

Customers would need to raise a GCP backfill case to request the backfilling of GCP tags. The internal Support or Engineering team will then need to trigger a refetch to load the data for the specified months.

How will Tag Explorer change with GCP Tags support?

Tag Explorer will now provide visibility into both GCP Tags and Labels, offering:

Enhanced Coverage Analysis:

- Dual-layer visibility : See both inherited GCP Tags and directly applied GCP Labels
- Inheritance tracking : Identify which costs are allocated through inherited tags vs. direct resource labeling
- Coverage gaps : Spot resources that lack either tags or labels for complete cost allocation

New Filter and Analysis Options:

- Tag source filtering : Filter by direct tags vs. inherited tags
- Hierarchy analysis : Understand cost allocation patterns across your GCP organization structure

---

## Set up GCP Monitoring Agent for rightsizing

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Google Cloud > Set up GCP Monitoring Agent for rightsizing
- **source_path:** SSVCLNQ/admin/gcp-memory-metrics.html
- **original_file:** cloud-set-up-gcp-monitoring-agent-rightsizing.md
- **images:** []

## Set up GCP Monitoring Agent for rightsizing

In order for Cloudability to utilize additional utilization metrics such as memory, you will need to configure the GCP Monitoring Agent. Cloudability supports both the Ops Agent and the Legacy Monitoring Agent. The following instructions detail ways on how to configure each agent:

1. Prerequisites To install the agent, ensure that all conditions are met. Installing the Ops Agent on individual VMs Installing the Legacy Cloud Monitoring agent on individual VMs
1. Install the agent using the command line To install the agent using the command line, use the following instructions. Installing the Ops Agent using the command line Installing the Legacy agent using the command line
1. Install the agent using the Google Cloud console You can install the agent on one or more Compute Engine VMs from the pre-configured Monitoring VM Instances dashboard. Installing the Ops Agent using the Google Cloud Console Installing the Legacy agent using the Google Cloud Console

---

## Setting up Commitment Portfolio for GCP

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Google Cloud > Setting up Commitment Portfolio for GCP
- **source_path:** SSVCLNQ/admin/commitment-portfolio-gcp.html
- **original_file:** cloud-setting-up-commitment-portfolio-gcp.md
- **images:**
  - 03-media/apptio-cloudability-standard/commitment-portfolio-3.jpg
  - 03-media/apptio-cloudability-standard/vc_ss6.jpg
  - 03-media/apptio-cloudability-standard/vc_ss7.jpg

## Setting up Commitment Portfolio for GCP

The Commitment Portfolio for GCP Spend-based commitments requires two additional permissions to populate beyond basic credentialing.

Before you start

You need to credential your account before following the steps to set up Commitment Portfolio. See Connect Google Cloud to credential your account.

Additional Permissions for Commitment Portfolio

Follow the below steps to set up credentials for additional permissions as mentioned above.

1. Sign into Cloudability , and then navigate to Settings > Vendor Credentials > GCP .
1. Find a Billing Account which has purchased GCP spend-based CUDs.
1. Hover over the ellipsis menu icon, and then click to select Edit a Credential .
1. Add your Organization ID.
1. Click Update Credential .

For more information on organizational resources, see Creating and managing organization resources .

Once the adjustment to credentialing is complete, the following new permissions are displayed under Master-Payer billing account Reservation section:

- consumerprocurement.orders.list

- consumerprocurement.orders.get

As part of the credentialing process, the next step is to create a new role under GCP organization scope. Apply this at the Billing Account scope along with the existing role at the Project scope with the BQ Table permissions for successful credentialing.

---

## Setting up Custom Pricing Support for GCP

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Google Cloud > Setting up Custom Pricing Support for GCP
- **source_path:** SSVCLNQ/product/gcp-rightsizing-custom-pricing-support.html
- **original_file:** cloud-setting-up-custom-pricing-support-gcp.md
- **images:**
  - 03-media/apptio-cloudability-standard/gcp-standard-billing-1.jpg
  - 03-media/apptio-cloudability-standard/gcp-standard-billing-2.jpg

## Setting up Custom Pricing Support for GCP

Custom pricing support is now extended to GCP for Cloudability so that contractual discounts and other customer specific pricing is applied to GCP rightsizing recommendations and Workload Planning .

1. Go to the GCP billing account.
1. Select Billing > Billing export .
1. Under Pricing , Click on “ Enable Pricing Export ”.
1. Select Pricing > Edit Settings .
1. Based on your choice of GCP Billing ( Standard Billing vs Detailed Billing ), you need to ensure the following: Select Project name and Dataset name same as Selected for “ Standard Usage Cost ” if you are using Standard Billing . Select Project name and Dataset name same as Selected for “ Detailed Usage Cost ” if you are using Detailed Billing .

---

## Connect IBM Cloud

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect IBM Cloud
- **source_path:** SSVCLNQ/product/apptio_help_center_ibm_cloud.html
- **original_file:** cloudability-connect-cloud.md
- **images:** []

## Connect IBM Cloud

It takes 4 to 24 hours before your initial cost and usage data appears in Cloudability. This depends on how long it takes IBM Cloud to generate your first billing reports.

Two ways to connect

1. Cloudability method: A Terraform script is provided for credentialing which would be API-key based.
1. Deployable Architecture (DA) app method: IBM Cloud supports a Deployable Architecture (DA) app called 'IBM Cloudability Enablement', using which you can credential your IBM Cloud account in Cloudability. This is the preferred method for credentialing IBM Cloud accounts as the app helps speed up the process.

---

## Setup IBM Cloud Credentials using Cloudability Method

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect IBM Cloud > Setup IBM Cloud Credentials using Cloudability Method
- **source_path:** SSVCLNQ/product/setup_ibm_cloud_credentials_using_cldy_method.html
- **original_file:** cloud-setup-credentials-using-cloudability-method.md
- **images:**
  - 03-media/apptio-cloudability-standard/ibm1.jpg
  - 03-media/apptio-cloudability-standard/ibm2.jpg
  - 03-media/apptio-cloudability-standard/ibm3.jpg
  - 03-media/apptio-cloudability-standard/ibm4.jpg
  - 03-media/apptio-cloudability-standard/ibm5.jpg
  - 03-media/apptio-cloudability-standard/ibm6.jpg
  - 03-media/apptio-cloudability-standard/ibm7.jpg
  - 03-media/apptio-cloudability-standard/ibm8.jpg
  - 03-media/apptio-cloudability-standard/ibm9.jpg
  - 03-media/apptio-cloudability-standard/ibm10.jpg
  - 03-media/apptio-cloudability-standard/ibm11.jpg
  - 03-media/apptio-cloudability-standard/ibm12.jpg
  - 03-media/apptio-cloudability-standard/ibm13.jpg
  - 03-media/apptio-cloudability-standard/ibm14.jpg
  - 03-media/apptio-cloudability-standard/ibm15.jpg
  - 03-media/apptio-cloudability-standard/ibm16.jpg
  - 03-media/apptio-cloudability-standard/ibm17.jpg
  - 03-media/apptio-cloudability-standard/ibm18.jpg
  - 03-media/apptio-cloudability-standard/ibm19.jpg
  - 03-media/apptio-cloudability-standard/ibm20.jpg
  - 03-media/apptio-cloudability-standard/ibm21.jpg
  - 03-media/apptio-cloudability-standard/ibm22.jpg
  - 03-media/apptio-cloudability-standard/ibm23.jpg
  - 03-media/apptio-cloudability-standard/ibm24.jpg
  - 03-media/apptio-cloudability-standard/ibm25.jpg
  - 03-media/apptio-cloudability-standard/ibm26.jpg

## Setup IBM Cloud Credentials using Cloudability Method

### Summary

Connect or credential your IBM Cloud accounts to Cloudability to enable the ingestion of cost and usage data. This document focuses on the Cloudability method and provides a step-by-step guide for setting up an IBM Cloud workspace using Terraform. The workspace will be used to deploy infrastructure using Terraform configurations hosted on a GitHub repository.

### Prerequisite

Enabling your IBM account to export usage data

Before you can enable your IBM account to export usage data, you need to have administrator or editor role on the Billing account management service. For more information, see IAM access .

1. From the IBM Cloud console, go to Manage > Billing and usage , and select Settings .
1. Click Connect .
1. Select a Cloud Object Storage instance and Bucket . By selecting these, you are choosing which bucket will store your usage reports. Optional: If you don't want to select an existing instance, click Select an instance > Create new . Optional: Select a bucket or create a new bucket by clicking Create new bucket from the dropdown. For more information, see Getting started with IBM Cloud Object Storage .
1. For service to service authorizations, click Authorize . For the required access, select Object Writer and Content Reader . Click Review and then Assign .
1. Click Connect after you review your folder details.

Reference: Exporting your usage data for continual insights

Copy Account Details for account where Enterprise is configured

1. Navigate to Manage .
1. Select Enterprise from the dropdown.
1. Access Dashboard and locate the ID field.

1. Navigate to Manage .
1. Click Enterprise from the dropdown and then select Accounts .
1. Identify the account labeled as 'This account is the enterprise account' and copy its ID.

Copy Account Details for Account where Enterprise is not configured

1. Navigate to Manage .
1. Click Account from the dropdown and then select Account Settings .
1. Copy its ID.

1. Access the IBM Cloud navigation menu.
1. Go to Resource List and select Storage .
1. Choose the Cloud Object Storage instance that contains the Bucket where the Usage Report is exported.

1. Access the IBM Cloud Navigation Menu.
1. Go to Resource List , select Storage and then choose Storage Instance .
1. Find the Buckets section and select the Bucket where the Usage Report is exported.
1. Navigate to Configuration and copy the Bucket Name and Location (Region).

1. Access the IBM Cloud Navigation Menu.
1. Go to Resource List , select Storage and then choose Storage Instance .
1. Find the Buckets section and select the Bucket where the Usage Report is exported.
1. Access the IBM Cloud Navigation menu and select the Bucket where the Usage Report is exported.

Copy the prefix located between the Bucket Name and the folder name (containing year and month; e.g., 2023-10), excluding both the Bucket Name and the Year-Month folder name.

1. Access the IBM Cloud Navigation Menu.
1. Go to Resource List , select Storage and then choose Storage Instance .
1. Find the Buckets section and select the Bucket where the Usage Report is exported.
1. Access the IBM Cloud Navigation menu and select the Bucket where the Usage Report is exported.
1. Navigate to any Year-Month folder and copy the file name named 'manifest' (the default file name is manifest). Note: Do not copy the file name extension. It should be just ‘manifest’ and not manifest.json.

### Generate Terraform Template from Cloudability

1. Ensure all details are copied and readily accessible.
1. Login to Cloudability UI and navigate to Settings: Vendor Credentials: Click ‘Add Datasource’ and select 'IBM'.
1. Under Add IBM Account side panel, click Next .
1. Enter all the details copied earlier and click Generate Template . Note: Cost Report Name should not have the filename extension (.json).

### Executing the Terraform

1. Ensure that Terraform has been downloaded and is hosted on a repository such as GitHub. Note: If your GitHub repository is private, you will need to generate a Personal Access Token (PAT) as described here.
1. Also, make sure that you have Account Owner or Manager Service access and Administrator Platform access for Schematics Service in your IAM Access.

Steps for Execution

Step 1: Login to IBM Cloud

1. Navigate to the IBM Cloud login page.
1. Enter your IBM Cloud credentials and log in to your IBM Cloud account.

Step 2: Access Schematics and Create a Workspace

1. After logging in, access the Navigation menu within IBM Cloud.
1. From the Navigation menu, select Schematics .
1. Click Workspaces to access the workspace management interface.

Step 3: Configure the Workspace

1. Click Create Workspace to initiate the workspace creation process.
1. Provide the GitHub repository URL where your Terraform configuration files are hosted.
1. If your GitHub repository is private, provide the Personal Access Token (PAT) that you generated during the prerequisites. Reference: Managing your personal access tokens
1. Select the latest Terraform Version, in this case, terraform_v1.5 . Note: Terraform version should be v1.5 and above.
1. Click Next to proceed.

Step 4: Define Variables

1. Provide a name for your workspace, e.g., 'CldyWorkspace'.
1. Under Tags , add a tag named "createdFor" with the value 'Cldy'.
1. Leave the Resource Group as 'Default'.
1. Choose a location for your workspace, as it determines where workspace actions will be executed.
1. Description is optional.
1. Click Next to continue.

Step 5: Apply the Terraform Plan

1. Click Create to confirm and create the workspace.
1. Your CldyWorkspace will be created.

Step 6: Access Created Resources

1. Select 'CldyWorkspace' from the list of workspaces.
1. Navigate to Settings for 'CldyWorkspace'.
1. From the Variables section, expand three dots (ellipsis), and select Edit .
1. Your CldyWorkspace will be created. Provide your ibmcloud_api_key, which must have the necessary access to create IAM resources. Reference: Managing user API Keys
1. Select Sensitive checkbox if you want to treat this variable value as sensitive or secret information. This prevents it from being exposed in workspace details, CLI output, or log output.
1. After configuring the variables, return to 'CldyWorkspace' and go to the Jobs section.
1. Click Apply plan to initiate the deployment of Terraform configuration.
1. Once Apply plan is successful, you can access the resources that were created in the Manage section.
1. Custom Roles can be found under Access (IAM) > Roles .
1. This concludes you have successfully deployed resources and can manage access and roles as needed .

Step 7: Verify Credentials in Cloudability

1. Once terraform plan is applied successfully, come back to the Cloudability UI and click Verify Credentials . The green check mark indicates that the credentialing process has been successful. Verify Credentials via Bulk Actions In order to Verify multiple accounts quickly, click on Bulk Actions button. This screen displays all the accounts except the ones with Credentials Needed status (X). Select the accounts which are needed to be verified. Click on Review Selection Click on Verify. This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes. Once completed, the accounts will move to either a Verified Credentialed status or Invalid Credential status (because of errors). Note: In case the number of accounts is huge this might take a few minutes. Sample Terraform Script (Expandable Header)

---

## Setup IBM Cloud Credentials using Deployable Architecture (DA) App

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect IBM Cloud > Setup IBM Cloud Credentials using Deployable Architecture (DA) App
- **source_path:** SSVCLNQ/product/setup_ibm_cloud_credentials_using_da_method.html
- **original_file:** cc-setup-cloud-credentials-using-deployable-architecture-da-app.md
- **images:** []

## Setup IBM Cloud Credentials using Deployable Architecture (DA) App

The Deployable Architecture (DA) App , also known as IBM Cloudability Enablement , provides an alternative and streamlined way to connect your IBM Cloud account to Cloudability. This app simplifies the setup process and is the recommended method for faster credentialing. The DA App is available in the IBM Cloud Public Catalog . To learn more about its architecture and how to configure and deploy it, see the Cloudability Enablement DA App documentation .

Using this method to credential your IBM Cloud account in Cloudability is completely optional.

To get help and support for IBM Cloudability Enablement using DA App, visit: Getting help and support for IBM Cloudability Enablement

---

## Connect Jira Cloud

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Jira Cloud
- **source_path:** SSVCLNQ/admin/connect-jira-cloud.html
- **original_file:** cloudability-connect-jira-cloud.md
- **images:** []

## Connect Jira Cloud

This article explains how to set up Jira Cloud in Cloudability.

Before you start

- Your organization uses Jira Cloud (and not Jira Server).
- You are a Cloudability administrator.
- The administrator for your Jira instance is available during the setup process.
- You have the site name for your Jira instance.

Steps for integration

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > JIRA .
1. The Add JIRA Account panel opens.
1. Enter the name of Base URL.
1. Select Save .

1. Log in to your Jira Cloud instance as an admin.
1. Select Settings > Add-ons .
1. Select Find new add-ons .
1. Search for 'Cloudability'.
1. Select Install .
1. Select Accept & install . Wait for the installation to complete.

How to confirm success

Check the status under Settings > Vendor Credentials .

---

## Connect Microsoft Azure

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure
- **source_path:** SSVCLNQ/admin/azure-cm-setup.html
- **original_file:** cloudability-connect-microsoft-azure.md
- **images:**
  - 03-media/apptio-cloudability-standard/azure-turbonomic-integration.jpg

## Connect Microsoft Azure

To configure the Cloudability credentials to access Azure cost management data by exporting a CSV file from the Azure Portal. The CSV file captures cost and usage data and saves it to Azure storage. The user is then provided the Cloudability access to that storage to read the data.

1. Set up cost management. Set up CSV formatted billing data to be automatically exported to Azure storage on a daily basis. Connecting with Azure (MCA) - Cost Management Exports Connecting with Azure (EA) - Cost Management Exports Connecting with Azure (MCA) - Cost Details API Connecting with Azure (EA) - Cost Details API
1. Enable rightsizing and RI planning Provide Cloudability with information about your billing data setup from your Azure Portal. Setup Azure Rightsizing and RI Planning
1. Enable collection of memory metrics Provide Cloudability read-only access to the cost & usage data on your Azure storage. Setup Azure Memory Metrics Collection

- tenant id
- subscription id
- resource group name
- storage account name
- container name
- directory name
- cost export name
- amortized export name

Before you start

Before you begin to set up the Cloudability credentials, confirm that you are a Cloudability Administrator and meet the following requirements.

- Global Administrator
- Application Developer
- Cloud Application Administrator
- Azure Savings Plan Reader (For Cloudability Premium customers)

For the Azure portal, you must have permissions provided by one of these Azure scopes to create the billing data export.

- Owner (can view/manage everything, including cost configuration)
- Contributor (can view/manage everything, including cost configuration, excluding access control)
- Cost Management Contributor (can view/manage cost configuration) Note: In order to successfully apply the “Enrollment Reader” permission to the IAM role (required for advanced features such as Savings Plans and Reserved Instance Planning), the user account running the power shell script must be at least of “Enrollment Writer” role them self under EA. For Azure Storage accounts:
- You must have "write" permissions to change the configured storage account (regardless of permissions on the export).
- The storage account must be configured for blob or file storage. If possible, Cloudability you must create a new storage account dedicated to cost management data.

For Azure Savings Plan Reader role:

1. Sign in to the Azure portal with a user account that has permissions to assign roles to savings plans https://portal.azure.com . Be sure that you are working in the correct Azure directory where you will assign the Savings Plan Reader role.
1. Browse to the Savings plans page: https://portal.azure.com/#view/Microsoft_Azure_Reservations/ReservationsBrowseBlade/productType/SavingsPlan
1. In the Savings Plans page, choose Role Assignment .
1. In the Access Control page, choose Add Role Assignment .
1. In the Add Role Assignment page: Choose the Role tab. In the search bar, type Savings Plan Reader as your search keyword. Choose Savings Plan Reader from the list of built-in roles that display and then choose Next. In the Members tab, choose + Select members . Search for the CloudabilityUtilizationDataCollector service principal. Add the service principal. Optionally, specify a description for this role assignment and then choose Next . In the Review + Assign tab, review your settings and then choose Review + Assign .

Upon upgrading to Cloudability Premium , the Billing Reports and Advanced Reports status for each of the Azure (EA or MCA) accounts in the listing page will not change. However, your Cloudability admin needs to edit each account following the steps enabling Cloudability share these accounts with Turbonomic .

1. Click Optimize Resources in the toggle button.
1. Generate setup script.
1. Update the permissions by executing the script.
1. Re-verify the account.

There are additional Turbonomic permissions that gets added to basic (Billing Data), advanced (Utilization Data) and Optimize Resources (execute actions) which are documented in the help center documents. Once your account is verified, the list of permissions can be viewed by choosing the Details option on each Azure account listed under Cloudability.

---

## Azure Tags

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure > Azure Tags
- **source_path:** SSVCLNQ/admin/azure-resource-group-tags.html
- **original_file:** azure-tags.md
- **images:** []

## Azure Tags

Cloudability supports the below mentioned types of tags for Azure

- Resource level tags These are part of the Azure Export files and no extra permissions are required within Cloudability for enabling these Tags format - cldy:Azure:ResourceTag:<resource tag key>
- Resource group tags To get Resource group tags from Azure, Cloudability needs an additional permissions either management:Reader or Microsoft.Resources/subscriptions/resourceGroups/read on the subscriptions Tags format - cldy:Azure:ResourceGroupTag:<resource group tag key>
- Subscription level tags To get subscription level tags from Azure, Cloudability needs an additional permission subscription:ReadSubscription Tags format - cldy:Azure:SubscriptionLevelTag:<subscription tag key>

Task : Enable access to resource group tag information to support cost allocation activities.

Using Azure resource group tags has become a popular primary allocation mechanism with large number of Azure users. It overcomes the duel problems of low tag coverage and the fact that Azure doesn't report back tag information for all resource types. Resource group tags don't natively appear in the detailed billing information and therefore, it's necessary to grant additional access as specified on this page.

Cloudability has a tag inheritance model for Azure: if an individual resource has a particular tag in the detailed billing data, we'll use that first to populate our analytics platform. If that tag doesn't appear in the billing data for that resource, Cloudability will then query the resource group it belongs to and pull the tag information from there. If the tag doesn't exist in the resource group, we'll consider it as "(not set)."

To enable the collection and processing of resource group tags, follow the steps here to credential your subscriptions.

---

## Connecting with Azure EA - Cost Management Exports

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure > Connecting with Azure EA - Cost Management Exports
- **source_path:** SSVCLNQ/admin/azure-cm-exports-ea.html
- **original_file:** azure-connecting-ea-cost-management-exports.md
- **images:**
  - 03-media/apptio-cloudability-standard/blobid1.jpg
  - 03-media/apptio-cloudability-standard/blobid0.jpg
  - 03-media/apptio-cloudability-standard/blobid5.jpg
  - 03-media/apptio-cloudability-standard/new-create_a_new_csv_export.jpg
  - 03-media/apptio-cloudability-standard/updated_new_import.jpg
  - 03-media/apptio-cloudability-standard/Azure-EA-Enrollment-id.png
  - 03-media/apptio-cloudability-standard/updated_tenant_id.jpg
  - 03-media/apptio-cloudability-standard/resource_group_name.jpg
  - 03-media/apptio-cloudability-standard/updated_storage_account.jpg
  - 03-media/apptio-cloudability-standard/blobid9.jpg
  - 03-media/apptio-cloudability-standard/clip_image001_-1832790195.png
  - 03-media/apptio-cloudability-standard/clip_image002_-821243953.png

## Connecting with Azure EA - Cost Management Exports

Overview

This guide walks you through the process of connecting your Microsoft Enterprise Agreement (EA) to IBM Cloudability via Azure Cost Management Exports.

Azure Cost Management Exports provide a granular detail containing all the raw billing and usage data behind your Azure costs and resource tags. Cloudability requires a couple of files for this integration:

- Cost and usage details (actual)

- Cost and usage details (amortized)

Once connected, you’ll gain access to the FinOps capabilities within Cloudability.

Prerequisites

Before you begin,

- Global Administrator or Enterprise administrator.
- Enrollement Writer or equivalent role to assign the Enrollment reader role

For the Azure portal, you must have permissions provided by one of these Azure scopes to create the billing data export.

- Owner (can view/manage everything, including cost configuration)

- Contributor (can view/manage everything, including cost configuration, excluding access control)

- Cost Management Contributor (can view/manage cost configuration)

- Admin access to the Cloudability Vendor Credentials

Getting Started:

Cloudability’s Azure Credentialing process requires two main steps:

- Azure Billing Account Credentialing

- Azure Subscription Account Credentialing

Azure Billing Account Credentialing process involves a few steps which will require you to take actions in both Azure portal and Cloudability at various phases.

During this process Cloudability will

- Add Cloudability’s Service Principal “CloudabilityUtilizationDataCollector” and assign “CloudabilityCostDataReader” role to it.

- CloudabilityCostDataReader role is used for getting the cost and usage data using the Azure built in Storage Blob Data Reader role .

- Uses Enrollment Reader role which provides read-only access to enterprise billing data

Step 1 - Azure Portal - Create an Azure Cost Details Export

Microsoft Azure also recommends using exports as a best practice for large datasets (more than 2 GB month-to-month).

1. From the Azure Portal, search for Cost Management + Billing , and select it from the list to open the Billing Scopes page. For example:
1. From the Cost Management + Billing page, ensure you have selected the correct Billing Scope. If you have multiple, select the scope with the majority of your cloud spend.
1. From the Cost Management + Billing console, select Exports from the navigation panel to open the Azure export utility.
1. Select Create to open the export page for creating a new CSV export.
1. Create a new export for Cost and Usage (actual) : Type of data: Cost and Usage (actual) Create an export prefix e.g.: Cloudability, then click on the cldy-actual-cost to reveal: Export name: Customer Defined Unique File Name Dataset version: 2021-10-01 Frequency: Daily export of month to date costs Export Description: Optional Click Save Click Next to open Destination tab Storage type: Azure blob storage Destination and storage: Select to use an existing subscription and resource group or create new Subscription: Select destination subscription Storage account: Select storage account Container: Enter a valid container name meeting your naming standards Directory: Enter a valid directory name meeting your naming standards Format: CSV Compression Type: None or Gzip File partitioning: Retain the default selection Overwrite data: Retain the default selection Click Next On the Review and Create tab, Click Create Cost and Usage (amortized) : Follow same steps as above Ensure that the same subscription, storage account container and directory are used as in the previous Export creation Click Review and Create Note: Both CSV formatted files are required by Cloudability and must be present in the storage account used to collect cost management data. We don't recommend FOCUS data ingestion for Azure as the native Azure Cost Management Exports provide much more granular information.
1. Ensure the below setting are applied for the Storage account configured for exports: Navigate to Storage Accounts and select your Storage Account used for Cloudability Select Security + Networking Select Networking Click Manage Under Public Network Access, select Enable Under Public network access scope select either of the below Enable from all networks, or Enable from selected networks In this case, contact Cloudability support to obtain a range of IPs which can be whitelisted Click Save Select Security + Networking Select Encryption Click Encryption scopes Provide an encryption scope name Encryption type Microsoft managed keys (MMK) Infrastructure encryption Enabled or Disabled Click Create
1. Gather billing data information for your Cloudability credential setup After you've created your billing data exports, Cloudability needs additional information from your Azure Portal for the Cloudability credential setup which is called out below: You can find the list of all properties Cloudability needs in the Azure Portal Cost Management console:

| Property Name | How to find it |
| --- | --- |
| Enrollment ID | Search for Cost Management + Billing and select it from the list to open the Cost Management + Billing Overview page. Select Billing Scopes and click the billing scope Navigate to Settings, click on properties, copy and save your Billing account ID ( Enrollment ID) |
| Tenant ID | Search for Microsoft Entra ID and select it to load the Active Directory Overview page. Copy and save the Tenant ID |
| Subscription ID | Search for Subscriptions and select it to open up the subscriptions page From the list of subscriptions under the same billing account select the subscription Copy the Subscription ID where the exports were created and save it. |
| Resource group name | From the storage account Overview page, click the storage account link to view the Resource group name as in this example: |
| Storage account name Container name Directory name Cost export name Amortized export name | Search for Cost Management + Billing and select it Navigate to Exports under settings to display a table with your billing data storage account. Scroll to the right and select the storage account for your billing data to open the Overview page, where you can view the Storage account name, Storage container name, Storage directory name, both the actual cost export and amortized cost export file names: |

Step 2 - Cloudability - Credential using the billing data information

Once you’ve gathered the information listed in the table, you can enter it into Cloudability to update your EA credential.

Cloudability will use this information to generate a PowerShell script. When the script is run from your Cloud Shell in the Azure Portal or from local PowerShell scoped to your tenant, it will create Service Principal and grant rights for Cloudability via the CloudabilityCostDataReader role in order to provide access to the storage account.

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > AZURE . Click Next Select Enterprise Agreement (EA) - the Add AZURE Account panel opens. Or Settings > Vendor Credentials > Ingress > AZURE . Click Next Select Enterprise Agreement (EA) - t he Add a Credential panel opens.
1. Enter the information gathered from your Azure Portal into the corresponding fields Enter the Azure Enrollment ID (Billing Account ID) Tenant ID Subscription ID Resource Group Name Storage account Name Container Name Directory Name Cost Export Name Amortized Cost Export Name
1. Select Generate Setup Script to download the new script file.
1. Select Close .

You will return to verify the changes later.

STEP 3 - Azure Portal - Grant Cloudability access from the Azure Portal

The next step is to grant Cloudability access to read the cost and usage data from your Azure storage by running the setup script in your Azure Portal Cloud Shell.

1. Log in to the Azure Portal and switch to the required tenant (the directory that is the at highest level in Azure for the target enrollment and where your Cost Management Exports are written).
1. From the Azure Portal, launch the Cloud Shell and select PowerShell as the scripting language.
1. After the Cloud Shell has initialized, select Upload from the Cloud Shell terminal menu.
1. Upload the setup script file provided by Cloudability.

![](../images/blobid9.jpg)

1. Run the script by typing: ./<YOUR_SCRIPT_NAME_HERE>.ps1

Step 4 - Cloudability - Verify the Account Credential

1. Return to the Cloudability credentials Azure page at Settings > Vendor Credentials> AZURE .
1. Select the three dots on the right hand side and select Edit next to your EA credential.
1. Select Verify Credential in the panel that open.
1. Click on the … next to the account being credentialed and select Re-Verify.

A green tick ( ) indicates success where as a red exclamation ( ) indicated errors.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and Azure tags within Cloudability.
- Pricing data would also be pulled in.
- Cloudability will also display the Subscriptions

As a next step you will need to credential the Subscriptions.

Click here to Set up Azure Rightsizing and Reserved Instance Planning for credentialing the Azure Subscriptions

1. I recently turned on the Azure Cost Management Exports and credentialed in Cloudability. How long will it take to see the data in Cloudability? Please refer the cost and usage data availability documentation
1. Azure Exports vs Azure Cost details API, which one should be used for integrating Azure in Cloudability? Using Azure exports is the Microsoft recommended way. This is a scalable approach as when your data set grows exports are able to handle bigger datasets. Azure cost details API can be used for smaller data sets.
1. Can we ingest historical cost data in Cloudability? If yes, how far back data can be ingested Yes, we can via One time Exports. Please check with IBM Cloudability Support teams on how to bring in Historical data.
1. Can FOCUS format be used instead of Azure exports for integration? No. For correct integration into Cloudability and bringing in things such as Rightsizing and Reserved Instance and Savings Plan Azure data we recommend using exports as it provides much more granular information.
1. Where Can I find Cloudability's Vendor Credentials APIs for Azure Please refer : Vendor Credentials End Points Azure
1. Do you support cost export on Billing Profiles /Departments Yes we can – Contact IBM Cloudability Support team for more information.
1. What are the guidelines for switching from EA to MCA ? Since EA to MCA is a contract change which also changes the Billing account id, Customers need to credential the MCA account as new Billing account and follow the credentialing steps. Please follow the credentialing script as the roles between EA and MCA changes for the billing account scope The subscription IDs should not change, only the Billing account changes Once basic credentials are completed the Billing exports would be picked up and the subscriptions would be populated subsequently. Azure EA data would be displayed until the date EA account had data. After the switch (and credentialing MCA) new data will be pulled via MCA account. EA account after successful switch and validating the cost can be archived. (optional)

---

## Connecting with Azure EA – Cost Details API

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure > Connecting with Azure EA – Cost Details API
- **source_path:** SSVCLNQ/admin/azure-cmapi-ea.html
- **original_file:** azure-connecting-ea-cost-details-api.md
- **images:**
  - 03-media/apptio-cloudability-standard/Azure-EA-Billing-id.png
  - 03-media/apptio-cloudability-standard/copy-tenant-id.png
  - 03-media/apptio-cloudability-standard/copy-subscription-id.png
  - 03-media/apptio-cloudability-standard/Azure-EA-Cost-Details-API.png
  - 03-media/apptio-cloudability-standard/Azure-PowerShell-Upload.jpg
  - 03-media/apptio-cloudability-standard/clip_image001_-1832790195.png
  - 03-media/apptio-cloudability-standard/clip_image002_-821243953.png
  - 03-media/apptio-cloudability-standard/CLDY-Vendor-Creds-Azure-Verified.png

## Connecting with Azure EA – Cost Details API

Overview

This guide walks you through the process of securely connecting your Azure EA environment to IBM Cloudability via Azure Cost Details APIs.

Cost Details API is an alternate credentialing mechanism for Azure Customers. Once connected, you’ll gain access to the FinOps experience in Cloudability. In this process we’ll create a Service Principle within your Azure account which will help Cloudability pull the Billing data.

To ensure full compatibility and support, please follow the connection steps as described. Custom configurations are not supported. If you have questions, reach out to IBM Support .

Prerequisites

Before you begin, ensure you have access to:

- Azure EA Portal

- Enterprise Admin (or a minimum of Enrollment Writer, or your organizations equivalent) role in Azure

- Administrator access to Cloudability Vendor Credentials page

Cloudability’s Azure Cost Details API Credentialing process requires 2 main steps:

- Billing Account Credentialing

- Subscription Credentialing

Billing Account Credentialing

Cloudability uses Billing Account credentialing for bringing in the Azure Cost and Usage data, resource level, resource group tags for credentialed Billing Account(s).

The credentialing process involves a few steps which will require you to take actions in both Azure Portal and Cloudability at various phases.

Let’s get started with the Credentialing process:

1. In the Azure Portal : Locate your Billing account ID (Enrollment ID). Search for Cost Management + Billing and select it from the list to open the Cost Management + Billing Overview page. Select the billing scope Navigate to Settings, Click on properties, copy and save your Billing account ID (Enrollment ID). Locate your Tenant ID Search for Microsoft Entra ID and select it to load the Active Directory Overview page. Copy and save the Tenant ID Get your S ubscription ID From the list of subscriptions under the same billing account. Copy one of the Subscription ID and save it.
1. In Cloudability - Configure Credentials for Azure Billing Account You must have Cloudability Administrator rights to complete this procedure. If you don’t have administrator rights, contact your organization’s primary Cloudability administrator for assistance. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource and select Azure - EA Enter the Azure Enrollment ID (Billing Account ID), Tenant ID and Subscription ID. Enter “ NA ” in all other fields. Click on Generate Setup Script. A PowerShell Script will be downloaded.
1. In Azure Portal - Upload the PowerShell script The next step is to grant Cloudability access to read the cost and usage data from your Azure storage by running the setup script in your Azure Portal Cloud Shell Execute the PowerShell script in the PowerShell console (or natively) To run the script: Log in to the Azure Portal and switch to the required tenant From the Azure Portal, launch the Cloud Shell and select PowerShell as the scripting language. After the Cloud Shell has initialized, select Upload from the Cloud Shell terminal menu. Upload the setup script file provided by Cloudability. Run the script by typing: Note: >: ./<YOUR_SCRIPT_NAME_HERE>.ps1 This PowerShell script will create a Service Principle called as “ CloudabilityUtilizationDataCollector ”. It will also assign a role called as Enrollment reader to the billing account which is used to access the Cost Details API by Cloudability.
1. In Cloudability - Verify the Billing account credential In Cloudability , navigate to Settings > Vendor Credentials > Azure. Click on the … next to the account being credentialed and select Re-Verify. A green tick ( ) indicates success whereas a red exclamation ( ) indicated errors

In the event that verification fails, please retry after 15 minutes.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and Azure tags within Cloudability.
- Pricing data would also be pulled in.
- Cloudability will also display the Subscriptions

As a next step you will need to credential the Subscriptions.

Subscription Account Credentialing

As a next step please continue to the Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning instructions. Putting these permissions in place will help bring in the Azure subscription tags and utilisation data which helps in using the Optimize features of Cloudability.

Frequently Asked Question’s

1. I don’t see any cost data after completing the account credentialing steps, what should be done? Please check if the account is successfully verified (shows a green tick mark). If it does wait for 24 hours for the data else reach to Cloudability support team. If the account is not verified (shows red!), Please check the configurations again and confirm all details are accurate AND that the script has been executed in your environment.
1. I recently turned on Azure and credentialed the accounts in Cloudability. How long will it take to see the Cost and Usage data? It may take up to 24 hours for your first Cost data to get displayed in Cloudability.
1. How do I update to the latest PowerShell template for permissions? This can be done using Cloudability Manage Azure credentials. To regenerate the PowerShell template to reconfigure your Azure access, do the following: In Cloudability , navigate to Settings > Vendor Credentials > Azure . Save and download the current PowerShell template. In Azure Portal, install the template. On successful update, re-verify the account.
1. Can we ingest historical cost data in Cldy? If yes, how far back data can be ingested? Yes, we can. Cost details APIs allows data to be fetched for 13 historical months. For requirements around historical data please raise a support ticket.
1. When should I use Cost details API for Azure. Cost details API for Azure is recommended for smaller datasets, preferably less than 2GB.
1. At first credentialing how much historical data Cloudability will bring in? Cloudability will bring current and previous months cost data.
1. How do I migrate from Azure Cost Details API to Azure Details Exports? This would require re credentialing of accounts. Please follow the credentialing steps for Azure exports.
1. Is changing of the content of the PowerShell script generated by Cloudability recommended? This is not recommended as an approach as for Cloudability to function correctly it needs the service principle and the roles assigned within the PowerShell script. Any changes to the script are unsupported.
1. What are the guidelines for switching from EA to MCA ? Since EA to MCA is a contract change which also changes the Billing account id, Customers need to credential the MCA account as new Billing account and follow the credentialing steps. Please follow the credentialing script as the roles between EA and MCA changes for the billing account scope The subscription IDs should not change, only the Billing account changes Once basic credentials are completed the Billing data would be picked up and the subscriptions would be populated subsequently. Azure EA data would be displayed until the date EA account had data. After the switch (and credentialing MCA) new data will be pulled via MCA account. EA account after successful switch and validating the cost can be archived. (optional)

---

## Connecting with Azure MCA - Cost Management Exports

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure > Connecting with Azure MCA - Cost Management Exports
- **source_path:** SSVCLNQ/admin/azure-cm-exports-mca.html
- **original_file:** azure-connecting-mca-cost-management-exports.md
- **images:**
  - 03-media/apptio-cloudability-standard/blobid1.jpg
  - 03-media/apptio-cloudability-standard/blobid0.jpg
  - 03-media/apptio-cloudability-standard/blobid5.jpg
  - 03-media/apptio-cloudability-standard/new-create_a_new_csv_export.jpg
  - 03-media/apptio-cloudability-standard/updated_new_import.jpg
  - 03-media/apptio-cloudability-standard/Azure-EA-Enrollment-id.png
  - 03-media/apptio-cloudability-standard/updated_tenant_id.jpg
  - 03-media/apptio-cloudability-standard/resource_group_name.jpg
  - 03-media/apptio-cloudability-standard/updated_storage_account.jpg
  - 03-media/apptio-cloudability-standard/blobid9.jpg
  - 03-media/apptio-cloudability-standard/clip_image001_-1832790195.png
  - 03-media/apptio-cloudability-standard/clip_image002_-821243953.png

## Connecting with Azure MCA - Cost Management Exports

Overview

This guide walks you through the process of connecting your Microsoft Customer Agreement (MCA) to IBM Cloudability via Azure Cost Management Exports.

Azure Cost Management Exports provide a granular detail containing all the raw billing and usage data behind your Azure costs and resource tags. Cloudability requires a couple of files for this integration:

- Cost and usage details (actual)

- Cost and usage details (amortized)

Once connected, you’ll gain access to the FinOps capabilities within Cloudability.

Prerequisites

Before you begin,

- Global Administrator or Enterprise administrator.
- Billing Account Owner or equivalent role to assign the Billing account reader role

For the Azure portal, you must have permissions provided by one of these Azure scopes to create the billing data export.

- Owner (can view/manage everything, including cost configuration)

- Contributor (can view/manage everything, including cost configuration, excluding access control)

- Cost Management Contributor (can view/manage cost configuration)

- Admin access to the Cloudability Vendor Credentials

Getting Started:

Cloudability’s Azure Credentialing process requires two main steps:

- Azure Billing Account Credentialing

- Azure Subscription Account Credentialing

Azure Billing Account Credentialing process involves a few steps which will require you to take actions in both Azure portal and Cloudability at various phases.

During this process Cloudability will

- Add Cloudability’s Service Principal “CloudabilityUtilizationDataCollector” and assign “CloudabilityCostDataReader” role to it.

- CloudabilityCostDataReader role is used for getting the cost and usage data using the Azure built in Storage Blob Data Reader role .

- Uses Billing Account Reader role which provides read-only access to billing data

This needs to be done manually .

Step 1 - Azure Portal - Create an Azure Cost Details Export

Microsoft Azure also recommends using exports as a best practice for large datasets (more than 2 GB month-to-month).

1. From the Azure Portal, search for Cost Management + Billing , and select it from the list to open the Billing Scopes page. For example:
1. From the Cost Management + Billing page, ensure you have selected the correct Billing Scope. If you have multiple, select the scope with the majority of your cloud spend.
1. From the Cost Management + Billing console, select Exports from the navigation panel to open the Azure export utility.
1. Select Create to open the export page for creating a new CSV export.
1. Create a new export for Cost and Usage (actual) : Type of data: Cost and Usage (actual) Create an export prefix e.g.: Cloudability, then click on the cldy-actual-cost to reveal: Export name: Customer Defined Unique File Name Dataset version: 2021-10-01 Frequency: Daily export of month to date costs Export Description: Optional Click Save Click Next to open Destination tab Storage type: Azure blob storage Destination and storage: Select to use an existing subscription and resource group or create new Subscription: Select destination subscription Storage account: Select storage account Container: Enter a valid container name meeting your naming standards Directory: Enter a valid directory name meeting your naming standards Format: CSV Compression Type: None or Gzip File partitioning: Retain the default selection Overwrite data: Retain the default selection Click Next On the Review and Create tab, Click Create Cost and Usage (amortized) : Follow same steps as above Ensure that the same subscription, storage account container and directory are used as in the previous Export creation Click Review and Create Note: Both CSV formatted files are required by Cloudability and must be present in the storage account used to collect cost management data. We don't recommend FOCUS data ingestion for Azure as the native Azure Cost Management Exports provide much more granular information.
1. Ensure the below setting are applied for the Storage account configured for exports: Navigate to Storage Accounts and select your Storage Account used for Cloudability Select Security + Networking Select Networking Click Manage Under Public Network Access, select Enable Under Public network access scope select either of the below Enable from all networks, or Enable from selected networks In this case, contact Cloudability support to obtain a range of IPs which can be whitelisted Click Save Select Security + Networking Select Encryption Click Encryption scopes Provide an encryption scope name Encryption type Microsoft managed keys (MMK) Infrastructure encryption Enabled or Disabled Click Create
1. Gather billing data information for your Cloudability credential setup After you've created your billing data exports, Cloudability needs additional information from your Azure Portal for the Cloudability credential setup which is called out below: You can find the list of all properties Cloudability needs in the Azure Portal Cost Management console:

| Property Name | How to find it |
| --- | --- |
| Billing Account ID | Search for Cost Management + Billing and select it from the list to open the Cost Management + Billing Overview page. Select Billing Scopes and click the billing scope Navigate to Settings, click on properties, copy and save your Billing Account ID |
| Tenant ID | Search for Microsoft Entra ID and select it to load the Active Directory Overview page. Copy and save the Tenant ID |
| Subscription ID | Search for Subscriptions and select it to open up the subscriptions page From the list of subscriptions under the same billing account select the subscription Copy the Subscription ID where the exports were created and save it. |
| Resource group name | From the storage account Overview page, click the storage account link to view the Resource group name as in this example: |
| Storage account name Container name Directory name Cost export name Amortized export name | Search for Cost Management + Billing and select it Navigate to Exports under settings to display a table with your billing data storage account. Scroll to the right and select the storage account for your billing data to open the Overview page, where you can view the Storage account name, Storage container name, Storage directory name, both the actual cost export and amortized cost export file names: |

Step 2 - Cloudability - Credential using the billing data information

Once you’ve gathered the information listed in the table, you can enter it into Cloudability to update your MCA credential.

Cloudability will use this information to generate a PowerShell script. When the script is run from your Cloud Shell in the Azure Portal or from local PowerShell scoped to your tenant, it will create and grant rights for Cloudability via the CloudabilityCostDataReader role in order to provide access to the storage account.

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > AZURE . Click Next Select Microsoft Customer Agreement (MCA) - the Add AZURE Account panel opens. Or Settings > Vendor Credentials > Ingress > AZURE . Click Next Select Microsoft Customer Agreement (MCA) - t he Add a Credential panel opens.
1. Enter the information gathered from your Azure Portal into the corresponding fields Enter the Azure Billing Account ID Tenant ID Subscription ID Resource Group Name Storage account Name Container Name Directory Name Cost Export Name Amortized Cost Export Name
1. Select Generate Setup Script to download the new script file.
1. Select Close .

You will return to verify the changes later.

STEP 3 - Azure Portal - Grant Cloudability access from the Azure Portal

The next step is to grant Cloudability access to read the cost and usage data from your Azure storage by running the setup script in your Azure Portal Cloud Shell.

1. Log in to the Azure Portal and switch to the required tenant (the directory that is the at highest level in Azure for the target enrollment and where your Cost Management Exports are written).
1. From the Azure Portal, launch the Cloud Shell and select PowerShell as the scripting language.
1. After the Cloud Shell has initialized, select Upload from the Cloud Shell terminal menu.
1. Upload the setup script file provided by Cloudability.

![](../images/blobid9.jpg)

1. Run the script by typing: ./<YOUR_SCRIPT_NAME_HERE>.ps1 Note: This should add Billing Account Reader role to the Cloudability Service Principal

Step 4 - Cloudability - Verify the Account Credential

1. Return to the Cloudability credentials Azure page at Settings > Vendor Credentials> AZURE .
1. Select the three dots on the right hand side and select Edit next to your MCA credential.
1. Select Verify Credential in the panel that open.
1. Click on the … next to the account being credentialed and select Re-Verify.

A green tick ( ) indicates success where as a red exclamation ( ) indicated errors.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and Azure tags within Cloudability.
- Pricing data would also be pulled in.
- Cloudability will also display the Subscriptions

As a next step you will need to credential the Subscriptions.

Click here to Set up Azure Rightsizing and Reserved Instance Planning for credentialing the Azure Subscriptions

1. I recently turned on the Azure Cost Management Exports and credentialed in Cloudability. How long will it take to see the data in Cloudability? Please refer the cost and usage data availability documentation
1. Azure Exports vs Azure Cost details API, which one should be used for integrating Azure in Cloudability? Using Azure exports is the Microsoft recommended way. This is a scalable approach as when your data set grows exports are able to handle bigger datasets. Azure cost details API can be used for smaller data sets.
1. Can we ingest historical cost data in Cloudability? If yes, how far back data can be ingested Yes, we can via One time Exports. Please check with IBM Cloudability Support teams on how to bring in Historical data.
1. Can FOCUS format be used instead of Azure exports for integration? No. For correct integration into Cloudability and bringing in things such as Rightsizing and Reserved Instance and Savings Plan Azure data we recommend using exports as it provides much more granular information.
1. Where Can I find Cloudability's Vendor Credentials APIs for Azure Please refer : Vendor Credentials End Points Azure
1. What are the guidelines for switching from EA to MCA ? Since EA to MCA is a contract change which also changes the Billing account id, Customers need to credential the MCA account as new Billing account and follow the credentialing steps. Please follow the credentialing script as the roles between EA and MCA changes for the billing account scope The subscription IDs should not change, only the Billing account changes Once basic credentials are completed the Billing exports would be picked up and the subscriptions would be populated subsequently. Azure EA data would be displayed until the date EA account had data. After the switch (and credentialing MCA) new data will be pulled via MCA account. EA account after successful switch and validating the cost can be archived. (optional)

---

## Connecting with Azure MCA – Cost Details API

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure > Connecting with Azure MCA – Cost Details API
- **source_path:** SSVCLNQ/admin/azure-cmapi-mca.html
- **original_file:** azure-connecting-mca-cost-details-api.md
- **images:**
  - 03-media/apptio-cloudability-standard/billing-mca-property.png
  - 03-media/apptio-cloudability-standard/copy-tenant-id.png
  - 03-media/apptio-cloudability-standard/copy-subscription-id.png
  - 03-media/apptio-cloudability-standard/Azure-MCA-Cost-Details-API.png
  - 03-media/apptio-cloudability-standard/Azure-PowerShell-Upload.jpg
  - 03-media/apptio-cloudability-standard/clip_image001_-1832790195.png
  - 03-media/apptio-cloudability-standard/clip_image002_-821243953.png
  - 03-media/apptio-cloudability-standard/CLDY-Vendor-Creds-Azure-Verified.png

## Connecting with Azure MCA – Cost Details API

Overview

This guide walks you through the process of securely connecting your Azure MCA environment to IBM Cloudability via Azure Cost Details APIs.

Cost Details API is an alternate credentialing mechanism for Azure Customers. Once connected, you’ll gain access to the FinOps experience in Cloudability. In this process we’ll create a Service Principle within your Azure account which will help Cloudability pull the Billing data.

To ensure full compatibility and support, please follow the connection steps as described. Custom configurations are not supported. If you have questions, reach out to IBM Support .

Prerequisites

Before you begin, ensure you have access to:

- Azure MCA Portal

- Enterprise Admin (or a minimum of Enrollment Writer, or your organizations equivalent) role in Azure

- Administrator access to Cloudability Vendor Credentials page

Cloudability’s Azure Cost Details API Credentialing process requires 2 main steps:

- Billing Account Credentialing

- Subscription Credentialing

Billing Account Credentialing

Cloudability uses Billing Account credentialing for bringing in the Azure Cost and Usage data, resource level, resource group tags for credentialed Billing Account(s).

The credentialing process involves a few steps which will require you to take actions in both Azure Portal and Cloudability at various phases.

Let’s get started with the Credentialing process:

1. In the Azure Portal : Locate your Billing account ID (Enrollment ID). Search for Cost Management + Billing and select it from the list to open the Cost Management + Billing Overview page. Select the billing scope Navigate to Settings, Click on properties, copy and save your Billing account ID (Enrollment ID). Locate your Tenant ID Search for Microsoft Entra ID and select it to load the Active Directory Overview page. Copy and save the Tenant ID Get your S ubscription ID From the list of subscriptions under the same billing account. Copy one of the Subscription ID and save it.
1. In Cloudability - Configure Credentials for Azure Billing Account You must have Cloudability Administrator rights to complete this procedure. If you don’t have administrator rights, contact your organization’s primary Cloudability administrator for assistance. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource and select Azure - EA Enter the Azure Enrollment ID (Billing Account ID), Tenant ID and Subscription ID. Enter “ NA ” in all other fields. Click on Generate Setup Script. A PowerShell Script will be downloaded.
1. In Azure Portal - Upload the PowerShell script The next step is to grant Cloudability access to read the cost and usage data from your Azure storage by running the setup script in your Azure Portal Cloud Shell. Execute the PowerShell script in the PowerShell console (or natively) To run the script: Log in to the Azure Portal and switch to the required tenant From the Azure Portal, launch the Cloud Shell and select PowerShell as the scripting language. After the Cloud Shell has initialized, select Upload from the Cloud Shell terminal menu. Upload the setup script file provided by Cloudability. Run the script by typing: Note: >: ./<YOUR_SCRIPT_NAME_HERE>.ps1 This PowerShell script will create a Service Principle called as “ CloudabilityUtilizationDataCollector ”. Note: This should add Billing Account Reader role to the Cloudability Service Principal
1. In Cloudability - Verify the Billing account credential In Cloudability , navigate to Settings > Vendor Credentials > Azure. Click on the … next to the account being credentialed and select Re-Verify. A green tick ( ) indicates success whereas a red exclamation ( ) indicated errors

In the event that verification fails, please retry after 15 minutes.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and Azure tags within Cloudability.
- Pricing data would also be pulled in.
- Cloudability will also display the Subscriptions

As a next step you will need to credential the Subscriptions.

Subscription Account Credentialing

As a next step please continue to the Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning instructions. Putting these permissions in place will help bring in the Azure subscription tags and utilisation data which helps in using the Optimize features of Cloudability.

Frequently Asked Questions

1. I don’t see any cost data after completing the account credentialing steps, what should be done? Please check if the account is successfully verified (shows a green tick mark). If it does wait for 24 hours for the data else reach to Cloudability support team. If the account is not verified (shows red!), Please check the configurations again and confirm all details are accurate AND that the script has been executed in your environment.
1. I recently turned on Azure and credentialed the accounts in Cloudability. How long will it take to see the Cost and Usage data? It may take up to 24 hours for your first Cost data to get displayed in Cloudability.
1. How do I update to the latest PowerShell template for permissions? This can be done using Cloudability Manage Azure credentials. To regenerate the PowerShell template to reconfigure your Azure access, do the following: In Cloudability , navigate to Settings > Vendor Credentials > Azure . Save and download the current PowerShell template. In Azure Portal, install the template. On successful update, re-verify the account.
1. Can we ingest historical cost data in Cldy? If yes, how far back data can be ingested? Yes, we can. Cost details APIs allows data to be fetched for 13 historical months. For requirements around historical data please raise a support ticket.
1. When should I use Cost details API for Azure. Cost details API for Azure is recommended for smaller datasets, preferably less than 2GB.
1. At first credentialing how much historical data Cloudability will bring in? Cloudability will bring current and previous months cost data.
1. How do I migrate from Azure Cost Details API to Azure Details Exports? This would require re credentialing of accounts. Please follow the credentialing steps for Azure exports.
1. Is changing of the content of the PowerShell script generated by Cloudability recommended? This is not recommended as an approach as for Cloudability to function correctly it needs the service principle and the roles assigned within the PowerShell script. Any changes to the script are unsupported.
1. What are the guidelines for switching from EA to MCA ? Since EA to MCA is a contract change which also changes the Billing account id, Customers need to credential the MCA account as new Billing account and follow the credentialing steps. Please follow the credentialing script as the roles between EA and MCA changes for the billing account scope The subscription IDs should not change, only the Billing account changes Once basic credentials are completed the Billing data would be picked up and the subscriptions would be populated subsequently. Azure EA data would be displayed until the date EA account had data. After the switch (and credentialing MCA) new data will be pulled via MCA account. EA account after successful switch and validating the cost can be archived. (optional)

---

## Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure > Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning
- **source_path:** SSVCLNQ/admin/azure-advanced-rightsizing.html
- **original_file:** cma-set-up-advanced-credentials-azure-rightsizing-reserved-instance-planning.md
- **images:**
  - 03-media/apptio-cloudability-standard/vc_ss1.jpg
  - 03-media/apptio-cloudability-standard/vc_ss2.jpg
  - 03-media/apptio-cloudability-standard/vc_ss3.jpg
  - 03-media/apptio-cloudability-standard/vc_ss4.jpg
  - 03-media/apptio-cloudability-standard/azure_rightsizing7.jpg
  - 03-media/apptio-cloudability-standard/azure_rightsizing8.jpg
  - 03-media/apptio-cloudability-standard/azure_rightsizing9.jpg
  - 03-media/apptio-cloudability-standard/azure_rightsizing11.jpg
  - 03-media/apptio-cloudability-standard/azure_rightsizing12.jpg
  - 03-media/apptio-cloudability-standard/details.jpg
  - 03-media/apptio-cloudability-standard/azure-rightsizing-credentials.jpg
  - 03-media/apptio-cloudability-standard/azure_rightsizing16.jpg

## Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning

Azure Subscription level credentialing unlocks the following features within Cloudability :

Optimization - through Rightsizing, and Reserved Instances (RIs)

Get recommendations for scaling your cloud resources with Rightsizing

The Reservation Portfolio

- Microsoft.Compute/virtualMachines/read
- Microsoft.Compute/virtualMachines/extensions/read
- Microsoft.Compute/disks/read
- Microsoft.Sql/servers/databases/read
- Microsoft.Sql/servers/read
- Microsoft.Sql/servers/elasticpools/read
- Microsoft.Insights/metricDefinitions/read
- Microsoft.Insights/metrics/read
- Microsoft.Resources/subscriptions/read
- Microsoft.Resources/subscriptions/resourceGroups/read
- Microsoft.Authorization/roleAssignments/read
- Microsoft.Insights/Metricnamespaces/Read
- Microsoft.Consumption/usageDetails/read
- Microsoft.Consumption/pricesheets/read
- Microsoft.CostManagement/query/read
- Microsoft.Commerce/UsageAggregates/read
- Microsoft.Commerce/RateCard/read
- Microsoft.Network/networkInterfaces/read

We use the OAuth 2.0 Authorization Grant Flow to register our application and create a service principal within the Azure tenant. You can read more about this process here: https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals

Before you begin

- You are a Cloudability Administrator. The Cloudability Administrator role gives you access to the Vendor Credentials page where you can manage your credentials. Manage Vendor Credentials
- You have one of the following Azure Active Directory roles in your organization: Global Administrator Application Developer Cloud Application Administrator

This is necessary for the OAuth 2.0 Authorization Grant Flow. See https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals .

- You are an Owner (or higher) on the Subscription you are credentialing. This is necessary for the OAuth 2.0 Authorization Grant Flow. See https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals . You need to be at least an Owner on the Subscription so that permissions can be attached to the Service Principal through IAM.

Enable Custom read-only role on a Subscription

The following steps assume that you have already added an Azure EA to Cloudability 's Vendor Credentials page. Also, you have one or more Subscriptions listed on that page for which you would like to provide us access.

1. In Cloudability , edit the subscription. Select the Edit icon for the Subscription for which you would like to provide Cloudability access.
1. Select the Generate Link button to generate a URL for each selected Subscription that you will then use to complete the OAuth 2.0 Authorization Grant Flow for each of those Subscriptions. Select Select Subscriptions . Select the Subscription(s) for which to generate link(s). Select Ok to complete your selections. Select Generate Links . A link is generated for each Subscription that you selected. Choose Optimization options as Read Only vs Optimize Resources .
1. Select each link to complete registering our application and creating a service principal.
1. Complete the OAuth 2.0 flow triggered from the link.
1. Accept the CloudabilityUtilizationDataCollector to complete the consent process.
1. Verify successful consent in the Azure portal: Active Directory. You can verify that the application has been successfully consented to by checking the Enterprise applications section in your Azure Active Directory. Subscription IAM. You can check whether the service principal is a assigned the custom role ‘CloudabilitySubscriptionDataReader’ on the subscription. Confirm that you have successfully credentialed your subscription

Return to the Vendor Credentials page in Cloudability to verify credentials.

Verify Credentials via Bulk Actions

In order to Verify multiple accounts quickly, click on Bulk Actions button. This screen displays all the accounts except the ones with Credentials Needed status (X).

1. Select the accounts which are needed to be verified.
1. Click on Review Selection
1. Click on Verify.

This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes.

- A green check box for a Subscription indicates that Cloudability has, a custom read-only role on the Subscription (through our service principal)
- A yellow check box implies that Cloudability has an incomplete credential, for example the credential process could have started (i.e., we have a record in our database) but there are no permissions attached to that credential.
- A red status color for the credential implies that there's an error with the credential.

We can now unlock all Advanced Features through our Service Principal (this requires the service principal to have the CloudabilitySubscriptionDataReader role on Subscriptions). The permissions box will show as a yellow checkbox but this is ok.

1. Re-verify the credential by clicking on the circular arrow A check mark is displayed briefly upon successful verification. You may need to refresh the browser to fetch new changes.
1. Select to view the updated permissions .
1. Check whether you have the CloudabilitySubscriptionDataReader role on the subscription. This role on the subscription is identified by these 11 permissions shown in green tick marks.

Click here to Set up Azure Memory Metrics Collection

---

## Set up Azure Memory Metrics Collection

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Azure > Set up Azure Memory Metrics Collection
- **source_path:** SSVCLNQ/admin/set_up_azure_memory_metrics_collection.html
- **original_file:** azure-set-up-memory-metrics-collection.md
- **images:**
  - 03-media/apptio-cloudability-standard/azure_monitoring.jpg

## Set up Azure Memory Metrics Collection

*Azure Monitor Agent collects monitoring data from Azure virtual machines and pushes it to Azure Monitor.*

### About this task

There are two types of metrics available from Azure Monitor:

- Standard Metrics : CPU Percentage, Disk Reads/Writes, Network Throughput
- Guest OS Metrics : Memory Utilization

For more information about Azure Monitor metrics, see Supported metrics with Azure Monitor .

### Procedure

1. Install Azure Monitor Agent Linux Installation Using Azure PowerShell: Set-AzVMExtension -Name AzureMonitorLinuxAgent -ExtensionType AzureMonitorLinuxAgent -Publisher Microsoft.Azure.Monitor -ResourceGroupName <resource-group-name> -VMName <virtual-machine-name> -Location <location> -TypeHandlerVersion <version-number> -EnableAutomaticUpgrade $true Using Azure CLI: az vm extension set --name AzureMonitorLinuxAgent --publisher Microsoft.Azure.Monitor --ids <vm-resource-id> --enable-auto-upgrade true For further details, refer to Azure Monitor Agent Management . Windows Installation Using Azure PowerShell: Set-AzVMExtension -Name AzureMonitorWindowsAgent -ExtensionType AzureMonitorWindowsAgent -Publisher Microsoft.Azure.Monitor -ResourceGroupName <resource-group-name> -VMName <virtual-machine-name> -Location <location> -TypeHandlerVersion <version-number> -EnableAutomaticUpgrade $true Using Azure CLI: az vm extension set --name AzureMonitorWindowsAgent --publisher Microsoft.Azure.Monitor --ids <vm-resource-id> --enable-auto-upgrade true Note: To confirm successful agent installation, check the extensions section of your virtual machine.
1. Send Guest OS Metrics with Azure Monitor Agent Azure Monitor Agent supports pushing guest OS metrics directly to Azure Monitor. Follow the steps below to configure data collection. Reference: Data Collection Rules for Azure Monitor Agent Create Data Collection Rule From the Monitor menu, select Data Collection Rules . Select Create to create a new data collection rule and associations. Enter a Rule name and specify a Subscription , Resource Group , Region , and Platform Type . On the Resources tab: Select + Add resources and associate resources to the data collection rule. Resources can be Virtual Machines, Virtual Machine Scale Sets, and Azure Arc for servers. The Azure portal installs Azure Monitor Agent on resources that don't already have it installed. Select Enable Data Collection Endpoints . Select a data collection endpoint for each of the resources associated with the data collection rule. On the Collect and deliver tab, select Add data source to add a data source and set a destination. Select a Data source type . Select which data you want to collect. For performance counters, you can select from a predefined set of objects and their sampling rate. For events, you can select from a set of logs and severity levels. Important: Cloudability only takes into account the following metrics for Memory Utilization: Windows: Memory Available Bytes + Memory Committed Bytes Linux: mem/available + mem/used On the Destination tab, add one or more destinations for the data source. You can select multiple destinations of the same or different types. For instance, you can select multiple Log Analytics workspaces, which is also known as multihoming. Select Add data source and then select Review + create to review the details of the data collection rule and association with the set of virtual machines. Select Create to create the data collection rule. Note: It can take up to 5 minutes for data to be sent to the destinations after you create the data collection rule.

---

## Connect Microsoft Entra ID

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Microsoft Entra ID
- **source_path:** SSVCLNQ/admin/connect-microsoft-entra-ID.html
- **original_file:** cloudability-connect-microsoft-entra-id.md
- **images:**
  - 03-media/apptio-cloudability-standard/Picture16.png
  - 03-media/apptio-cloudability-standard/Picture17.png
  - 03-media/apptio-cloudability-standard/Picture18.png
  - 03-media/apptio-cloudability-standard/Picture19.png
  - 03-media/apptio-cloudability-standard/Picture20.png
  - 03-media/apptio-cloudability-standard/Picture21.png
  - 03-media/apptio-cloudability-standard/Picture22.png
  - 03-media/apptio-cloudability-standard/Picture23.png

## Connect Microsoft Entra ID

Microsoft Entra ID (earlier known as Azure Active Directory) is a cloud-based Identity and Access Management (IAM) service which acts as an Identity Provider (IdP). It authenticates and verifies the identities of users, devices, and services for secure access to applications and resources.

- You are a Cloudability administrator.
- You have Admin permissions in the Microsoft Entra ID tenant.

- To connect to your Microsoft Entra ID tenant, Cloudability registers its own app in the Entra ID tenant that you choose to credential with Cloudability. Then, Cloudability creates a Service Principal in your tenant using the registered app.
- For authentication, Cloudability uses its app’s access and secret key which are stored and managed by Apptio.
- To credential Cloudability with your Microsoft Entra ID, download a power shell script from Cloudability’s Vendor Credentials module and run it in your Microsoft Entra ID tenant you want to credential.
- Here's a sample of a power shell script: $entraAppId = "8dd8d868-a85c-4607-acd4-491df5068a79" $cldyEntraObjectId = (Get-AzADServicePrincipal -ApplicationId $entraAppId).id if (!$cldyEntraObjectId) { New-AzADServicePrincipal -ApplicationId $entraAppId $cldyEntraObjectId = (Get-AzADServicePrincipal -ApplicationId $entraAppId).id } else { echo "Service principal already present, skipping new service principal creation" }
- Running this script in your power shell command will register Cloudability’s app (with the AppID as mentioned in the first line of the script) in your tenant and create the Service Principal using the app. If a Service Principal is already present, then it will skip the creation of a new Service Principal and will re-use the existing Service Principal.
- Finally, you will need to add User.ReadBasic.All and GroupMember.Read.All permissions to the Service Principal. Note: To credential Cloudability with your Entra ID, you don’t need to take any other action in your Azure environment other than running the power shell script as mentioned earlier and granting the required permissions.

Detailed Steps

1. Navigate to Settings > Vendor Credentials .
1. Click Add Datasource button and then select Microsoft Entra ID .
1. Click Next from the slide out.
1. Provide the Tenant ID for the specific Azure Entra ID tenant you want to credential with Cloudability and click Save .
1. Select Download Script .
1. Run the downloaded script in the specific Azure Entra ID tenant.
1. Add User.ReadBasic.All and GroupMember.Read.All permissions to the Service Principal. Follow these steps to add the permissions: Search "CloudabilityGroupReaderApp" in the Azure Portal search bar. Once inside the application, navigate to the Permissions section under Manage. Click Grant admin consent for Default Directory . After the consent is granted, you can see the permission(s) listed as shown here.
1. After the script runs successfully, navigate to Settings > Vendor Credentials > Microsoft Entra ID tab . The credential will display with a yellow tick indicating it is yet to be verified. Expand the ... option and select the Edit option.
1. Click the Verify Credential button from the slide out.
1. If verified, the credential will display with a green tick .

---

## Connect MongoDB

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect MongoDB
- **source_path:** SSVCLNQ/admin/connect-mongodb.html
- **original_file:** cloudability-connect-mongodb.md
- **images:**
  - 03-media/apptio-cloudability-standard/MongoDB-Organization.jpeg
  - 03-media/apptio-cloudability-standard/MongoDB-Permissions.jpeg
  - 03-media/apptio-cloudability-standard/MongoDB-API.jpeg
  - 03-media/apptio-cloudability-standard/MongoDB-CLDY.jpeg

## Connect MongoDB

Overview

This guide walks you through the process of connecting your MongoDB to IBM Cloudability. Once connected, you’ll gain access to the MongoDB Cost and usage data within Cloudability.

Prerequisites

- You should be a Cloudability administrator.
- You should have admin permissions in the MongoDB Atlas console.

- The high-level line item for AWS
- The line items with detailed MongoDB costs, with "AWS Marketplace" listed as Seller.

If you want to hide your marketplace costs, set up a filter.

Marketplace costs are excluded from billing.

MongoDB Account Credentialing process involves a few steps which will require you to take actions in both MongoDB console and Cloudability at various phases.

During this process Cloudability will use your MongoDB OrganizationID to connect with your account and fetch the Cost and usage data.

Step 1 – MongoDB Console

Get your Organization ID

1. Go to the MongoDB Atlas console.
1. Click on the user profile and then on Organizations.
1. Click on the Organization name
1. Click the gear icon next to the Organization settings.
1. Copy the your Organization ID and save it for use later.

Create an Organization API Key

1. Go the Access Manager page in the MongoDB Atlas console.
1. Click on applications and select the API tab
1. Click Create API Key .
1. Enter the API Key information. In the Description box, enter a description (e.g., Cloudability Access). In the Organization Permissions menu, select the Organization Billing Viewer role.
1. Click Next .
1. Copy the public and private keys

Step 2 – Cloudability

1. Open Cloudability in a new tab or window.
1. In Cloudability, go to Settings > Vendor Credentials .
1. In the Ingress section, choose the MongoDB tile. The Add MongoDB Account panel opens.
1. Read the information presented and choose the Next button when you are ready to proceed.
1. Paste the copied Organization ID into the Organization ID field.
1. Paste the Public Key and Private Key into their respective fields.
1. From the Subscription Model field, choose whether your organization uses a Marketplace or buys Direct from MongoDB.
1. Click on the Save button.
1. Click on Verify Credentials .

By default, MongoDB restricts API access using the IP Access List for the Atlas Administration API. If this is not disabled for your organization, use the following IP ranges to give MongoDB access to Cloudability:

- 185.115.88.0/22
- 103.195.128.0/22
- 129.41.0.0/22

For more details on Whitelisting IPs please contact IBM Support teams.

Frequently Asked Questions

- Which version on MongoDB is supported in Cloudability? MongoDB Atlas
- When should I use Marketplace vs subscription? If you bought MongoDB from a Marketplace like AWS or Azure use this option If you bought MongoDB Direct from MongoDB then select Direct

---

## Connect New Relic

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect New Relic
- **source_path:** SSVCLNQ/admin/new-relic-integration.html
- **original_file:** cloudability-connect-new-relic.md
- **images:**
  - 03-media/apptio-cloudability-standard/cloudability-newrelic-account-insights-keys.jpg
  - 03-media/apptio-cloudability-standard/cloudability-newrelic-insights-key-details.jpg
  - 03-media/apptio-cloudability-standard/vc_ss9.jpg
  - 03-media/apptio-cloudability-standard/cloudability-newrelic-credentails-list.jpg
  - 03-media/apptio-cloudability-standard/cloudability-newrelic-rightsizing-list.jpg
  - 03-media/apptio-cloudability-standard/cloudability-newrelic-datasource-filter.jpg

## Connect New Relic

New Relic is a popular application performance management (APM) platform. This integration enables Apptio Cloudability customers to leverage New Relic as their preferred utilization data provider, resulting in improved rightsizing recommendations for Amazon EC2, GCP GCE, and Azure Compute virtual machines. Support for multiple accounts is also included with this integration.

Compared to the native utilization data providers, New Relic provides more precise platform performance metrics (CPU, Network, Disk), and access to guest OS memory metrics. With this higher precision data source, the rightsizing engine surfaces more informed recommendations, providing up to an additional 15 percent savings, on top of the existing savings opportunities, further reducing your cloud spend.

Before you start

The following steps are required to enable New Relic integration with Cloudability successfully:

- Virtual Machines -Each virtual machine resource needs to have the New Relic infrastructure agent installed. The instructions vary based on the operating system; currently, Linux and Windows are supported.

- Linux
- Windows

- New Relic Accounts

For each New Relic account, you must provide an Account Id and Insights Query Key. Cloudability uses these read-only credentials to retrieve the performance metrics from your associated virtual machine resources via the Insights API .

- Obtaining Account Credentials
- Entering New Relic Credentials

Steps for integration

- Enabling Azure integration

- Enable Azure Integration

- Obtaining Account Credentials

To manage or obtain your New Relic account credentials:

1. Go to insights.newrelic.com and switch to the desired account
1. From the left menu, click Manage data
1. From the top menu, click API Keys
1. To create a New Key, click Query Keys [+]
1. To view or edit an existing key, click the appropriate Edit button

The below screen allows the customer to create or edit the Notes associated with an Insights Query key.

From this screen, the customer can obtain the following:

- Account Id (a seven or greater digit number)
- Insights Query Key (key begins with NRIQ-)

We suggest you label this query key as `cloudability-integration` for tracking and auditing purposes.

Entering New Relic Credentials

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > New Relic . The Add New Relic Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > New Relic . Select Add a Credential . The Add a Credential panel opens.
1. Enter the New Relic credentials.
1. Select Save .

How to confirm success

- To modify a credential, select Edit
- To delete a credential, select Delete
- To validate a credential, select Refresh

Using Rightsizing

After the setup is complete, the customer can view the rightsizing recommendations from the Data Source column.

Filter or Sort by Data Source

- To sort, click on the Data Source column heading and the list will be sorted by this value.
- To filter, either click on the Data Source value to limit the recommendations to this value, or click the Filters menu, then select Measure = Data Source , Operator = equals , and Value = New Relic .
- To clear the filter, click the Filter menu, and then delete the condition by clicking the 'x' icon.

GCP Integration

For additional information on connecting Google Cloud Platform services to New Relic, see https://docs.newrelic.com/docs/infrastructure/google-cloud-platform-integrations/get-started/connect-google-cloud-platform-services-new-relic/ .

---

## Connect Oracle Cloud

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Oracle Cloud
- **source_path:** SSVCLNQ/admin/connect-oracle-cloud.html
- **original_file:** cloudability-connect-oracle-cloud.md
- **images:**
  - 03-media/apptio-cloudability-standard/terraform_script_1.jpg
  - 03-media/apptio-cloudability-standard/terraform_script_2.jpg
  - 03-media/apptio-cloudability-standard/terraform_script_3.jpg
  - 03-media/apptio-cloudability-standard/terraform_script_4.jpg
  - 03-media/apptio-cloudability-standard/terraform_script_5.jpg
  - 03-media/apptio-cloudability-standard/OCI_Terrform_version%20update.png
  - 03-media/apptio-cloudability-standard/terraform_script_7.jpg
  - 03-media/apptio-cloudability-standard/validating_oci_1.jpg
  - 03-media/apptio-cloudability-standard/OCI-user-groups-.png
  - 03-media/apptio-cloudability-standard/validating_oci_3.jpg
  - 03-media/apptio-cloudability-standard/OCI-api-key.png
  - 03-media/apptio-cloudability-standard/OCI-generate-api-key.png
  - 03-media/apptio-cloudability-standard/generating__api_oci_3.jpg
  - 03-media/apptio-cloudability-standard/oracle-cloud-adding-credentials-child-tenancies.jpg

## Connect Oracle Cloud

To ensure full compatibility and support, please follow the connection steps as described. Custom configurations are not supported. If you have questions, reach out to IBM Support .

1. Getting your cost and usage data in Cloudability Cloudability gets your OCI cost and usage data from Cost Reports, which are owned by OCI and located in the root tenancy of your OCI console. To provide Cloudability with access to your OCI cost and usage data, you need to validate the credentials for your root tenancy as the data for your child tenancies roll up to the root tenancy. The credentialing process is done using a Terraform script and your root tenancy OCID is required to generate and run the script. The script includes commands to create a group and a user, add the user to the group, create policies, and attach them to the group so that Cloudability can access the cost reports from the OCI console. Please note that these policies provide Cloudability with read-only permission to the OCI data. Once the script is executed in the OCI console, you will need to generate Signing Keys. The last step will be to paste the home region name, user OCID, group OCID, Fingerprint and Private Key in Cloudability UI.
1. Getting your utilization data in Cloudability Once you have completed the credentialing process for your root tenancy, you will be getting OCI utilization data only for your parent tenancy. After the credentials are verified, your child tenancies are displayed in the credentialing UI, and you will need to go through the credentialing process for these child tenancies as well to get their utilization data. Getting utilization data will allow Cloudability to provide rightsizing recommendations. You can find more details at the bottom of this page under “ Adding Credentials for your child tenancies ”.

Prerequisites

- You are a Cloudability administrator.
- You have administrator permissions in the OCI console. This is required to execute the Terraform script in the OCI console .

Integration Steps

1. Log in to the Oracle Cloud Infrastructure (OCI) Console.
1. Select Governance & Administration from the navigation menu at the top left corner of the dashboard.
1. Select Tenancies in the Organization Managemen t header. Your tenancies are listed here.
1. Copy your parent tenancy ID, by selecting the copy icon next to your tenancy ID with "Parent tenancy" in the name.
1. In Cloudability , navigate to Settings > Vendor Credentials > OCI.
1. Select Add a Credential . The Add a Credential panel opens on the left side.
1. Paste the parent tenancy ID.
1. Select Save .

Generate the Terraform Script

Once your Tenancy ID is saved, select Generate Script . It downloads the terraform script. Please create a specific folder eg: Cloudability and save the script in that folder in your local machine. This is done as when you upload the script you cannot individually upload the script – You have to upload the folder which contains the script.

The following is the terraform content used by Cloudability to create required resources:

```
variable "cloudablity_user_email" {
				description = "This is a variable to assign the email to user. If not provided, default email will be set."
				type        = string
				default     = "cldyuser@cloudability.com"
				}
				 
				resource "oci_identity_user" "cloudablity_user" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability user and they will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_User"
				freeform_tags = {
				"User_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_group" "cloudability_group" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability group and it will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_Group"
				freeform_tags = {
				"Group_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_user_group_membership" "user_group_membership" {
				group_id = oci_identity_group.cloudability_group.id
				user_id = oci_identity_user.cloudablity_user.id
				}
				 
				resource "oci_identity_policy" "cloudability_policy" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This policy will retrieve permissions to access the cost report and list policy."
				name = "CloudabilityCostDataReaderPolicy"
				freeform_tags = {
				"Policy_Created_For"= "Cloudability"
				}
				statements = [
				"define tenancy reporting as ocid1.tenancy.oc1..aaaaaaaaned4fkpkisbwjlr56u7cj63lf3wffbilvqknstgtvzub7vhqkggq",
				"endorse group ${oci_identity_group.cloudability_group.name} to read objects in tenancy reporting",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-tenancy in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-family in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read policies in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read metrics in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read rate-cards in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-images in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to inspect instances in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-family in tenancy"
				]
		}
```

1. In the OCI console, select the navigation menu on the top left corner of the dashboard page, and then select Developer Services .
1. Select Stacks in the Resource Manager header. Note: Make sure to select the root compartment in the List Scope on the left side view.
1. Select Create Stack to create a new stack.
1. In the Create Stack page, select My Configuration to upload Terraform configuration files.
1. In Stack configuration section, select Folder , and then browse to the folder where the configuration file is stored.
1. Select Upload on the pop-up. Note: Make sure that the selected compartment has "(root)" selected under the Create in Compartment field.
1. In the Name textbox, enter ‘ Cloudability ’ as the value. Select Next .
1. You now have the option to update the email address “cldyuser@cloudability.com” that is provided in the Terraform script. This variable is only required if you have Identity Domain in your OCI console and can be updated at this stage, if required.
1. Select Terraform version as "1.5"
1. Select the Run Apply checkbox.
1. Select Create to create the stack.

The Resource Manager will validate the provided Terraform file and create a new stack.

Monitor the job status (lifecycle state) by getting the job. Succeeded indicates the job is complete.

This job will create a User, a Group and a Policy. The operation can take some time depending on the complexity of the job. While the job runs, or after it is completed, you will get the job logs content.

Once the stack is created, you can see it in the Stacks section.

1. Select Identity & Security from the navigation menu at the top-left corner of the dashboard.
1. Select Users in the Identity header by going to Identity → Domain → Select Domain → User Management Tab. You can notice a user named "CloudabilityDataCollector_User" that was created by the Terraform job. Note: If you do not wish Cloudability to create a local user and instead would like to have a “federated” user, see Federating a User for OCI Credentialing .
1. Select Groups in the Identity header. If you are leveraging Identity Domain , you will need to select Domains in the Identity header , and then select Default domain, User management and select Groups . You can notice a group named "CloudabilityDataCollector_Group" that was created by the Terraform job.
1. Select ' CloudabilityDataCollector_Group ' to check if ' CloudabilityDataCollector_User ' has been added into this group as a Group Member .
1. In the Group Information , copy the group OCID and save it. This information will need to be pasted later in Cloudability UI.
1. Select Policies in the Identity header. You can notice the policy named "CloudabilityCostDataReaderPolicy" that was created by the Terraform job. This policy contains all the policies required to fetch data from the customer environment. Modifying this policy name is not supported.

1. Select Identity & Security from the navigation menu at the top-left corner of the dashboard.
1. Select Users in the Identity header by going to Identity → Domain → Select Domain → User Management Tab. Note: If you are leveraging the Identity Domain module, select Domains in the Identity header, and then select Default domain and Users .
1. Select the user named "CloudabilityDataCollector_User".
1. Select API keys → Add API Key
1. Select Generate API Key Pair .
1. Select Download Private Key . You will need to paste it later in Cloudability UI.
1. Select Download Public Key .
1. Select Add and the fingerprint will be generated.
1. Select View Configuration file.

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > OCI . The Add OCI Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > OCI. Select Add a Credential . The Add a Credential panel opens. Paste the information in the configuration file as below: Home Region : This is displayed next to region in the Configuration File User ID : This is displayed next to user in the Configuration File . Group ID : This information was saved during the previous step. You can find this OCID by navigating to Identity & Security > Groups > ' CloudabilityDataCollector_Group '. Namespace : This is your OCI namespace, please fill in the namespace configured. Fingerprint : This is displayed directly in the Configuration File . Passphrase : This can be left blank. Private Key : This information was saved during the previous step . Note: Make sure to paste the Private Key in its entirety in Cloudability , including "-----BEGIN PRIVATE KEY----” and “-----END PRIVATE KEY----".
1. Select Save .
1. Select Verify Credential . Note: Make sure to select Save before selecting Verify Credential to avoid any error messages.

If the information is correctly verified, a green check mark appears under Billing Reports . A green check mark will appear under the Advanced Features as well but only for the root tenancy.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and OCI tags within Cloudability.
- Pricing data would also be pulled in
- Cloudability will also display the OCI child tenancies.

As a next step you will need to credential the OCI child tenancies..

Once you see your OCI data, you can proceed to update your tags and business mappings - you can learn more about this in the Apptio Community Post .

Step 3 - In Cloudability - Adding Credentials for your child tenancies

Once your credentials are verified, your child tenancies will be automatically discovered by Cloudability and displayed in the UI. Hover over the 3 dots on the right side of your child tenancy and select the “pencil” button.

Then, you can start credentialing your child tenancies, following the same process described above for parent tenancies.

Verify Credentials via Bulk Actions

In order to Verify multiple accounts quickly, click on Bulk Actions button. This screen displays all the accounts except the ones with Credentials Needed status (X).

1. Select the accounts which are needed to be verified.
1. Click on Review Selection
1. Click on Verify.

This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes.

Permission List

You can find below the list of permissions displayed in OCI credential details. Some of them are applicable only to the Parent Account/ Tenancy, and not to the Child Account/ Tenancy (“oci.get.costReports”, “oci.list.tenancies”, and “oci.list.rateCards”).

| Permission | Description | Applicable to Parent Account/ Tenancy | Applicable to the Child Account/Tenancy |
| --- | --- | --- | --- |
| oci.get.costReports | Permission to fetch cost report | Yes | No |
| oci.list.tenancies | Permission to list child tenancy from parent | Yes | No |
| oci.get.metrics | Permission to get metrics | Yes | Yes |
| oci.list.rateCards | Permission to list rate cards | Yes | No |
| oci.list.assignedSubscriptions | Permission to list assigned subscription | Yes | Yes |
| oci.list.computeShapes | Permission to list compute shapes | Yes | Yes |
| oci.list.computeImages | Permission to list compute images | Yes | Yes |
| oci.list.imageShape.Compatibility | Permission to list image shapes | Yes | Yes |
| oci.get.instanceFamily | Permission to read instance family | Yes | Yes |
| oci.list.policies | Permission to read policy for verification | Yes | Yes |

---

## Federating a User for OCI Credentialing

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Oracle Cloud > Federating a User for OCI Credentialing
- **source_path:** SSVCLNQ/admin/oci-credentialing.html
- **original_file:** cloud-federating-user-oci-credentialing.md
- **images:** []

## Federating a User for OCI Credentialing

Summary

This page outlines the step-by-step process to handle a federated user in an identity provider for OCI, specifically focusing on the creation and configuration of users and groups in the Oracle Identity Cloud Service (“IDCS”).

This process is optional, it is done by deploying a terraform and then replacing the user with a federated user.

Pre-requisites

To create users and groups in the Oracle Identity Cloud Service federation, you will need the Identity Domain Administrator role, or be a member of a group that has been granted that role.

Steps

Preparation

Ensure that " CloudabilityDataCollector_Group ", " CloudabilityDataCollector_User ", and " CloudabilityCostDataReaderPolicy " are already created through Terraform.

Deleting Local User

Delete the " CloudabilityDataCollector_User " if it exists.

1. Navigate to Identity -> Federation -> Identity Provider Details -> Users .
1. Create a new IDCS user using the following credentials. Username : CloudabilityDataCollector_Fed_User Email : cldyfeduser@cloudability.com or any valid email First Name : CloudabilityDataCollector Last Name : Fed_User
1. Click Create and then Close .

1. Navigate to Identity -> Federation -> Identity Provider Details -> Group .
1. Create a new group in IDCS called " CloudabilityDataCollector_Fed_Group ".
1. Add the federated user " CloudabilityDataCollector_Fed_User " to the group.

Mapping Local Group to Federated Group

Since federated groups cannot be given access via policy, you need to map a local group to the federated group.

1. Navigate to Identity -> Federation -> Identity Provider Details -> Group Mappings.
1. Create a new group in IDCS called " CloudabilityDataCollector_Fed_Group ".
1. Create a mapping between the OCI group " CloudabilityDataCollector_Group " and the federated group " CloudabilityDataCollector_Fed_Group ".

Synchronization of OCI Synched User

Navigate to Identity -> Federation -> Identity Provider Details -> Users -> " CloudabilityDataCollector_Fed_User ".

Click on the OCI Synched User link of the federated user " CloudabilityDataCollector_Fed_User ".

1. Navigate to API Keys .
1. Add a new API key.
1. Generate an API key pair.
1. Download the private key and the public key.
1. Add the keys.

Providing details to Cloudability

Provide the required details, including API keys and other relevant information, to Cloudability through the user interface.

---

## Connect Pagerduty

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Pagerduty
- **source_path:** SSVCLNQ/admin/connect-pagerduty.html
- **original_file:** cloudability-connect-pagerduty.md
- **images:** []

## Connect Pagerduty

The following information will help you connect your Pagerduty Services to Cloudability.

Steps for integration

1. From the Configuration menu, select Services .
1. If you are creating a new service for your integration, on your Services page, select Add New Service .
1. If you are adding your integration to an existing service, on your Services page, select the name of the service to which you want to add the integration. Then, select the Integrations tab and select New Integration .
1. From the Integration Type menu, select Cloudability and complete the Integration Name field.
1. If you are creating a new service for your integration, in General Settings , enter a name for your new service in the Name field. Then, in Incident Settings , specify the Escalation Policy , Notification Urgency , and Incident Behavior for your new service.
1. Select Add Service , or Add Integration to save your new integration. You will be redirected to the Integrations page for your service.
1. Copy the Integration Key for your new integration. This will be used in the following procedure.

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > PagerDuty . The Add PagerDuty Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > PagerDuty . Select Add a new service . The Add a new service panel opens
1. Enter the details in the Integration Name and Integration Key fields.

1. Navigate to the Anomaly Detection page.
1. Select ALERTS and configure your PagerDuty alert settings.

Troubleshooting

What can Cloudability do with my integration key in Pagerduty?

We integrate them with v2 of Pagerduty's Events API. The Events API v2 is a highly reliable, highly available asynchronous API that ingests events from monitoring tools. Events sent to this API are routed to a Pagerduty service and processed. They may result in a new alert or incident being created, or an existing one being updated or resolved. Previously, the Events API was also used to integrate Pagerduty with ticketing systems and various other software tools. Today, we recommend using the synchronous Incidents API to integrate ticketing systems or other systems of record with Pagerduty

Therefore, integration keys only allow sending alerts to a service.

---

## Connect Snowflake

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Snowflake
- **source_path:** SSVCLNQ/admin/connect-snowflake.html
- **original_file:** cloudability-connect-snowflake.md
- **images:**
  - 03-media/apptio-cloudability-standard/snowflake_1.jpg

## Connect Snowflake

You can connect your Snowflake account to Cloudability to enable the ingestion of Snowflake granular cost data for warehouses along with Snowflake warehouse and account level tags.

If you are purchasing Snowflake via a cloud provider marketplace and adding cost and usage data for Snowflake with this integration, you will see costs displayed twice in Cloudability reporting. As an example, if you purchased Snowflake via the AWS Marketplace, you would have:

- The high-level line item for AWS.
- The line items with detailed Snowflake costs and AWS Marketplace listed as Seller.

You will need to set up filters or views to hide your Marketplace costs. Marketplace costs are excluded from billing.

Prerequisites

- Admin access to Cloudability for Vendor Credentials.
- Access to Snowflake Org 1.0 or 2.0 (2.0 recommended) for granular cost data.
- Account Admin permissions in the Snowflake 1.0.
- Global Org Admin permissions for Snowflake 2.0.
- For enabling Snowflake Tags Org 2.0 Billing account with Enterprise Edition or higher SNOWFLAKE.ORGANIZATION_USAGE. TAG_REFERENCES view enabled. This is a premium view and may incur additional Snowflake costs. To reduce costs, you can ask Snowflake to disable all premium views except for the one we need (unless you need any of these premium views)

If Tag References view is not enabled , granular warehouse level costs will still be available but without the tags information.

Steps for integration

Snowflake

Access your Snowflake account using appropriate credentials to view account details.

1. Navigate to Snowsight - the web-based SQL editor for Snowflake.
1. Open the account selector from the bottom left menu bar. This displays a list of accounts previously accessed.
1. Identify the account name, and then select the account.
1. Hover over the selected account to view additional details.
1. Copy the Organization Name and the Account Name details.

1. Navigate to the Cloudability application, and click on Vendor Credentials under Settings in the left-hand menu.
1. Provide the following information: Organization Name : Paste the previously copied organization name from Snowflake. Snowflake Account Name : Paste the previously copied account name from Snowflake. Warehouse Name : Provide the name of an existing Snowflake warehouse. Database Name (For Cloudability ): Specify a name for the database to be created by Cloudability. User Name (for Cloudability ): Specify a name for the user to be created by Cloudability. A role with the same name suffixed with the _role will also be created.

Once all inputs are provided, click Vendor Credentials > Generate Template .

This will generate the template as a text file containing configuration details based on earlier input variables.

1. Copy the content of the generated text file.
1. Paste the content into the appropriate worksheet or configuration file within the Snowflake Account. Ensure that you have the Account Admin role in Snowflake.
1. Run the provided SQL query and wait till all the statements are executed successfully.

1. Return to Cloudability and navigate to the Vendor Credentials screen.
1. Click Verify Credentials to confirm the integration status. If the check box is Green, you have successfully integrated Snowflake. Note: Private links are not yet supported for Snowflake.

Frequently Asked Questions

I’m a customer with Snowflake already credentialed but without granular data. Do I need to make changes to view granular Snowflake costs?

Existing customers will continue to see service level costs without any required changes.

To enable granular data, you must re-credential the same Snowflake accounts.

- On Snowflake Org 1.0: You will receive granular warehouse costs but no tags.

- To access both granular costs and tags, upgrade to Snowflake Org 2.0 and then re-credential.

Are there any steps I should be aware of before switching to granular snowflake costs ?

If you are already on Snowflake Org 2.0 , no additional steps are required beyond re-credentialing , as Cloudability requires additional permissions to ingest granular warehouse-level costs and tags.

Which Snowflake Tags are supported?

We support Snowflake warehouse and account level tags in the below format:

- cldy:snowflake:account:<tagkey>
- cldy:snowflake:warehouse:<tagkey>

These would need to be mapped in the Tags and Labels page after the first successful data ingestion.

Where can I get the IP for whitelisting?

Please reach out to IBM support team.

How much historical data can be refetched?

Granular cost data begins from the month you credential the integration.

For historical months, a refetch is required. Cloudability supports 12 months of historical data refetch (including the current month).

Please contact the IBM Support team to request a refetch.

Why can’t I view tags in Snowflake org 1.0?

Tag visibility requires:

- A Snowflake Org 2.0 Billing Account with Enterprise Edition or higher
- The SNOWFLAKE.ORGANIZATION_USAGE. TAG_REFERENCES premium view enabled

Without these, tag data cannot be ingested.

---

## Connect to ServiceNow

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect to ServiceNow
- **source_path:** SSVCLNQ/admin/connect-servicenow-integration.html
- **original_file:** cloudability-connect-servicenow.md
- **images:**
  - 03-media/apptio-cloudability-standard/servicenow_integration-1.jpg
  - 03-media/apptio-cloudability-standard/servicenow_integration-2.jpg
  - 03-media/apptio-cloudability-standard/ServiceNow-Creds.jpeg
  - 03-media/apptio-cloudability-standard/vc_ss8.jpg

## Connect to ServiceNow

Overview

This guide walks you through the process of connecting your ServiceNow account to IBM Cloudability. Once connected, you’ll gain access to using ServiceNow within Cloudability.

Prerequisites

- You are a Cloudability administrator.
- Your organization uses ServiceNow Cloud.
- The administrator for your ServiceNow instance is available during the setup process.
- You have the domain name for your ServiceNow instance.

ServiceNow Account Credentialing process involves a few steps which will require you to take actions in both ServiceNow console and Cloudability at various phases.

During this process Cloudability will use your ServiceNow domain to connect with your account.

- Note the Domain Name of your ServiceNow Cloud. e.g. https://xxxyyy.service-now.com

Step 2 - Cloudability

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > ServiceNow . The Add ServiceNow Account panel opens.
1. Enter the domain name of your ServiceNow instance. Select Save .
1. Click Generate Script and Download the script .

1. In your ServiceNow instance, navigate to System Definitions > Fix Scripts .
1. Click New .
1. Provide the Name as Cldy Script.
1. Paste the generated script from the previous step into the Script section.
1. Make sure Application is set to Global .
1. Click Submit .
1. Go to the created Cldy Script .
1. Click Run Fix Script and Proceed .
1. Navigate to System Security > Users .
1. Search for the Name CldyUser_Script . Note the User ID.
1. Click Set Password , and then type and save the password. Note the password down if required.
1. Navigate to System OAuth > Application Registry .
1. Search for the name Cldy OAuth Client . Note the Client Id .
1. Click the lock button of the Client Secret . Copy the Client Secret .

Step 4 - Cloudability

1. Enter the User ID .
1. Enter the Password .
1. Enter the Client ID .
1. Enter the Client Secret .
1. Click Save .

How to confirm success

Check the status under Settings > Vendor Credentials > ServiceNow. A green tick mark indicates that the integration is successful.

Frequently Asked Questions

I followed the above steps but my account status is still red. What should I do?

Please check if you have entered the details correctly e.g Domain name, User Id, Password, ClientId and Client Secret.

How can I edit the details of ServiceNow Integration?

Click on the 3 dots beside the account and click edit. Add the details and save the credential.

In case the domain has changed , please add a new credential by following all the steps mentioned in this integration. Please delete the old account before doing so.

---

## Connect to ServiceNow CMDB

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect to ServiceNow CMDB
- **source_path:** SSVCLNQ/admin/connect-servicenow-cmdb.html
- **original_file:** cloudability-connect-servicenow-cmdb.md
- **images:**
  - 03-media/apptio-cloudability-standard/connection-credentials.png
  - 03-media/apptio-cloudability-standard/new-api-key.png
  - 03-media/apptio-cloudability-standard/cldy-key-secret.png
  - 03-media/apptio-cloudability-standard/create-connection.png
  - 03-media/apptio-cloudability-standard/workflow-studio.png
  - 03-media/apptio-cloudability-standard/servicenow-cross-scope.png
  - 03-media/apptio-cloudability-standard/cloudability-workspace.png
  - 03-media/apptio-cloudability-standard/cloudability-home-page.png
  - 03-media/apptio-cloudability-standard/cloudability-list-page.png
  - 03-media/apptio-cloudability-standard/new-business-dimension.png
  - 03-media/apptio-cloudability-standard/create-new-business-dimension.png
  - 03-media/apptio-cloudability-standard/new-statement-template.png
  - 03-media/apptio-cloudability-standard/new-dimension-statement.png
  - 03-media/apptio-cloudability-standard/new-statement-group.png
  - 03-media/apptio-cloudability-standard/new-statement-condition.png
  - 03-media/apptio-cloudability-standard/publish-servicenow-business-dimension.png

## Connect to ServiceNow CMDB

### Overview

The ServiceNow CMDB Integration for Cloudability enables seamless synchronization between your ServiceNow Configuration Management Database (CMDB) and IBM Cloudability. This integration allows you to create automated business mappings in Cloudability based on configuration items and organizational data stored in your ServiceNow CMDB, providing enhanced cloud cost allocation and governance capabilities.

### Key Benefits

- Automated Business Mapping : Automatically create and maintain business mappings in Cloudability using your existing ServiceNow CMDB data, reducing manual configuration effort and improving accuracy.
- Centralized Data Management : Leverage your ServiceNow CMDB as the single source of truth for organizational structure, applications, and cost centers that drive your cloud cost allocation.
- Real-time Synchronization : Keep your Cloudability business mappings up-to-date with changes in your ServiceNow CMDB through automated synchronization processes.
- Enhanced Cost Governance : Improve cloud cost visibility and accountability by aligning cloud resources with your organization's structure as defined in ServiceNow

### Prerequisites

Before installing and configuring the ServiceNow CMDB Integration, ensure you meet the following requirements:

ServiceNow Requirements

- ServiceNow instance (Paris release or later recommended)
- Admin or equivalent privileges to install applications from the ServiceNow Store
- CMDB plugin activated in your ServiceNow instance
- Properly configured CMDB with relevant configuration items (applications, business services, cost centers, etc.)

Cloudability Requirements

- Active IBM Cloudability account with administrative privileges
- API access enabled in your Cloudability instance
- Valid Cloudability API credentials

### Installation

Step 1: Download from ServiceNow Store

1. Log into your ServiceNow instance as an administrator
1. Navigate to System Applications > All Available Applications > All
1. Search for "Cloudability" in the ServiceNow Store
1. Click Install and follow the installation prompts
1. Wait for the installation to complete and restart any required services

Step 2: Post-Installation Setup

1. Configure the Cloudability access key Navigate to IntegrationHub > Connections & Credentials > Connection & Credential Aliases Search for "Cloudability KeyAccess" and open it Click "New" to add a new Credentials When prompted "What type of Credentials would you like to create?" select "API Key Credentials" Input "KeyAccess" as the Name and paste the API Key from Cloudability
1. Configure the Cloudability Key Secret In "Connection & Credential Aliases" search for "Cloudability KeySecret" and open it Click "Create New Connection & Credential" Add "Cloudability Spoke Connection" as the "Connection Name" Add "<Region Specific Frontdoor Domain>/service/apikeylogin" as the "Connection URL". Replace "<Region Specific Frontdoor Domain>" with the appropriate Cloudability Frontdoor domain, for example "https://frontdoor.apptio.com/service/apikeylogin" Add the API Secret from the Frontdoor user profile page

Step 3: Testing the configuration

- Navigate to Workflow Studio
- Navigate to the "Actions" section, find "Cloudability Integration - Get Frontdoor Token" and open it
- Click "Test" and then "Run Test"
- When the test is finished running click "View the action execution details"
- If the "Status" variable returns "Success" it means that the credentials were configured correctly

- Provide cross-scope privileges for the Cloudability app to read data from the tables/views specified in the Integration properties. These tables/views are used in the Business Dimension creation page. Please refer to the ServiceNow document . The example below shows the required configuration. Read permission is sufficient for the app.

### Navigation

You can access the Cloudability Business Mapping application through a workspace or through the All menus list.

All user functions are available from the workspace, and this is the recommended method for accessing the application.

Administrator functions are not available in the workspace. They must be accessed through the "All menus" list.

User needs admin access to perform Administrator functions. But for all other user operations admin access is not required.

The Home page displays a list of published and pending ServiceNow business dimensions.

The List page allows you to see lists of ServiceNow business dimensions grouped by status. Clicking on a list to display the business dimensions with that status value.

### Use cases

1. Create/Update Business Dimensions

ServiceNow business dimensions allow you to define and modify Cloudability business dimensions from within ServiceNow utilizing data from the ServiceNow CMDB. You can create new ServiceNow business dimensions or update existing draft business dimensions. To create a new ServiceNow business dimension, click on [+] and select New Business Dimension.

Complete the fields in the form as described in the table below:

| Field | Description |
| --- | --- |
| Field | Description |
| Name | Select a Cloudability Business Dimension. |
| Effective Date | Set the date when this ServiceNow business dimension should update Cloudability. This field is initially set to the current date. |
| Table | Select a ServiceNow table. The data from the table will be used to build out the business dimension statements. |
| Statement template query | Define a query that will be used to filter the data used to build out the business dimension statements. |

Click the Save button to save your changes.

2. Create/Update Statement Templates

Statement templates allow you to define dynamic statements for your Cloudability Business Dimension. They are dynamic in the sense that field values from ServiceNow table rows can be substituted in the statement value expression or the matching expression.

You can create new or update existing statement templates from a draft business dimension. Open a draft business dimension. Click on the “Statement Templates” tab.

To create a new statement template, navigate to "Statement Templates" from a given Business Dimension context and click the “New” button. To update an existing statement template, click on its "Number" value.

Complete the fields in the form as described in the table below:

| Field | Description |
| --- | --- |
| Field | Description |
| Use dynamic value | Check this field if you want to use a Cloudability business dimension, account group, tag, or internal measure as the value for this statement |
| Dynamic value | Select a Cloudability business dimension, account group, tag, or internal measure |
| Value | Enter a text value. The text can include variables from the Columns list. |

Variables as values

You can add variable (column) values to the Value field by clicking the Columns button. Select one or more columns and close the dialog box. The column names are automatically copied to your clipboard. You can paste the clipboard contents into the Value field.

The variables in the Value field must be in the following format:

${<column name>}

If you use the Columns button to select column names they will be properly formatted when you paste them into the Value field.

3. Create/Update Statement Groups

Each statement template is made up of one or more statement groups which are used to form the statement match expression. Each group will be logically ANDed together when the match expression is determined. You can create new or update existing statement groups from a statement template on a draft business dimension. Open a statement template. Click on the “Statement Groups” tab. To create a new statement group, click the “New” button. To update an existing statement group, click on its Number value.

Click "Set Conditions" and configure the match conditions applied for a given Statement Group.

| Field | Description |
| --- | --- |
| Field | Description |
| Dimension | Select a Cloudability business dimension, account group, tag, or internal measure |
| Operator | Select the operator which will be used to compare the Dimension against the Value |
| Value | Enter a text value. The text can include variables from the Columns list. |

4. Publish a ServiceNow Business Dimension

To update a Cloudability business dimension from ServiceNow you must first publish the ServiceNow business dimension. Only business dimensions with a status of “Draft” can be published.

Open a draft business dimension. Click the Publish button.

The status of the business dimension will be changed to one of two values:

Published

If the effective date on the business dimension is current or in the past the status is changed to “Published” and Cloudability is updated immediately.

Pending

If the effective date on the business dimension is in the future the status is changed to “Pending”. Cloudability is not updated immediately.

When the effective date becomes current the status will change to “Published”, Cloudability will be updated, and any previously published version will be retired.

---

## Connect Turbonomic and Cloudability

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connect Turbonomic and Cloudability
- **source_path:** SSVCLNQ/admin/connect-turbonomic.html
- **original_file:** cloudability-connect-turbonomic.md
- **images:**
  - 03-media/apptio-cloudability-standard/turbonomics_usermanagement.jpg
  - 03-media/apptio-cloudability-standard/turbonomics_usermanagement2.jpg

## Connect Turbonomic and Cloudability

This integration enables Apptio Cloudability customers to leverage Turbonomic insights within Cloudability.

Before you start

You need to have a local user in Turbonomics. In case you don’t have a local user, you are required to create one.

Integration Steps

1. Click to navigate to the Settings Page. From there, you can perform a variety of Turbonomic configuration tasks.
1. Select User Management . This page lists all the user accounts that you currently have configured for Turbonomic .
1. Click on a new local user account.
1. Enter the username and password for the new user, and specify the role.
1. Select a role for the local user from the list below. Advisor- Users with this role can view all Turobnomic charts and data, and run plans. However, users cannot use Place to reserve workloads, create policies, or execute any recommended actions. Automator - Users with this role can use all Turobnomic features (including Plan, Park, and Place), but cannot configure Turbonomic installation or create policies. Deployer- Users with this role can view all Turobnomic charts and data, use Place to reserve workloads, and create placement policies and templates. However, users cannot run plans or execute any recommended actions. Observer- Users with this role can view the environment, including the Home Page and Dashboards. Users can also use Search to set a scope to the session. For scope, only VM groups and Resource Groups are supported. Note the username and password of the newly created local user. Specify the Authorization – Scope (optional). The scope limits what the user can monitor in your environment.

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > Turbonomic . The Add Turbonomic Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > Turbonomic . Select Add a Credential . The Add a Credential panel opens.

1. Select Add a Credential . Enter the Turbonomic credentials Turbonomic IP/URL (with https), Username , and Password .
1. Click Save .
1. Click Verify Credential . Note: A green tick mark indicates that the verification is successful. If not, a red cross will be displayed. After the credentials are validated, you can change, delete, or refresh the credentials. To modify a credential, select Edit . To delete a credential, select Delete . To validate a credential, select Refresh .

---

## Connecting with AWS - Customer Integration Guide

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connecting with AWS - Customer Integration Guide
- **source_path:** SSVCLNQ/admin/aws-credentialing-standard-enterprise-home.html
- **original_file:** cloudability-connecting-aws-customer-integration-guide.md
- **images:**
  - 03-media/apptio-cloudability-standard/curP.png
  - 03-media/apptio-cloudability-standard/curP1.png
  - 03-media/apptio-cloudability-standard/AWS-VC.png
  - 03-media/apptio-cloudability-standard/clip_image001_1499665667.png
  - 03-media/apptio-cloudability-standard/clip_image002_-1577046812.png
  - 03-media/apptio-cloudability-standard/AWSp.png

## Connecting with AWS - Customer Integration Guide

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

---

## AWS - Obtaining Memory Metrics for EC2 Instances - Windows & Linux

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connecting with AWS - Customer Integration Guide > AWS - Obtaining Memory Metrics for EC2 Instances - Windows & Linux
- **source_path:** SSVCLNQ/admin/aws-credentialing-standard-enterprise-memory.html
- **original_file:** cacig-aws-obtaining-memory-metrics-ec2-instances-windows-linux.md
- **images:**
  - 03-media/apptio-cloudability-standard/AWS-cloudwatch.jpg

## AWS - Obtaining Memory Metrics for EC2 Instances - Windows & Linux

The Cloudability Rightsizing Engine evaluates the underlying resource utilization for each EC2 instance and recommends instance types that are well matched to each utilization profile. The end goal is to keep your costs down while being mindful of operational risks.

To get the most accurate recommendations, there are four utilization metrics that need to be assessed: CPU, Disk IOPS (in the case of instances that have local disks), Network Bandwidth, and Memory Utilization. For a number of very good reasons, we’ve taken the approach of pulling this data directly from CloudWatch. The key reason being that hypervisor level metrics are saved to CloudWatch by default for each instance without you doing anything. This leaves Memory Utilization as the only metric that requires a little extra effort on your end to publish to CloudWatch. This is done using what AWS calls Custom Metrics which you can read about .

The good news is that AWS has come up with standard formats for memory data publication and we’ve taken a streamlined approach to ingest that data. We require only one custom metric to be published using the current unified agent.

Steps for integration

AWS Unified Agent

This is the preferred method for memory data. Cloudability supports the standard location and naming conventions that the unified agent uses when writing custom metrics to Cloudwatch. These details are:

- metric-name : "mem_used_percent" (for Linux)
- metric-name : "Available Mbytes" (for Windows)
- namespace : CWAgent
- dimensions : InstanceId (it’s important to only add this one dimension)
- unit : percent

Instructions

AWS provides a number of options for installing the agent which you can find at https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/install-CloudWatch-Agent-on-EC2-Instance.html . The unified agent provides capabilities to publish many types of custom metrics.

The following is an example of a minimal Linux configuration to publish just the memory information:

The following is an example of a minimal Windows configuration to publish just the memory information:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						],
						"resources": [
						"*"
						]
						}
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				} 

```

The following is an example of a minimal Windows configuration to publish just the memory information:

```
{  
						"metrics": { 
						"metrics_collected": { 
						"Memory": { 
						"measurement": [ 
						{"name": "Available Mbytes", "unit":"Megabytes"} 
						], 
						"resources": [ 
						"*" 
						] 
						} 
						},  
						"append_dimensions": { 
						"InstanceId": "${aws:InstanceId}" 
						} 
						} 
						} 

```

If you do wish to publish multiple dimensions you can rely on the aggregation_dimensions keyword as shown in the Linux example below. The extra dimension in this case is AutoScalingGroupName. In this example, you'll end up with three published memory metrics each with a different dimension combination 1) just InstanceID 2) just AutoScalingGroupName 3) both InstanceID and AutoScalingGroupName.

The following is a Linux example:

```
{   
						"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						],
						"resources": [
						"*"
						]
						}
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				} 

```

Perl Based Agent

Please note that AWS has deprecated the perl based agent but it remains available for download. Cloudability will continue to support this method however we recommend you switch to the newer unified agent if possible.

As stated above only one custom metric is required. The perl based metric looks like this:

- metric-name: MemoryUtilization
- namespace: System/Linux or Windows/Default
- dimensions: InstanceId (it’s important to only add this one dimension)
- unit: percent

Instructions

Install the perl CloudWatch monitoring scripts as described on this AWS webpage. You'll find instructions on this page for installing the pre-requisite packages on machines running the Amazon Linux AMI and other popular operating systems such as Red Hat.

Here is the crontab configuration we use at Cloudability for Linux machines:

```
*
* * * * ~/aws-scripts-mon/mon-put-instance-data.pl --mem-util --from-cron
```

This will publish exactly what Cloudability requires and nothing more. You should be able to confirm that the memory metric is reported at 5 min intervals.

Other options: Other options include creating your own agent which integrates with the AWS SDK. Here is an example using Golang that some of our customers have had success with.

How to confirm success

Normally within 24 hours of configuring your EC2 instance, this memory information will become available within Cloudability rightsizing.

Here is an example of the resultant memory data when viewing in the AWS Cloudwatch console. This can be helpful for debugging purposes.

Having this memory data within CloudWatch is going to provide benefits well beyond Cloudability and we’d highly recommend going down this path. For example, you could use the memory data to trigger autoscaling events or trigger alarms. Once you find what method works for you, it’d be a good idea to roll that up into your configuration.

Getting Recommendations Based on GPU Data Cloudability enables users to view recommendations based on GPU data from AWS EC2 instances.

Cloudability ingests GPU processing and memory utilization data from your AWS instances. This will allow Cloudability to make rightsizing recommendations that also consider this data. For example, if you are not using GPUs then you could be recommended to move to an instance type that does include GPUs so you can save money.

Cloudability provides 2 options for collecting GPU data:

Option 1: Use AWS CloudWatch Agent (Linux only)

In order to begin ingesting the GPU utilization data using AWS CloudWatch Agent, you must first setup your agent to provide this data: https://docs.aws.amazon.com/AmazonCloudWatch/latest/monitoring/CloudWatch-Agent-NVIDIA-GPU.html

The following is an example of a minimal Linux configuration to publish just the memory and GPU information:

```
"metrics": {
						"metrics_collected": {
						"mem": {
						"measurement": [
						"mem_used_percent"
						]       
						},
						"nvidia_gpu": {
						"measurement": [
						"utilization_gpu",
						"utilization_memory"
						]
						}    
						},  
						"append_dimensions": {
						"InstanceId": "${aws:InstanceId}"
						} 
						}
				} 

```

Option 2: Use GPU Monitoring Agent (both Linux & Windows)

In order to begin ingesting the GPU utilization data, you must use the GPU monitoring agent .

Before you start

Your VM should have the following:

- GPU enabled
- Nvidia drivers installed
- Python 2.7 or higher installed

Steps for integration

Instructions for Linux VMs

Run the Python script

1. Install Python 2.7 or higher if it is not available already and make it the default Python version.
1. Install pip >= 20.3.4 if it is not available already.
1. Given that your instance is already running on the GPU Enabled AMI, you need to create an IAM role that grants your instance the permission to push metrics to Amazon CloudWatch. Create an EC2 service role that allows for the following policy: { "Version": "2012-10-17", "Statement": [ { "Action": [ "cloudwatch:PutMetricData", ], "Effect": "Allow", "Resource": "*" } ] }
1. Get the custom gpumon script from https://community.apptio.com/viewdocument/custom-gpumon-python-script-to-coll and place it in the targeted VM.
1. Install all the dependencies. For Python 2.7: sudo pip2.7 install Nvidia-ml-py boto3 For Python 3 or higher: sudo pip install Nvidia-ml-py boto3
1. Run the given command in the background: python gpumon.py <Region> <log file path>

For example: nohup python gpumon.py <AWS-Region> <log file path> &

Install and run Datadog agent

1. Follow the given doc to set up the Datadog agent at https://docs.datadoghq.com/integrations/nvml/ .

Run the following Agent integration install command in place of the command provided in the Datadog documentation:

```
sudo -u dd-agent datadog-agent integration install -t
datadog-nvml==<INTEGRATION_VERSION>
```

Instructions for Windows VMs

1. Install Python 2.7 or higher.
1. Given that your instance is already running on the GPU Enabled AMI, you need to create an IAM role that grants your instance the permission to push metrics to Amazon CloudWatch. Create an EC2 service role that allows for the following policy: { "Version": "2012-10-17", "Statement": [ { "Action": [ "cloudwatch:PutMetricData", ], "Effect": "Allow", "Resource": "*" } ] }
1. Set up the path of Python to Windows environment variables.
1. Get the custom gpumon Python script from https://community.apptio.com/viewdocument/custom-gpumon-python-script-to-coll update the log file path according to the Windows file directory.
1. Run the command in administrator mode to install all the dependencies. For Python 2.7: pip2.7 install Nvidia-ml-py boto3 For Python 3 and higher: pip install Nvidia-ml-py boto3
1. Run the script to collect the GPU utilization data and push it to cloud watch using the following command in administrator mode: python gpumon.py <AWS-Region> <log file path>.

Install and run the Datadog agent

1. Install the Datadog agent in your Windows VM.
1. Set the path ( C:\Program Files\Datadog\Datadog Agent\bin ) to the environment variables of Windows.
1. Run this command: agent integration install -t datadog-nvml==<INTEGRATION_VERSION>
1. Install pip in Windows in the given path of the Python executable which is used by Datadog ( C:\Program Files\Datadog\Datadog Agent\embedded3 ).
1. In the command prompt in administrator mode, navigate to the path C:\Program Files\Datadog\Datadog Agent\embedded3\Scripts , then run the following command to install the package. pip3 install grpcio pynvml
1. Edit the nvml.d/conf.yaml file, in the conf.d/ directory at the root of your Agent’s configuration directory to start collecting your NVML performance data. See the sample nvml.d/conf.yaml for all available configuration options.
1. Restart the Agent.

---

## AWS Credentialing using Bulk Actions

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connecting with AWS - Customer Integration Guide > AWS Credentialing using Bulk Actions
- **source_path:** SSVCLNQ/admin/aws-credentialing-bulk-actions.html
- **original_file:** guide-aws-credentialing-using-bulk-actions.md
- **images:** []

## AWS Credentialing using Bulk Actions

Bulk Actions on Vendor Credentials screen allows admins to quickly complete the advance credentialing process within Cloudability.

1. Save multiple non credentialed accounts quickly
1. Update multiple accounts
1. Bulk verify multiple accounts to complete the credentialing process in an easier and faster way.

Prerequisites

Instructions

Save New Credentials

1. This screen will not show up if there are no accounts configured using Automated credentialing of linked accounts.

1. Select the accounts which are needed to be credentialed.
1. Click on Review Selection Add SCP region as required for AWS.
1. Click on Save.

1. Once save is complete, the accounts will move to Unverified status.
1. Please download the Cloud Formation template from one of the accounts which was saved and apply it to the AWS accounts in the AWS console as a stackset.
1. Once completed, please trigger verify account(s) for the accounts selected in the previous step.

Update Credentials

1. Select the accounts which are needed to be updated.
1. Click on “Review Selection” Add SCP region as required for AWS.
1. Click on Save.

This would trigger the bulk update process and the bulk actions button would be disabled until the process completes.

Once completed, please trigger Verify Credentials.

Verify Credentials

This screen displays all the accounts except the ones with Credentials Needed status (X).

1. Select the accounts which are needed to be verified.
1. Click on Review Selection
1. Click on Verify.

This would trigger the bulk verify process and the bulk actions button would be disabled until the process completes.

---

## AWS Linked Account Credentialing

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connecting with AWS - Customer Integration Guide > AWS Linked Account Credentialing
- **source_path:** SSVCLNQ/admin/aws-credentialing-standard-enterprise-linked.html
- **original_file:** guide-aws-linked-account-credentialing.md
- **images:**
  - 03-media/apptio-cloudability-standard/AWS-linked1.png
  - 03-media/apptio-cloudability-standard/clip_image002_1065401583.png
  - 03-media/apptio-cloudability-standard/clip_image003_1276902897.png
  - 03-media/apptio-cloudability-standard/AWS-linked2.png
  - 03-media/apptio-cloudability-standard/clip_image002_1795777736.png
  - 03-media/apptio-cloudability-standard/clip_image003_-445731613.png

## AWS Linked Account Credentialing

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

---

## AWS Tags

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connecting with AWS - Customer Integration Guide > AWS Tags
- **source_path:** SSVCLNQ/admin/support-for-aws-tags.html
- **original_file:** guide-aws-tags.md
- **images:**
  - 03-media/apptio-cloudability-standard/Tag1.png
  - 03-media/apptio-cloudability-standard/tag2.png
  - 03-media/apptio-cloudability-standard/tag3.png
  - 03-media/apptio-cloudability-standard/tag4.png
  - 03-media/apptio-cloudability-standard/tag5.png
  - 03-media/apptio-cloudability-standard/tag6.png
  - 03-media/apptio-cloudability-standard/tag7.png
  - 03-media/apptio-cloudability-standard/tag8.png
  - 03-media/apptio-cloudability-standard/tag9.png

## AWS Tags

Cloudability supports the below tags for AWS:

- Resource level tags These are part of the AWS CUR files and no extra permissions are required within Cloudability for enabling these
- Account level tags To get account level tags from AWS Organizations, Cloudability needs an additional permission named organizations:ListTagsForResource These are displayed in the below format in Cloudability cldy:aws:accountLevelTag:<tag key> Note: If a customer switches from legacy CUR to CUR 2.0, then they have to reconfigure their Tags and Labels within Cloudability. Account level tags are currently not available in Cloudability Gov. Difference between AWS Legacy CUR and CUR 2.0 tags Legacy CUR tags format aws tags = aws:<tagkey> e.g. aws:autoscaling:groupname user tags = <tagkey> e.g. application CUR 2.0 tags format aws tags= aws_<tag key will be separate with _> =e.g. aws_autoscaling_group_name user tags = user_<tagkey> e.g. user_application

In order to enable the resource level tags , please ensure you have enabled the below:

In the AWS Console - Enable cost allocation tags

- From the Billing & Cost Management Dashboard , navigate to Cost Allocation Tags .
- Select the tags that you want to include
- Note – Please be mindful of camel case, example if you have “Name” or “name” as a tag key – both needs to be activated so they are written to CUR.
- Select Activate .

In Order to enable account level tags from AWS Organizations, Cloudability needs an additional permission named organizations:ListTagsForResource

If you are an existing AWS customer in Cloudability, you can enable this feature using two options:

Option 1 - Re-credential your AWS master payer account(s) for which you want to enable AWS account level tags

1. Go to IAM Dashboard in AWS and click on Roles .
1. Search for the role that you assigned to Cloudability. If you have not renamed the role, it should show up as CloudabilityRole . Click on this role.
1. Under Permission policies , click on CloudabilityManagementAccountPolicy
1. Click Edit .
1. Switch to Visual view on the top right. Expand Organizations .
1. Check the permission ListTagsForResource .
1. Select Next .
1. Under Review & save, click Save Changes .
1. Verify that the permission shows a green tick under the Cost tab in the permissions pane (displayed on click of eye icon for the respective master account) in Cloudability, as below:

---

## Frequently Asked Questions for Connecting with AWS

<!-- sub-header -->
- **breadcrumb:** Getting data into Cloudability > Connecting with AWS - Customer Integration Guide > Frequently Asked Questions for Connecting with AWS
- **source_path:** SSVCLNQ/admin/aws-credentialing-standard-enterprise-faq.html
- **original_file:** guide-frequently-asked-questions-connecting-aws.md
- **images:** []

## Frequently Asked Questions for Connecting with AWS

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

---

## How to Request a New Or Updated SSO/Certificate

<!-- sub-header -->
- **breadcrumb:** Getting started > How to Request a New Or Updated SSO/Certificate
- **source_path:** SSVCLNQ/chatbot/chatbot-sso.html
- **original_file:** started-how-request-new-updated-ssocertificate.md
- **images:** []

## How to Request a New Or Updated SSO/Certificate

How to Request a New SSO Install

Overview

1. Submit a Support Ticket: Once support has received the required files and Questions below .
1. Testing and Validation Call: Once you have configured your (IdP) side of the federation, notify your Apptio engineer, Apptio will schedule a call to test Single Sign On (SSO).
1. Enablement Call: If necessary, Apptio will conduct a third call to permanently enable SSO.

More information about Apptio's SSO platform

- Partner / EntityID: urn:federation:apptio
- If you configure "audience restriction" in your SSO, set the value to: urn:federation:apptio "https://federation.apptio.com/apptio-pf-metadata.zip" "https://federation.apptio.com/metadata.xml" "https://federation.apptio.com/sso_certificate.txt" "https://pfidentity.apptio.com/sp/acs.saml2"
- SAML Protocol: SAML 2.0
- Allowable SAML Bindings: POST and Redirect (GET)
- Supported SAML Profiles: SP-initiated (default) and IdP-initiated

Required attributes

- mail: Unique identifier (email address of the user). This must at least look like an email address in the format: user@domain
- fullname: An attribute that contains the First and the Last name. Format can be whatever your internal standard is (e.g. ‘First Last’ or ‘Last, First’ or ‘Last First’ ).

- Apptio can only support integrations with customer SSO systems that are fully SAML 2.0 compliant. Ensure that your system meets this specification.
- If you want to use multi-factor-authentication (a.k.a. MFA or 2FA), it must implemented in your own SSO system. Apptio cannot manage MFA for customers.

How to Request an Updated Certificate

If you have enabled SSO and require certificate renewal, the process is straightforward. To initiate the renewal, submit a support request with the following details:

- A copy of the new metadata file
- Expiry date and time of the certificate

Upon receiving the new file, Apptio will schedule the switch and handle any incidents that may arise during the process. For more information, reach out to technical support team.

Apptio Questions

1. Partner Federation Platform: What SSO Platform are you using and does it support SAML 2.0?
1. Does the TBM Team deploying Apptio intend to use Billing Standard or IT Finance variance report email capabilities? If the TBM Team wants to use these emails which include deep links to specific reports, then it is required that SP-initiated workflow be enabled. This does not exclude the ability to also have an IDP-initiated workflow configured and used, but SP-initiated is a necessary condition for successful use of these emails.
1. Role Management
1. Role management is done inside Apptio by default. Hence, new users are not automatically created and would receive an authorization error. Will this meet your role management requirements?
1. Apptio allows roles to be managed by the identity provider, would you like to also send us a role assertion?

Your provider can send us an assertion in the role attribute. Information on supported roles and permissions across different applications is available in the Apptio Help Center, under Access Administration > Manage user permissions and roles .

1. IdP Initiated: Will you need support for IdP-initiated logins?
1. Login Preference It is important to Apptio to provide a secure Technology Business Management experience for our customers. Our customers who use a single-sign on (SSO) identity provider (IdP) can employ one of two options.\\\
1. User is required to enter their SSO credentials to access Apptio products during any of the following scenarios: Accessing Apptio product URL for the very first time (OR) Accessing Apptio product URL after explicitly logging out (OR) Accessing Apptio product URL after the user session was terminated due to inactivity (60 minutes of continuous inactivity in Apptio)

User authentication to your IdP occurs prior to accessing Apptio . This option allows users to access Apptio as long as there is an established session with your IdP. This requires no additional login steps, unless user does not have an existing session with your IdP. This means that if users closes the browser or navigate away, so long as there is a session with the IdP, when they return they will be instantly logged in without additional requests for credentials.

1. Testing Environment: Will you be using a Staging or UAT Federation environment before configuring this federation in production?
1. Signature and Encryption
1. Sign AuthN Requests? YES/ NO By default Apptio does not expect the AuthN request to be signed
1. Encrypt Entire Assertion? YES/NO By default Apptio does not expect the entire SAML assertion to be encrypted

Next Steps

1. Setup your SP connection with the provided metadata file.
1. Please reply-all to this email and include your metadata file, as well as the answers to the Apptio questions.
1. Once your SP connection is setup, we will schedule a time to conduct a test and validation.

The Apptio support team can also investigate specific slowdowns in your environment with the help of HAR files. To learn how to collect a HAR file, visit Apptio Community page.

---
