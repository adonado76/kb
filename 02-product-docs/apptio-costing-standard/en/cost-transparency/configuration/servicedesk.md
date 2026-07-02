---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "CT Apps - Service Desk component"
breadcrumb: []
source_path: "cost-transparency/configuration/servicedesk.html"
images:
  - "resources/images/ct_images/6868_1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Service Desk component

The Service Desk component is a prerequisite component that is used by the Service Desk
Insights component. The Service Desk component does not provide new reports but is used to create
metrics that are exposed in the Service Desk Insights component.

Applies to: Costing Standard on TBM Studio 12.0 and later

Component Icon

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6868_1.png)

## Supporting tables

When you install the CT Apps - Service Desk component, a new Service Desk group is created with
two tables: Tickets (model table), Tickets Master Data.

## Master data

For a description of the fields in the master data table, see the information on the CT Apps -
Service Desk component page in the product. To display the page:

1. Click the **Project** tab in the ribbon.
2. Click **Components**.
3. Click the **CT Apps - Service Desk** component.

## Upload the data

Upload your service desk data. The required and recommended fields are listed below. All of the
fields can be mapped to the Tickets Master Data table.

- Application ID (recommended)
- Assigned To (recommended)
- Category (required)
- Close Time (required)
- Closed (recommended)
- Description (recommended)
- Duration (recommended)
- Impact (recommended)
- Location (recommended)
- Open Time (required)
- Priority (required)
- Priority Weight (required)
- Reported By (recommended)
- Service (recommended)
- Severity (recommended)
- Status (required)
- Ticket ID (required)
- Type (required)
- Weighting (required)

## Map the data

After uploading the service desk data, map the table to the Service Desk Master Data table.

After you map the data, there should be value allocated from IT Resource Towers to Tickets in the
Cost model.

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
