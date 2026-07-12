---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
  - "Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning"
source_path: "SSVCLNQ/admin/azure-advanced-rightsizing.html"
images:
  - "03-media/apptio-cloudability-standard/vc_ss1.jpg"
  - "03-media/apptio-cloudability-standard/vc_ss2.jpg"
  - "03-media/apptio-cloudability-standard/vc_ss3.jpg"
  - "03-media/apptio-cloudability-standard/vc_ss4.jpg"
  - "03-media/apptio-cloudability-standard/azure_rightsizing7.jpg"
  - "03-media/apptio-cloudability-standard/azure_rightsizing8.jpg"
  - "03-media/apptio-cloudability-standard/azure_rightsizing9.jpg"
  - "03-media/apptio-cloudability-standard/azure_rightsizing11.jpg"
  - "03-media/apptio-cloudability-standard/azure_rightsizing12.jpg"
  - "03-media/apptio-cloudability-standard/details.jpg"
  - "03-media/apptio-cloudability-standard/azure-rightsizing-credentials.jpg"
  - "03-media/apptio-cloudability-standard/azure_rightsizing16.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning

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
