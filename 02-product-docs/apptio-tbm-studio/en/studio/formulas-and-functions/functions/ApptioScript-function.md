---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Recurring Publish function"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Formulas and functions"
source_path: "studio/formulas-and-functions/functions/ApptioScript-function.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Recurring Publish function

**Applies to**: TBM Studio 12.11.22 and later

The **Recurring Publish** feature allows you to automate the publishing of editable table data
using an ApptioScript function. When you click the button, the system allows you to write
Apptioscript for scheduling recurring publish runs. After execution, the script publishes data from
the editable table to the associated transform table.

## Where to use

Use the syntax in the **Server Action** field of a button on a report.

## Syntax

`PublishNow("schedule2", "schedule4",autoPromoteToProd="true")`

## Parameters

Schedule 2 is a mandatory parameter, while the remaining parameters are optional

*Schedule 2*: Define when the recurring publish should run.

*autoPromoteToProd="true"* When set to `true`, the published changes are
promoted to **Production** If set to `false`, the changes remain in the
**Staging** environment.

## Example

`PublishNow("Weekday Evening Publish", autoPromoteToProd="true")`

This will publish every weekday evening and transfer data to associated transform table.
