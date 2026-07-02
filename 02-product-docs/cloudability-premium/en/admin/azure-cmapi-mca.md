---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connecting with Azure MCA – Cost Details API"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
source_path: "admin/azure-cmapi-mca.html"
images:
  - "images/Azure-MCA-Cost-Details-API.png"
  - "images/Azure-PowerShell-Upload.jpg"
  - "images/CLDY-Vendor-Creds-Azure-Verified.png"
  - "images/billing-mca-property.png"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image002_-821243953.png"
  - "images/copy-subscription-id.png"
  - "images/copy-tenant-id.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connecting with Azure MCA – Cost Details API

**Overview**

This guide walks you through the process of securely connecting your Azure MCA environment to IBM
Cloudability via Azure Cost Details APIs.

Cost Details API is an alternate credentialing mechanism for Azure Customers. Once connected,
you’ll gain access to the FinOps experience in Cloudability. In this process we’ll create a Service
Principle within your Azure account which will help Cloudability pull the Billing data.

Note: Cloudability recommends using Azure exports for credentialing Microsoft Azure. Click  [here](azure-cm-ea.html)  to setup Azure exports. Microsoft Azure also recommends using
 [exports](https://learn.microsoft.com/en-us/azure/cost-management-billing/automate/usage-details-best-practices "(Opens in a new tab or window)")  as a best practice for large datasets. (More than 2 GB
month-to-month)

To ensure full compatibility and support, please follow the connection steps as
described. Custom configurations are not supported. If you have questions, reach out to **IBM
Support**.

**Prerequisites**

Before you begin, ensure you have access to:

- Azure MCA Portal

- Enterprise Admin (or a minimum of Enrollment Writer, or your organizations equivalent) role in
  Azure

- Administrator access to Cloudability Vendor Credentials page

Cloudability’s Azure Cost Details API Credentialing process requires 2 main steps:

- Billing Account Credentialing

- Subscription Credentialing

**Billing Account Credentialing**

Cloudability uses Billing Account credentialing for bringing in the Azure Cost and Usage data,
resource level, resource group tags for credentialed Billing Account(s).

The credentialing process involves a few steps which will require you to take actions in both
Azure Portal and Cloudability at various phases.

Let’s get started with the Credentialing process:

1. **In the Azure Portal :**

   1. Locate your **Billing account ID** (Enrollment ID).
      1. Search for **Cost Management + Billing** and select it from the list to open the Cost
         Management + Billing Overview page.
      2. Select the billing scope
      3. **Navigate to Settings, Click on properties,** copy and save your **Billing account
         ID**(Enrollment ID).

         ![](../../../../03-media/cloudability-premium/images/billing-mca-property.png)
   2. Locate your **Tenant ID**
      1. Search for **Microsoft Entra ID** and select it to load the Active Directory Overview page.
      2. Copy and save the **Tenant ID**

         ![](../../../../03-media/cloudability-premium/images/copy-tenant-id.png)
   3. Get your S**ubscription ID**
      1. From the list of subscriptions under the same billing account.
      2. Copy one of the **Subscription ID** and save it.

         ![](../../../../03-media/cloudability-premium/images/copy-subscription-id.png)
2. **In Cloudability - Configure Credentials for Azure Billing Account**

   You must have Cloudability Administrator rights to complete this procedure.

   If you don’t have administrator rights, contact your organization’s primary Cloudability
   administrator for assistance.

   1. In Cloudability , navigate to **Settings**> **Vendor Credentials**> **Add Datasource and
      select Azure - EA**
   2. Enter the Azure **Enrollment ID (Billing Account ID), Tenant ID and Subscription ID.**
   3. Enter “**NA**” in all other fields.
   4. Click on **Generate Setup Script.**
   5. A PowerShell Script will be downloaded.![](../../../../03-media/cloudability-premium/images/Azure-MCA-Cost-Details-API.png)
