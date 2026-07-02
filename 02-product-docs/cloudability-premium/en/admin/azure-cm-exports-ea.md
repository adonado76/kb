---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connecting with Azure EA - Cost Management Exports"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
source_path: "admin/azure-cm-exports-ea.html"
images:
  - "images/Azure-EA-Enrollment-id.png"
  - "images/blobid0.jpg"
  - "images/blobid1.jpg"
  - "images/blobid5.jpg"
  - "images/blobid9.jpg"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image002_-821243953.png"
  - "images/new-create_a_new_csv_export.jpg"
  - "images/resource_group_name.jpg"
  - "images/updated_new_import.jpg"
  - "images/updated_storage_account.jpg"
  - "images/updated_tenant_id.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connecting with Azure EA - Cost Management Exports

**Overview**

This guide walks you through the process of connecting your **Microsoft Enterprise Agreement
(EA)** to IBM Cloudability via Azure Cost Management Exports.

Azure Cost Management Exports provide a granular detail containing all the raw billing and usage
data behind your Azure costs and resource tags. Cloudability requires a couple of files for this
integration:

- Cost and usage details (actual)

- Cost and usage details (amortized)

Once connected, you’ll gain access to the FinOps capabilities within Cloudability.

Note: To ensure full compatibility and support, please follow the connection steps as described.
Custom configurations are not supported. If you have questions, reach out to **IBM
Support**.

**Prerequisites**

Before you begin,

Ensure that you have one of the following Azure Active Directory roles in your organization:

- Global Administrator or Enterprise administrator.
- Enrollement Writer or equivalent role to assign the Enrollment reader role

For the Azure portal, you must have permissions provided by one of these [Azure scopes](https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/understand-work-scopes "(Opens in a new tab or window)") to create the billing data export.

- Owner (can view/manage everything, including cost configuration)

- Contributor (can view/manage everything, including cost configuration, excluding access control)

- Cost Management Contributor (can view/manage cost configuration)

- Admin access to the Cloudability Vendor Credentials

**Getting Started:**

Cloudability’s Azure Credentialing process requires two main steps:

- Azure Billing Account Credentialing

- Azure Subscription Account Credentialing

Azure Billing Account Credentialing process involves a few steps which will require you to take
actions in both Azure portal and Cloudability at various phases.

During this process Cloudability will

- Add Cloudability’s Service Principal “CloudabilityUtilizationDataCollector” and assign
  “CloudabilityCostDataReader” role to it.

