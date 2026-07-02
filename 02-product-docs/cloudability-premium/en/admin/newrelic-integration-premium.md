---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Connect New Relic"
breadcrumb:
  - "Cloudability Premium"
  - "Getting data into Cloudability"
source_path: "admin/newrelic-integration-premium.html"
images:
  - "images/cloudability-newrelic-account-insights-keys.jpg"
  - "images/cloudability-newrelic-credentails-list.jpg"
  - "images/cloudability-newrelic-datasource-filter.jpg"
  - "images/cloudability-newrelic-insights-key-details.jpg"
  - "images/cloudability-newrelic-rightsizing-list.jpg"
  - "images/vc_ss9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Connect New Relic

New Relic is a popular application performance management (APM) platform.  This
integration enables Apptio Cloudability customers to leverage New Relic as
their preferred utilization data provider, resulting in improved rightsizing recommendations for
Amazon EC2, GCP GCE, and Azure Compute virtual machines. Support for  [multiple accounts](https://docs.newrelic.com/docs/accounts/install-new-relic/account-setup/manage-apps-or-users-sub-accounts "(Opens in a new tab or window)")  is also included with this integration.

Compared to the native utilization data providers, New Relic provides more precise platform performance metrics (CPU, Network, Disk), and access to guest OS memory metrics. With this higher precision data source, the rightsizing engine surfaces more informed recommendations, providing up to an additional 15 percent savings, on top of the existing savings opportunities, further reducing your cloud spend.

Before you start

The following steps are required to enable New Relic integration with
Cloudability
successfully:

- **Virtual Machines**

Each virtual machine resource needs to have the New Relic infrastructure agent installed. The
instructions vary based on the operating system; currently, Linux and Windows are supported.

[Linux](https://docs.newrelic.com/docs/infrastructure/install-infrastructure-agent/linux-installation/install-infrastructure-agent-linux-using-package-manager "(Opens in a new tab or window)")

[Windows](https://docs.newrelic.com/docs/infrastructure/install-infrastructure-agent/windows-installation/install-infrastructure-agent-windows-server-using-msi-installer "(Opens in a new tab or window)")

- New Relic Accounts

For each New Relic account, you must provide an Account Id and Insights Query Key.
Cloudability
uses these read-only credentials to retrieve the performance metrics from your associated virtual machine resources via the
[Insights API](https://docs.newrelic.com/docs/insights/insights-api/get-data/query-insights-event-data-api "(Opens in a new tab or window)")
.

See below for

[Obtaining Account Credentials](#obtainin "(Opens in a new tab or window)")

[Entering New Relic Credentials](#entering "(Opens in a new tab or window)")

Steps for integration

- Enabling Azure integration

In addition to the New Relic agent, Azure integrations are also required for Azure Compute virtual machines. It provides necessary resource-level data like subscription and tenant id to obtain unambiguous resource ids.

[Enable Azure Integration](https://docs.newrelic.com/docs/integrations/microsoft-azure-integrations/getting-started/activate-azure-integrations "(Opens in a new tab or window)")

- **Obtaining Account Credentials**

To manage or obtain your New Relic account credentials:

1. Go to
   [insights.newrelic.com](https://docs.newrelic.com/docs/integrations/microsoft-azure-integrations/getting-started/activate-azure-integrations "(Opens in a new tab or window)")
   and switch to the desired account
2. From the left menu, click **Manage data**
3. From the top menu, click **API Keys**
4. To create a New Key, click **Query Keys [+]**
5. To view or edit an existing key, click the appropriate **Edit** button ![api keys screenshot](../../../../03-media/cloudability-premium/images/cloudability-newrelic-account-insights-keys.jpg)

The below screen allows the customer to create or edit the Notes associated with an Insights Query key.

From this screen, the customer can obtain the following:

- Account Id (a seven or greater digit number)
- Insights Query Key (key begins with NRIQ-)

  Note: We suggest you label this query key as
  `cloudability-integration` for tracking and auditing purposes.

  ![query key screenshot](../../../../03-media/cloudability-premium/images/cloudability-newrelic-insights-key-details.jpg)

Entering New Relic Credentials

To integrate the new relic credentials into
Cloudability
:

1. In Cloudability , navigate to  Settings  >  Vendor
   Credentials  >  Add Datasource  >  New Relic
    . The  Add New Relic Account  panel opens.

   Or

   In
   Cloudability , navigate to  Settings  >  Vendor Credentials
    >  New Relic  . Select  Add a Credential
    . The  Add a Credential  panel opens.
2. Enter the  New Relic  credentials.
3. Select  Save .![newrelic list screenshot](../../../../03-media/cloudability-premium/images/vc_ss9.jpg)

How to confirm success

After the credentials are validated, the customer can change, delete, or refresh the credential.

- To modify a credential, select  Edit
- To delete a credential, select  Delete
- To validate a credential, select  Refresh![reresh newrelic screenshot](../../../../03-media/cloudability-premium/images/cloudability-newrelic-credentails-list.jpg)

Using Rightsizing

After the setup is complete, the customer can view the rightsizing recommendations from the
 Data Source  column. ![newrelic rightsizing screenshot](../../../../03-media/cloudability-premium/images/cloudability-newrelic-rightsizing-list.jpg)

Filter or Sort by Data Source

The customer can filter or sort the list of recommendations by the utilization data source provider.

- To sort, click on the **Data Source** column heading and the list will be sorted by this
  value.
- To filter, either click on the  Data Source  value to limit the recommendations to this
  value, or click the  Filters  menu, then select  **Measure = Data Source** , **Operator
  = equals** , and **Value = New Relic** .
- To clear the filter, click the **Filter** menu, and then delete the condition by clicking
  the 'x' icon.![filter newrelic screenshot](../../../../03-media/cloudability-premium/images/cloudability-newrelic-datasource-filter.jpg)

GCP Integration

For additional information on connecting Google Cloud Platform services to New Relic, see
[https://docs.newrelic.com/docs/infrastructure/google-cloud-platform-integrations/get-started/connect-google-cloud-platform-services-new-relic/](https://docs.newrelic.com/docs/infrastructure/google-cloud-platform-integrations/get-started/connect-google-cloud-platform-services-new-relic/ "(Opens in a new tab or window)")

Upgrading for existing Cloudability customers to Cloudability Premium

Upon upgrading to Cloudability Premium , the  Verification Status  for
each New Relic account in the listing page will not change with this release. However, your
Cloudability admin needs to edit each account following the steps enabling Cloudability share these
accounts with Turbonomic .

1. Click
   Edit
   in the New Relic account.
2. Input an additional field value for
   User Key
   and click
   Save
   .

Post validation and verification,
Cloudability
shares the account with
Turbonomic
.
