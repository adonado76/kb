---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Connect Pagerduty"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Pagerduty"
source_path: "SSVCLNQ/admin/connect-pagerduty.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Connect Pagerduty

The following information will help you connect your Pagerduty Services to Cloudability.

Steps for integration

1. From the Configuration menu, select Services .
1. If you are creating a new service for your integration, on your Services page, select Add New Service .
1. If you are adding your integration to an existing service, on your Services page, select the name of the service to which you want to add the integration. Then, select the Integrations tab and select New Integration .
1. From the Integration Type menu, select Cloudability and complete the Integration Name field.
1. If you are creating a new service for your integration, in General Settings , enter a name for your new service in the Name field. Then, in Incident Settings , specify the Escalation Policy , Notification Urgency , and Incident Behavior for your new service.
1. Select Add Service , or Add Integration to save your new integration. You will be redirected to the Integrations page for your service.
1. Copy the Integration Key for your new integration. This will be used in the following procedure.

1. In Cloudability , navigate to Settings > Vendor Credentials > Add Datasource > PagerDuty . The Add PagerDuty Account panel opens. Or In Cloudability , navigate to Settings > Vendor Credentials > PagerDuty . Select Add a new service . The Add a new service panel opens
1. Enter the details in the Integration Name and Integration Key fields.

1. Navigate to the Anomaly Detection page.
1. Select ALERTS and configure your PagerDuty alert settings.

Troubleshooting

What can Cloudability do with my integration key in Pagerduty?

We integrate them with v2 of Pagerduty's Events API. The Events API v2 is a highly reliable, highly available asynchronous API that ingests events from monitoring tools. Events sent to this API are routed to a Pagerduty service and processed. They may result in a new alert or incident being created, or an existing one being updated or resolved. Previously, the Events API was also used to integrate Pagerduty with ticketing systems and various other software tools. Today, we recommend using the synchronous Incidents API to integrate ticketing systems or other systems of record with Pagerduty

Therefore, integration keys only allow sending alerts to a service.