- CloudabilityCostDataReader role is used for getting the cost and usage data using the Azure built
  in [Storage Blob Data Reader role](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles/storage#storage-blob-data-reader) "(Opens in a new tab or window)").

- Uses Enrollment Reader role which provides read-only access to enterprise billing data

Note: An EnrollmentReader Role can be assigned to an SPN only by a user who has an enrollment writer
role e.g Enterprise Administrator /Global Administrator or equivalent.

**Step 1 - Azure Portal - Create an Azure Cost Details Export**

Note: Cloudability recommends using Azure exports for credentialing Microsoft Azure.

Microsoft
Azure also recommends using  [exports](https://learn.microsoft.com/en-us/azure/cost-management-billing/automate/usage-details-best-practices "(Opens in a new tab or window)")  as a best practice for large datasets (more than 2 GB
month-to-month).

1. From the Azure Portal, search for  Cost Management + Billing  , and
   select it from the list to open the  Billing Scopes  page. For example:

   ![](../../../../03-media/cloudability-premium/images/blobid1.jpg)
2. From the  Cost Management + Billing  page, ensure you have selected the
   correct Billing Scope. If you have multiple, select the scope with the majority of your cloud
   spend.

   ![](../../../../03-media/cloudability-premium/images/blobid0.jpg)
3. From the  Cost Management + Billing  console, select  Exports 
   from the navigation panel to open the Azure export utility.

   ![](../../../../03-media/cloudability-premium/images/blobid5.jpg)
4. Select  Create  to open the export page for creating a
   new CSV export.

   ![](../../../../03-media/cloudability-premium/images/new-create_a_new_csv_export.jpg)
5. Create a new export for
   1. **Cost and Usage (actual)**:
      1. Type of data: Cost and Usage (actual)
      2. Create an export prefix e.g.: Cloudability, then click on the cldy-actual-cost to reveal:
         1. Export name: Customer Defined Unique File Name
         2. Dataset version: 2021-10-01
         3. Frequency: Daily export of month to date costs
         4. Export Description: Optional
      3. Click Save
      4. Click Next to open Destination tab
         1. Storage type: Azure blob storage
         2. Destination and storage: Select to use an existing subscription and resource group or create new
         3. Subscription: Select destination subscription
         4. Storage account: Select storage account
         5. Container: Enter a valid container name meeting your naming standards
         6. Directory: Enter a valid directory name meeting your naming standards
         7. Format: CSV
         8. Compression Type: None or Gzip
         9. File partitioning: Retain the default selection
         10. Overwrite data: Retain the default selection
      5. Click Next
      6. On the Review and Create tab, Click Create

         ![](../../../../03-media/cloudability-premium/images/updated_new_import.jpg)
   2. **Cost and Usage (amortized)**:

      1. Follow same steps as above
      2. Ensure that the same subscription, storage account container and directory
         are used as in the previous Export creation
      3. Click Review and Create

         Note: Both CSV formatted files are required by Cloudability and must be present in the storage
         account used to collect cost management data.

         We don't recommend FOCUS data ingestion for Azure as
         the native Azure Cost Management Exports provide much more granular information.
6. Ensure the below setting are applied for the Storage account configured for exports:
   1. Navigate to Storage Accounts and select your Storage Account used for Cloudability
   2. Select Security + Networking
   3. Select Networking
   4. Click Manage
      1. Under Public Network Access, select Enable
      2. Under Public network access scope select either of the below
         1. Enable from all networks, or
         2. Enable from selected networks
            1. In this case, contact Cloudability support to obtain a range of IPs which can be whitelisted
   5. Click Save
   6. Select Security + Networking
   7. Select Encryption
   8. Click Encryption scopes
   9. Provide an encryption scope name
   10. Encryption type
       1. Microsoft managed keys (MMK)
   11. Infrastructure encryption
       1. Enabled or Disabled
   12. Click Create
7. **Gather billing data information for your Cloudability credential setup**

   After you've created your billing data exports, Cloudability needs additional information from
   your Azure Portal for the Cloudability credential setup which is called out below:

   You can find the list of all properties Cloudability needs in the Azure Portal Cost Management
   console:

| Property Name | How to find it |
| --- | --- |
| Enrollment ID | - Search for **Cost Management + Billing** and select it from the list to open the Cost   Management + Billing Overview page. - Select Billing Scopes and click the billing scope - **Navigate to Settings, click on properties,**copy and save your **Billing account ID   (**Enrollment ID) |
| Tenant ID | - Search for **Microsoft Entra ID** and select it to load the Active Directory Overview page.  - Copy and save the **Tenant ID** |
| Subscription ID | - Search for **Subscriptions** and select it to open up the subscriptions page - From the list of subscriptions under the same billing account select the subscription - Copy the **Subscription ID** where the exports were created and save it. |
| Resource group name | From the storage account  Overview  page, click the storage account link to view the Resource group name as in this example: |
| Storage account name  Container name  Directory name  Cost export name  Amortized export name | - Search for **Cost Management + Billing** and select it - Navigate to Exports under settings to display a table with your billing data storage   account. - Scroll to the right and select the storage account for your billing data to open the Overview   page, where you can view the   - Storage account name,   - Storage container name,   - Storage directory name,   - both the actual cost export and amortized cost export file names: |

**Step 2 - Cloudability - Credential using the billing data information**

Once you’ve gathered the information listed in the table, you can enter it into Cloudability to
update your EA credential.

Cloudability will use this information to generate a PowerShell script. When the script is run
from your Cloud Shell in the Azure Portal or from local PowerShell scoped to your tenant, it will
create Service Principal and grant rights for Cloudability via the CloudabilityCostDataReader role
in order to provide access to the storage account.

1. In Cloudability , navigate to
   1. **Settings** > **Vendor Credentials** > **Add Datasource** > **AZURE** .
   2. Click Next
   3. Select Enterprise Agreement (EA) - the **Add AZURE Account** panel opens.Or
   4. **Settings** > **Vendor Credentials** > **Ingress** > **AZURE** .
   5. Click Next
   6. Select Enterprise Agreement (EA)  **- t**he Add a Credential panel opens.
2. Enter the information gathered from your Azure Portal into the corresponding fields
   1. Enter the Azure Enrollment ID (Billing Account ID)
   2. Tenant ID
   3. Subscription ID
   4. Resource Group Name
   5. Storage account Name
   6. Container Name
   7. Directory Name
   8. Cost Export Name
   9. Amortized Cost Export Name
3. Select **Generate Setup Script** to download the new script file.
4. Select **Close**.

You will return to verify the changes later.

**STEP 3 - Azure Portal -** **Grant Cloudability access from the Azure Portal**

The next step is to grant Cloudability access to read the cost and usage data from your Azure
storage by running the setup script in your Azure Portal Cloud Shell.

To run the script:

1. Log in to the Azure Portal and switch to the required tenant (the directory that is the at
   highest level in Azure for the target enrollment and where your Cost Management Exports are
   written).
2. From the Azure Portal, launch the Cloud Shell and select PowerShell as the scripting
   language.
3. After the Cloud Shell has initialized, select **Upload** from the Cloud Shell terminal menu.
4. Upload the setup script file provided by Cloudability.

![](../../../../03-media/cloudability-premium/images/blobid9.jpg)

1. Run the script by typing:

   ./<YOUR\_SCRIPT\_NAME\_HERE>.ps1

**Step 4 - Cloudability - Verify the Account Credential**

The final step is to verify your updated Cloudability EA credential.

1. Return to the Cloudability credentials Azure page at **Settings > Vendor Credentials> AZURE**.
2. Select the three dots on the right hand side and select Edit next to your **EA** credential.
3. Select **Verify Credential** in the panel that open.
4. Click on the … next to the account being credentialed and select Re-Verify.

A green tick (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png))
indicates success where as a red exclamation (![](../../../../03-media/cloudability-premium/images/clip_image002_-821243953.png)) indicated errors.

