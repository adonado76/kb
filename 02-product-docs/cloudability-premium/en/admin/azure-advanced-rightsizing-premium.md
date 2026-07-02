---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
source_path: "admin/azure-advanced-rightsizing-premium.html"
images:
  - "images/azure-cldy-turbo-integration.jpg"
  - "images/azure-premium-1.jpg"
  - "images/azure-rightsizing-credentials.jpg"
  - "images/azure_rightsizing11.jpg"
  - "images/azure_rightsizing12.jpg"
  - "images/azure_rightsizing16.jpg"
  - "images/azure_rightsizing7.jpg"
  - "images/azure_rightsizing8.jpg"
  - "images/azure_rightsizing9.jpg"
  - "images/details.jpg"
  - "images/regenerate_11_35_55_am_png.jpg"
  - "images/vc_ss1.jpg"
  - "images/vc_ss2.jpg"
  - "images/vc_ss4.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Set up Advanced Credentials, Azure Rightsizing and Reserved Instance Planning

Azure Subscription level credentialing unlocks the following features within Cloudability :

- Apply resource group tags to resources within the resource groups

  Learn about  [Tag mapping](tag-data.html)
- Optimization - through Rightsizing, and Reserved Instances (RIs)

  Learn about  [Get
  recommendations for scaling your cloud resources with Rightsizing](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

  Learn about  [The Reservation Portfolio](../product/reservation-portfolio.html)

Currently, our platform uses a custom role called “CloudabilitySubscriptionDataReader” on
Subscriptions with the below mentioned permissions in order to fetch the necessary data:

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

We use the OAuth 2.0 Authorization Grant Flow to register our application and create a service
principal within the Azure tenant. You can read more about this process here: [https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals](https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals "(Opens in a new tab or window)")

Before you begin

You must meet the minimum requirements for successful credentialing.

- You are a Cloudability Administrator. The Cloudability Administrator role gives you access to
  the Vendor Credentials page where you can manage your credentials.

  Learn about  [Manage Vendor Credentials](manage-vendor-credentials.html)
- You have one of the following Azure Active Directory roles in your organization:
  - Global Administrator
  - Application Developer
  - Cloud Application Administrator

  This is necessary for the OAuth 2.0 Authorization Grant Flow. See [https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals](https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals "(Opens in a new tab or window)")

  Your Azure Active Directory (AD) role is used to register our enterprise app within
  your Azure AD tenant, and create the Service Principal.
- You are an Owner (or higher) on the Subscription you are credentialing. This is necessary for
  the OAuth 2.0 Authorization Grant Flow. See [https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals](https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals "(Opens in a new tab or window)") . You need to be at least an Owner on the Subscription so that permissions can be attached
  to the Service Principal through IAM.

Note: Ensure you have the billing:EnrollmentReader permission on your billing account.

Enable Custom read-only role on a Subscription

The following steps assume that you have already added an Azure EA to Cloudability 's Vendor
Credentials page. Also, you have one or more Subscriptions listed on that page for which you would
like to provide us access.

Learn about  [Set up Cost Management for new Cloudability Azure
Enrollment Agreement (EA) customers](azure-cm-ea.html)

1. In Cloudability , edit the subscription. Select the Edit icon for the Subscription for which
   you would like to provide Cloudability access. ![adding azure credential screenshot](../../../../03-media/cloudability-premium/images/vc_ss1.jpg)
2. Select the Generate Link button to generate a URL for each selected Subscription that you will
   then use to complete the OAuth 2.0 Authorization Grant Flow for each of those Subscriptions.
   1. Select Select Subscriptions.

      ![select credential screenshot](../../../../03-media/cloudability-premium/images/vc_ss2.jpg)
   2. Choose Advanced Rightsizing as  Read Only  vs  Automate
      Actions.
   3. Select the Subscription(s) for which to generate link(s).

      ![edit credential screenshot](../../../../03-media/cloudability-premium/images/azure-premium-1.jpg)
   4. elect Ok to complete your selections.
   5. Select Generate Links. A link is generated for each Subscription that you
      selected.
3. Select each link to complete registering our application and creating a service principal.
4. Complete the OAuth 2.0 flow triggered from the link.

   ![service principal screenshot](../../../../03-media/cloudability-premium/images/vc_ss4.jpg)
5. Accept the CloudabilityUtilizationDataCollector to complete the consent process.

   ![cloudabilityutilizationdatacollector screenshot](../../../../03-media/cloudability-premium/images/azure_rightsizing7.jpg)
6. Verify successful consent in the Azure portal:
   - Active Directory. You can verify that the application has been successfully consented to by
     checking the Enterprise applications section in your Azure Active Directory.

     ![active directory screenshot](../../../../03-media/cloudability-premium/images/azure_rightsizing8.jpg)
7. Subscription IAM. You can check whether the service principal is a assigned the custom role
   ‘CloudabilitySubscriptionDataReader’ on the subscription. ![subscriptiondatareader screenshot](../../../../03-media/cloudability-premium/images/azure_rightsizing9.jpg)

Confirm that you have successfully credentialed your subscription

Return to the Vendor Credentials page in Cloudability to verify credentials.

**Verify Credentials**
**via Bulk Actions**

In order to Verify multiple accounts quickly, click on Bulk Actions
button. This screen displays all the accounts except the ones with Credentials Needed status
(X).

1. Select the accounts which are needed to be verified.
2. Click on **Review Selection**
3. Click on **Verify.**

This would trigger the bulk verify process and the bulk actions button would be disabled
until the process completes.

Once completed, the accounts will move to either a Verified
Credentialed status or Invalid Credential status (because of errors).

Note: In case the number of
accounts is huge this might take a few minutes.

You may see a yellow or green check box, in the Advanced Features column, for the Subscription.

- A green check box for a Subscription indicates that Cloudability has,
  - a custom read-only role on the Subscription (through our service principal)
- A yellow check box implies that Cloudability has an incomplete credential, for example the
  credential process could have started (i.e., we have a record in our database) but there are no
  permissions attached to that credential.
- A red status color for the credential implies that there's an error with the credential.

Note: We can now unlock all Advanced Features through our Service Principal (this requires the
service principal to have the CloudabilitySubscriptionDataReader role on Subscriptions). The
permissions box will show as a yellow checkbox but this is ok.

1. Re-verify the credential by clicking on the circular arrow. ![reverify credential screenshot](../../../../03-media/cloudability-premium/images/azure_rightsizing11.jpg)

   A check mark is displayed briefly upon successful verification.

   ![succesful credential screenshot](../../../../03-media/cloudability-premium/images/azure_rightsizing12.jpg)

   You may need to refresh the browser to fetch new changes.
2. Select ![image details icon](../../../../03-media/cloudability-premium/images/details.jpg) to view the updated permissions.

   ![azure rightsizing screenshot](../../../../03-media/cloudability-premium/images/azure-rightsizing-credentials.jpg)s
3. Check whether you have the CloudabilitySubscriptionDataReader role on the subscription. This
   role on the subscription is identified by these 11 permissions shown in green tick marks. ![subsciption data reader screenshot](../../../../03-media/cloudability-premium/images/azure_rightsizing16.jpg)

Note: Some permissions are green and some are red. As long as we have the 11 permissions shown in
green above, Advanced Features are unlocked for that Subscription.

Additional permission is
required for Azure EA accounts.

Enrollment Reader permission will be added to Apptio
Cloudability to access Azure SQL RI planner data (including Azure Compute, SQL, Cosmos DB, and
Savings Plans)

Click here to  [Set up Azure Memory Metrics Collection](azure-advanced-metrics.html)

Upgrading existing Cloudability customers to Cloudability Premium

Upon upgrading to Cloudability Premium , the Billing Reports and Advanced Reports status for
each Azure account in the listing page automatically changes to error status. . Hence, Cloudability
admin needs to edit each account following the steps below which will set the right account status
in Cloudability for Azure data ingestion as well as enable Cloudability share these accounts with
Turbonomic .

1. In Cloudability , navigate to  Settings  >  Vendor
   Credentials  >  Azure  .
2. Hover your cursor over the icon of the payer or project for which you want to update
   credentials.
3. Select the ![edit icon](../../../../03-media/cloudability-premium/images/regenerate_11_35_55_am_png.jpg) icon to open Edit a Credential.
4. Choose Advanced Rightsizing as Read only vs Automate actions:
5. Generate setup script.
6. Update the permissions by executing the script.
7. Re-verify the account.

There are additional Turbonomic permissions that gets added to basic (Billing Data), advanced
(Utilization Data) and Optimize Resources (execute actions) which are documented in the help center
documents. Once your account is verified, the list of permissions can be viewed by choosing the
 Details  option on each Azure account listed under Cloudability. ![azure turbo credential screenshot](../../../../03-media/cloudability-premium/images/azure-cldy-turbo-integration.jpg)

In case the existing customers do not add the new permissions then

- There would be no change in Vendor credentials UI.
- The Automate actions will be shown as Off on the subscriptions.
- In the Details tab, all Turbonomic permissions appear with a RED x mark.

Once the new permissions are enabled on subscriptions with Readonly selection

- The Automate actions will still be shown as Off.
- In the Details tab, Turbonomic permissions for Cost, billing and billing execution will appear
  with a Green tick mark.

Once the new permissions are enabled with Automate actions and account(s) is verified

- The Automate actions will be marked as On.
- In the Details tab, all Turbonomic permissions appear with a Green tick mark.

Note: The Automate Actions ON/ OFF is displayed on the Vendor Credentials UI based on the selection
in the Toggle and download of the template.

**Parent topic:** [Connect Microsoft Azure](../admin/azure-cm-setup-premium.html)
