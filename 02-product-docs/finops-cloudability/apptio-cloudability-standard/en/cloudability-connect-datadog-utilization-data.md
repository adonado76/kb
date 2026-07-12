---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect Datadog - Utilization Data"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Datadog - Utilization Data"
source_path: "SSVCLNQ/admin/connect-datadog.html"
images:
  - "03-media/apptio-cloudability-standard/datadog-integration-readonly.jpg"
  - "03-media/apptio-cloudability-standard/vc_ss10.jpg"
  - "03-media/apptio-cloudability-standard/datadog-integration-azure.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect Datadog - Utilization Data

If you use Datadog to monitor your resources, you can take advantage of Cloudability 's Datadog integration to help you reduce wasted spend by optimizing your resource usage.

Cloudability fully supports Datadog multiple organizational accounts .

- AWS EC2
- Azure Compute
- GCP GCE

- European Union data residency (datadoghq.eu)
- Datadog multiple organizational accounts

Using an Application Performance Monitoring (APM) product like Datadog makes it easy to generate and collect the necessary resource utilization metrics (such as guest memory metrics, which can be difficult to instrument at scale) to get an accurate picture of how the resource is being utilized leading to an accurate rightsizing recommendation. Learn more about Datadog and its product offerings here .

- Improved recommendations: utilization data provided by Datadog offers higher precision, as metric sampling occurs at a higher frequency when compared to the native provider. As a result, we are able to leverage this increased precision to discover an additional 15-20% cost savings opportunities over the default platform metrics.
- Increased coverage: by completing the Datadog Azure integration you will benefit from easier and increased coverage of virtual machine resources, receiving rightsizing recommendations and corresponding cost savings opportunities.

Before you start

API and Application keys

- Datadog API key
- Application key

If you have multiple Datadog organizations, you need to create one API key and Application key per organization. Cloudability requires only a single API key and Application key per Datadog organizational account.'

- Administrator
- Standard
- Read-only

- Read-only keys prevent Cloudability from fetching metadata, such as key name, for the keys.
- Read-only keys prevent Cloudability from being able to perform de-dup. For example, in the case when a user adds multiple read-only keys from the same Datadog organizational account, we need only a single API and Application key per account, but we can't de-dup since read-only keys do not provide us access to the data necessary to perform that check. In other words, Cloudability does not know that these read-only credentials are from the same account.

If you add a read-only application key to your Cloudability credentials, metadata such as key name and owner are shown as Not available .

Steps for integration

We recommend to downgrade the Admin User to Read-Only User for the purposes of this integration, to follow the best practices of information security and privacy.

If you are already an Administrator and need to be the lead for this integration, invite yourself as a new user using a different email address than the one currently set as an Admin User and create the keys. Afterward, downgrade yourself to a Read-Only User.

Create new keys in Datadog

1. Invite a new member as an Admin User for the integration. See Datadog’s User Roles and Permission for more information.
1. Log in as the newly created Admin User.
1. Navigate to Integrations > APIs > New API key .
1. Create a new API key.
1. Go to the New application key section and create a new application key.

Add your Datadog keys to Cloudability

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > Datadog . The Add Datadog Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > Datadog . Select Add a Credential . The Add a Credential panel opens.
1. Select the Datadog tab.
1. Select Yes, I'm ready to confirm you have your Datadog keys.
1. Copy and paste the new API key and application key into the relevant field.
1. Input your API limit in Rate Limit . Note: This integration will require about 300 API requests per hour, as Cloudability needs to collect a month's data within 24 hours. 300 API requests per hour per organization is the default rate set on Datadog's side. If you use the Datadog API for other purposes, we highly recommend you contact Datadog Support to request an increase in the number of API requests you can make. In general, we recommend increasing it to between 600 and 900 API requests per hour per organization. This is a simple, free request to Datadog, and you can reference Cloudability in your request.

Cloudability lists all your Datadog credentials in the same page:

Cloudability integration with Datadog for Azure Compute

Once you have completed the integration steps above, complete the Datadog subscription integration for each subscription containing virtual machines. This procedure includes installing the Datadog Agent on each virtual machine.

Cloudability integration with Datadog for GCP GCE (Google Compute Engine)

For additional information on the setup and installation of Datadog on Google Cloud Platform, see https://docs.datadoghq.com/integrations/google_cloud_platform/#setup

How to confirm success

Within 24 hours after the Datadog Azure integration has been completed, you will see rightsizing recommendations informed by utilization metrics from Datadog. The Data Source column will now display Datadog if the recommendation was informed by utilization data from Datadog.
