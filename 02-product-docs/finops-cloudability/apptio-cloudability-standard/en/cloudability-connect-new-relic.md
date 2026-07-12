---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect New Relic"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect New Relic"
source_path: "SSVCLNQ/admin/new-relic-integration.html"
images:
  - "03-media/apptio-cloudability-standard/cloudability-newrelic-account-insights-keys.jpg"
  - "03-media/apptio-cloudability-standard/cloudability-newrelic-insights-key-details.jpg"
  - "03-media/apptio-cloudability-standard/vc_ss9.jpg"
  - "03-media/apptio-cloudability-standard/cloudability-newrelic-credentails-list.jpg"
  - "03-media/apptio-cloudability-standard/cloudability-newrelic-rightsizing-list.jpg"
  - "03-media/apptio-cloudability-standard/cloudability-newrelic-datasource-filter.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect New Relic

New Relic is a popular application performance management (APM) platform. This integration enables Apptio Cloudability customers to leverage New Relic as their preferred utilization data provider, resulting in improved rightsizing recommendations for Amazon EC2, GCP GCE, and Azure Compute virtual machines. Support for multiple accounts is also included with this integration.

Compared to the native utilization data providers, New Relic provides more precise platform performance metrics (CPU, Network, Disk), and access to guest OS memory metrics. With this higher precision data source, the rightsizing engine surfaces more informed recommendations, providing up to an additional 15 percent savings, on top of the existing savings opportunities, further reducing your cloud spend.

Before you start

The following steps are required to enable New Relic integration with Cloudability successfully:

- Virtual Machines -Each virtual machine resource needs to have the New Relic infrastructure agent installed. The instructions vary based on the operating system; currently, Linux and Windows are supported.

- Linux
- Windows

- New Relic Accounts

For each New Relic account, you must provide an Account Id and Insights Query Key. Cloudability uses these read-only credentials to retrieve the performance metrics from your associated virtual machine resources via the Insights API .

- Obtaining Account Credentials
- Entering New Relic Credentials

Steps for integration

- Enabling Azure integration

- Enable Azure Integration

- Obtaining Account Credentials

To manage or obtain your New Relic account credentials:

1. Go to insights.newrelic.com and switch to the desired account
1. From the left menu, click Manage data
1. From the top menu, click API Keys
1. To create a New Key, click Query Keys [+]
1. To view or edit an existing key, click the appropriate Edit button

The below screen allows the customer to create or edit the Notes associated with an Insights Query key.

From this screen, the customer can obtain the following:

- Account Id (a seven or greater digit number)
- Insights Query Key (key begins with NRIQ-)

We suggest you label this query key as `cloudability-integration` for tracking and auditing purposes.

Entering New Relic Credentials

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > New Relic . The Add New Relic Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > New Relic . Select Add a Credential . The Add a Credential panel opens.
1. Enter the New Relic credentials.
1. Select Save .

How to confirm success

- To modify a credential, select Edit
- To delete a credential, select Delete
- To validate a credential, select Refresh

Using Rightsizing

After the setup is complete, the customer can view the rightsizing recommendations from the Data Source column.

Filter or Sort by Data Source

- To sort, click on the Data Source column heading and the list will be sorted by this value.
- To filter, either click on the Data Source value to limit the recommendations to this value, or click the Filters menu, then select Measure = Data Source , Operator = equals , and Value = New Relic .
- To clear the filter, click the Filter menu, and then delete the condition by clicking the 'x' icon.

GCP Integration

For additional information on connecting Google Cloud Platform services to New Relic, see https://docs.newrelic.com/docs/infrastructure/google-cloud-platform-integrations/get-started/connect-google-cloud-platform-services-new-relic/ .
