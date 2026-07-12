---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connecting with Azure MCA - Cost Management Exports"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
  - "Connecting with Azure MCA - Cost Management Exports"
source_path: "SSVCLNQ/admin/azure-cm-exports-mca.html"
images:
  - "03-media/apptio-cloudability-standard/blobid1.jpg"
  - "03-media/apptio-cloudability-standard/blobid0.jpg"
  - "03-media/apptio-cloudability-standard/blobid5.jpg"
  - "03-media/apptio-cloudability-standard/new-create_a_new_csv_export.jpg"
  - "03-media/apptio-cloudability-standard/updated_new_import.jpg"
  - "03-media/apptio-cloudability-standard/Azure-EA-Enrollment-id.png"
  - "03-media/apptio-cloudability-standard/updated_tenant_id.jpg"
  - "03-media/apptio-cloudability-standard/resource_group_name.jpg"
  - "03-media/apptio-cloudability-standard/updated_storage_account.jpg"
  - "03-media/apptio-cloudability-standard/blobid9.jpg"
  - "03-media/apptio-cloudability-standard/clip_image001_-1832790195.png"
  - "03-media/apptio-cloudability-standard/clip_image002_-821243953.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connecting with Azure MCA - Cost Management Exports

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
