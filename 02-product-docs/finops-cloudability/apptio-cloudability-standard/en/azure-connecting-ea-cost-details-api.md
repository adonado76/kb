---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connecting with Azure EA – Cost Details API"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
  - "Connecting with Azure EA – Cost Details API"
source_path: "SSVCLNQ/admin/azure-cmapi-ea.html"
images:
  - "03-media/apptio-cloudability-standard/Azure-EA-Billing-id.png"
  - "03-media/apptio-cloudability-standard/copy-tenant-id.png"
  - "03-media/apptio-cloudability-standard/copy-subscription-id.png"
  - "03-media/apptio-cloudability-standard/Azure-EA-Cost-Details-API.png"
  - "03-media/apptio-cloudability-standard/Azure-PowerShell-Upload.jpg"
  - "03-media/apptio-cloudability-standard/clip_image001_-1832790195.png"
  - "03-media/apptio-cloudability-standard/clip_image002_-821243953.png"
  - "03-media/apptio-cloudability-standard/CLDY-Vendor-Creds-Azure-Verified.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connecting with Azure EA – Cost Details API

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