After completion of this process, within a few hours,

- Cloudability will start showing your Billing data and Azure tags within Cloudability.
- Pricing data would also be pulled in.
- Cloudability will also display the Subscriptions

As a next step you will need to credential the Subscriptions.

Click here to  [Set up Azure Rightsizing and Reserved
Instance Planning](azure-advanced-rightsizing.html)  for credentialing the Azure Subscriptions

**Frequently Asked Questions** 

1. **I recently turned on the Azure Cost Management Exports and credentialed in Cloudability. How
   long will it take to see the data in Cloudability?**Please refer the [cost and usage data availability documentation](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=ts-cloudability-cloudability-cost-usage-data-availability-in-reporting "(Opens in a new tab or window)")
2. **Azure Exports vs Azure Cost details API, which one should be used for integrating Azure in
   Cloudability?**Using Azure exports is the Microsoft recommended way. This is a scalable approach as when your
   data set grows exports are able to handle bigger datasets. Azure cost details API can be used for
   smaller data sets.
3. **Can we ingest historical cost data in Cloudability? If yes, how far back data can be ingested** Yes, we can via One time Exports. Please check with IBM Cloudability Support teams on how to
   bring in Historical data.
4. **Can FOCUS format be used instead of Azure exports for integration?**No. For correct integration into Cloudability and bringing in things such as Rightsizing and
   Reserved Instance and Savings Plan Azure data we recommend using exports as it provides much more
   granular information.
5. **Where Can I find Cloudability's Vendor Credentials APIs for Azure**Please refer : [Vendor Credentials End Points Azure](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=api-vendor-credentials-end-points-azure "(Opens in a new tab or window)")
6. **Do you support cost export on Billing Profiles****/Departments**Yes we can – Contact
   IBM Cloudability Support team for more information.

**Parent topic:** [Connect Microsoft Azure](../admin/azure-cm-setup-premium.html)
