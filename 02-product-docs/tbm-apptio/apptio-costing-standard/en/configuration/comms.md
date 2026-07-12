---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "CT Apps - Communications component"
breadcrumb: []
source_path: "configuration/comms.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Communications component

The CT Apps - Communications component is part of Costing Standard Applications and
Services module. It is used to allocate Communication infrastructure costs including circuits and
usage to the consumers of the communication resource.

Applies to: Costing Standard on TBM Studio 12.0 and later

Component Icon

![](../../resources/images/ct_images/6878_1.png)

## Supporting tables

When you install the CT Apps - Communications component, a new Communications group is created
with two tables: Communication (model table), Communications Master Data.

## Master data

For a description of the fields in the master data table, see the information on the CT Apps -
Communications component page in the product. To display the page:

1. Click the Project tab in the ribbon.
2. Click Components.
3. Click the CT Apps - Communications component.

## Upload the data

Upload your communications data. The required and recommended fields are listed below. All of the
fields can be mapped to the Communications Master Data table.

- Account (recommended)
- Amount (required)
- Circuit ID (recommended)
- Location (recommended)
- Location Type (required)
- Object Identifier (required)
- Offering (recommended)
- Product (recommended)
- Service Provider (recommended)
- Type (required)

## Map the data

After uploading the communications data, map the table to the Communications Master Data
table.

After you map the data, there should be value allocated from IT Resource Towers to
Communications, and from Communications to Servers and Business Services in the Cost model.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
