---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "CT Apps - Services component"
breadcrumb: []
source_path: "configuration/services.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Services component

The CT Apps - Services component provides insight into IT spending on business services,
including month-to-Month changes in spend and performance against plan.

Applies to: Costing Standard on TBM Studio 12.0 and later

Component Icon

![](../../resources/images/ct_images/6848_1.png)

## Supporting tables

When you install the CT Apps - Services component, a new Business Service group is created with
three tables: Business Services (model table), All Business Services, All Business Services
Reference List.

The All Business Services Reference List table includes a list of service types (e.g.: Business
Application Services, End User Services, etc.) and the various service categories associated with
each service type. You should not modify this table.

## Required and recommended data

There is no master table for the CT Apps - Services component. However, the All Business Services
table serves a similar function.

The required and recommended fields are listed below. All of the fields can be mapped to the All
Business Services table.

- Description (recommended)
- Lifecycle Stage (recommended)
- Objective (recommended)
- Quantity (recommended)
- .PK (required)
- Allocation Type (recommended)
- Check for SAD (required)
- Service Category (recommended)
- Service Count (required)
- Service ID (required)
- Service Name (required)
- Service Offering (recommended)
- Service Owner (recommended)
- Service Type (recommended)
- Type (required)
- Unit of Measure (recommended)

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