3. **In Azure Portal - Upload the PowerShell script** 

   The next step is to grant Cloudability
   access to read the cost and usage data from your Azure storage by running the setup script in your
   Azure Portal Cloud Shell.

   1. Execute the PowerShell script in the PowerShell console (or natively)
   2. To run the script:
      1. Log in to the Azure Portal and switch to the required tenant
      2. From the Azure Portal, launch the Cloud Shell and select PowerShell as the scripting language.
      3. After the Cloud Shell has initialized, select **Upload** from the Cloud Shell terminal
         menu.

         ![](../../../../03-media/cloudability-premium/images/Azure-PowerShell-Upload.jpg)
      4. Upload the setup script file provided by Cloudability.
      5. Run the script by typing:

         Note:

         >: ./<YOUR\_SCRIPT\_NAME\_HERE>.ps1
   3. This PowerShell script will create a Service Principle called as
      “**CloudabilityUtilizationDataCollector**”.

      Note: This should add Billing Account Reader role to the Cloudability Service Principal
4. **In Cloudability - Verify the Billing account credential**
   1. In Cloudability , navigate to **Settings > Vendor Credentials > Azure.**
   2. Click on the … next to the account being credentialed and select Re-Verify.
      1. A green tick (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png))
         indicates success whereas a red exclamation (![](../../../../03-media/cloudability-premium/images/clip_image002_-821243953.png)) indicated errors

In the event that verification fails, please retry after 15 minutes.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and Azure tags within Cloudability.
- Pricing data would also be pulled in.
- Cloudability will also display the Subscriptions

As a next step you will need to credential the Subscriptions.

![](../../../../03-media/cloudability-premium/images/CLDY-Vendor-Creds-Azure-Verified.png)

**Subscription Account Credentialing**

As a next step please continue to the **Set up Advanced Credentials, Azure Rightsizing and
Reserved Instance Planning** instructions. Putting these permissions in place will help bring in
the Azure subscription tags and utilisation data which helps in using the Optimize features of
Cloudability.

**Frequently Asked Questions**

1. **I don’t see any cost data after completing the account credentialing steps, what should be
   done?**

   Please check if the account is successfully verified (shows a green tick mark). If it does wait
   for 24 hours for the data else reach to Cloudability support team.

   If the account is not verified
   (shows red!), Please check the configurations again and confirm all details are accurate AND that
   the script has been executed in your environment.
2. **I recently turned on Azure and credentialed the accounts in Cloudability. How long will it
   take to see the Cost and Usage data?**

   It may take up to 24 hours for your first Cost data to get displayed in Cloudability.
3. **How do I update to the latest PowerShell template for permissions?**

   This can be done using Cloudability Manage Azure credentials.

   1. To regenerate the PowerShell template to reconfigure your Azure access, do the following:

      1. In Cloudability , navigate to **Settings > Vendor Credentials > Azure**.
      2. Save and download the current **PowerShell** template.
      3. In Azure Portal, install the template.
      4. On successful update, re-verify the account.
4. **Can we ingest historical cost data in Cldy? If yes, how far back data can be ingested?**

   Yes, we can. Cost details APIs allows data to be fetched for 13 historical months.

   For
   requirements around historical data please raise a support ticket.
5. **When should I use Cost details API for Azure.**

   Cost details API for Azure is recommended for smaller datasets, preferably less than 2GB.
6. **At first credentialing how much historical data Cloudability will bring in?**

   Cloudability will bring current and previous months cost data.
7. **How do I migrate from Azure Cost Details API to Azure Details Exports?**

   This would require re credentialing of accounts. Please follow the credentialing steps for Azure
   exports.
8. **Is changing of the content of the PowerShell script generated by Cloudability
   recommended?**

   This is not recommended as an approach as for Cloudability to function correctly it needs the
   service principle and the roles assigned within the PowerShell script. Any changes to the script are
   unsupported.

**Parent topic:** [Connect Microsoft Azure](../admin/azure-cm-setup-premium.html)
