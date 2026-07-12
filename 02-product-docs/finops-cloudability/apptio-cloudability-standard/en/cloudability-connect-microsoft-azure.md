---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect Microsoft Azure"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
source_path: "SSVCLNQ/admin/azure-cm-setup.html"
images:
  - "03-media/apptio-cloudability-standard/azure-turbonomic-integration.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect Microsoft Azure

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
