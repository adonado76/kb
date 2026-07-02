---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect Microsoft Azure"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/azure-cm-setup-premium.html"
images:
  - "images/TurboTarget-other-CSPs.png"
  - "images/azure-turbonomic-integration.jpg"
  - "images/regenerate_11_35_55_am_png.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect Microsoft Azure

To configure the Cloudability credentials to access Azure cost management data by exporting a
CSV file from the Azure Portal. The CSV file captures cost and usage data and saves it to Azure
storage. The user is then provided the Cloudability access to that storage to read the data.

1. Set up cost management

   Set up CSV formatted billing data to be
   automatically exported to Azure storage on a daily basis.

   - Learn about [Connecting with Azure (MCA) -
     Cost Management Exports](azure-cm-exports-mca.html)
   - Learn about [Connecting with Azure (EA) - Cost
     Management Exports](azure-cm-exports-ea.html)
   - Learn about [Connecting with Azure (MCA) - Cost
     Details API](azure-cmapi-mca.html)
   - Learn about [Connecting with Azure (EA) - Cost
     Details API](azure-cmapi-ea.html)
2. Enable rightsizing and RI planning 

   Provide Cloudability with
   information about your billing data setup from your Azure Portal.

   - Learn about  [Setup Azure Rightsizing and RI
     Planning](azure-advanced-rightsizing-premium.html)
3. Enable collection of memory metrics 

   Provide Cloudability read-only
   access to the cost & usage data on your Azure storage.
4. - Learn about  [Setup Azure Memory Metrics Collection](azure-advanced-metrics.html)

An example of the type of information Cloudability requires from the Azure Portal is listed
below;

- tenant id
- subscription id
- resource group name
- storage account name
- container name
- directory name
- cost export name
- amortized export name

Before you start

Before you begin to set up the Cloudability credentials, confirm that you are a Cloudability
Administrator and meet the following requirements.

Ensure that you have one of the following Azure Active Directory roles in your organization:

- Global Administrator
- Application Developer
- Cloud Application Administrator
- Azure Savings Plan Reader (For Cloudability Premium customers)

For the Azure portal, you must have permissions provided by one of these Azure scopes to create
the billing data export.

Learn about [https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/understand-work-scopes](https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/understand-work-scopes "(Opens in a new tab or window)")

- Owner (can view/manage everything, including cost configuration)
- Contributor (can view/manage everything, including cost configuration, excluding access
  control)
- Cost Management Contributor (can view/manage cost configuration)

Note: In order to successfully apply the “Enrollment Reader” permission to the IAM role (required
for advanced features such as Savings Plans and Reserved Instance Planning), the user account
running the power shell script must be at least of “Enrollment Writer” role them self under EA.

For Azure Storage accounts:

- You must have "write" permissions to change the configured storage account (regardless of
  permissions on the export).
- The storage account must be configured for blob or file storage. If possible, Cloudability you
  must create a new storage account dedicated to cost management data.

For Azure Savings Plan Reader role:

If you have savings plans for your Azure workloads, enable access for Turbonomic to these
savings plans by assigning the built-in  Savings Plan Reader  role to
Cloudability's service principal.

Note: Before performing the steps below, the Cloudability application's service principal must
already exist in the Azure tenant(s) where the Savings Plan Reader role will be assigned. Follow the
steps in [Connecting with Azure (EA) - Cost
Management Exports](azure-cm-exports-ea.html), [Connecting with Azure (EA)
- Cost Details API](azure-cmapi-ea.html) , [Connecting with
Azure (MCA) - Cost Management Exports](azure-cm-exports-mca.html), [Connecting with Azure (MCA) - Cost Details API](azure-cmapi-mca.html) , and/or  [Set up Azure Rightsizing and Reserved Instance Planning](azure-advanced-rightsizing.html) sections first to create the Cloudability service principal in the tenant(s).

1. Sign in to the Azure portal with a user account that has permissions to assign roles to savings
   plans [https://portal.azure.com](https://portal.azure.com/ "(Opens in a new tab or window)")  .

   Be sure that you are working in the correct Azure directory where you will assign the
    Savings Plan Reader  role.
2. Browse to the Savings plans page: [https://portal.azure.com/#view/Microsoft\_Azure\_Reservations/ReservationsBrowseBlade/productType/SavingsPlan](https://portal.azure.com/#view/microsoft_azure_reservations/reservationsbrowseblade/producttype/savingsplan "(Opens in a new tab or window)")
3. In the  Savings Plans  page, choose  Role Assignment
    .
4. In the  Access Control  page, choose  Add Role Assignment
    .
5. In the  Add Role Assignment  page:

   1. Choose the  Role  tab.
   2. In the search bar, type  Savings Plan Reader  as your search keyword.
   3. Choose  Savings Plan Reader  from the list of built-in roles that display
      and then choose  Next.
   4. In the  Members  tab, choose  + Select members  .
   5. Search for the  CloudabilityUtilizationDataCollector  service principal.
   6. Add the service principal. Optionally, specify a description for this role assignment and then
      choose  Next  .
   7. In the  Review + Assign  tab, review your settings and then choose
       Review + Assign  .

Upon upgrading to Cloudability Premium , the  Billing Reports  and
 Advanced Reports  status for each of the Azure (EA or MCA) accounts in the
listing page will not change. However, your Cloudability admin needs to edit each subscription
account following the steps enabling Cloudability share these accounts with Turbonomic .

Note: This page requires admin permissions to access it.

1. In Cloudability , navigate to  Settings  >  Vendor
   Credentials  >  Azure  .
2. Hover your cursor over the icon of the account for which you want to download the template.
   Additional options are displayed.
3. Select the ![edit credential pencil icon](../../../../03-media/cloudability-premium/images/regenerate_11_35_55_am_png.jpg) icon to open Edit a Credential.
4. The  Edit a Credential  panel opens.
5. Select the option in  Advanced Rightsizing  toggle button.
6. Generate setup script.
7. Update the permissions by executing the script.
8. Re-verify the account.

There are additional Turbonomic permissions that gets added to basic (Billing Data), advanced
(Util- ization Data) and Optimize Resources (execute actions). Once your account is verified, the
list of permissions can be viewed by choosing the Details option on each Azure account listed under
Cloudability.

![turbonomic permissions screenshot](../../../../03-media/cloudability-premium/images/azure-turbonomic-integration.jpg)

**Credentials Status**

Cloudability Vendor credential screen displays both account status from:

- Cloudability
- Turbonomic

Once the latest templates are run the account status should be in sync between Cloudability and
Turbonomic. For details on the account status please check account details section.

![](../../../../03-media/cloudability-premium/images/TurboTarget-other-CSPs.png)

- **[Connecting with Azure EA - Cost Management Exports](../admin/azure-cm-exports-ea.html)**
- **[Connecting with Azure EA – Cost Details API](../admin/azure-cmapi-ea.html)**
- **[Connecting with Azure MCA - Cost Management Exports](../admin/azure-cm-exports-mca.html)**
- **[Connecting with Azure MCA – Cost Details API](../admin/azure-cmapi-mca.html)**
- **[Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning](../admin/azure-advanced-rightsizing-premium.html)**
- **[Azure Tags](../admin/azure-resource-group-tags.html)**
- **[Set up Azure Memory Metrics Collection](../admin/set_up_azure_memory_metrics_collection.html)**  
  Azure Monitor Agent collects monitoring data from Azure virtual machines and pushes it to Azure Monitor.
- **[Permissions Reference - Microsoft Azure](../admin/permissions-reference-azure.html)**
