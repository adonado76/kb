---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect Databricks"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Databricks"
source_path: "SSVCLNQ/admin/connect-databricks.html"
images:
  - "03-media/apptio-cloudability-standard/Databricks-Service-Principle.png"
  - "03-media/apptio-cloudability-standard/Databricks-Add-Service-Principle.png"
  - "03-media/apptio-cloudability-standard/Databricks-Add-Service-Principle-permission.png"
  - "03-media/apptio-cloudability-standard/Databrick-Runtime.png"
  - "03-media/apptio-cloudability-standard/clip_image001_-1832790195.png"
  - "03-media/apptio-cloudability-standard/clip_image002_-821243953.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect Databricks

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
