---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "CT Apps - Storage component"
breadcrumb: []
source_path: "configuration/storage.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Storage component

The Storage component is a foundational prerequisite component that is used by
the Storage Insights component. The Storage component does not provide new reports but is used to
create metrics that are exposed in the Storage Insights component.

Component
Icon:

![](../../resources/images/ct_images/6849_1.png)

## Supporting tables

When you install the CT Apps - Storage component, two new groups are created with two tables
each:

- Storage
- Storage (model table)
- Storage Master Data
- Storage Devices
- Storage Devices (model table)
- Storage Devices Master Data

The Storage Devices Master Data table includes information about the physical storage
devices.

The Storage Master Data table includes the LUNs (logical unit numbers) associated with the
physical storage devices.

## Master data

For a description of the fields in the master data table, see the information on the CT Storage
component page in the product. To display the page:

1. Click the Project tab in the ribbon.
2. Click Components.
3. Click the CT Apps - Storage component.

## Upload the data

Upload your data center data. The required and recommended fields are listed below. All of the
fields can be mapped to the Storage Master Data table or the Storage Devices Master Data table.

- Actual Units (required)
- Budgeted Units (recommended)
- Date Purchased (recommended)
- Environment (required)
- Location (required)
- Platform (required)
- Purpose (required)
- Server ID (required)
- Sourcing (required)
- Storage Device ID (required)
- Tier (required)
- Total Space (required)
- Type (required)

## Map the data

After uploading the storage data, map the table to the Storage Devices Master Data table.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
