---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "CT Apps - End User Devices component"
breadcrumb: []
source_path: "cost-transparency/configuration/enduserdevices.html"
images:
  - "resources/images/ct_images/6859_1.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - End User Devices component

The CT - Apps End User Devices component is part of Costing Standard
Applications and Services module. It is used to understand the TCO of the End User Devices including
PCs, Laptops, Smartphones, Tablets and other client compute equipment and to allocate those costs
used by the company's workforce.

Component Icon:

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6859_1.png)

The End User Devices component installs a new
data tables and recommended allocation strategies for determining end user device TCO and to
apportion end user device costs to the following typical services:

- End User Services - for end user devices used as Client Compute service offerings by the workforce
- Specific Business Services - for business specific needs such as distributed compute resources (e.g. kiosk) for a retail offering (e.g. ATM Machine)

## Supporting tables

When you install the CT Apps - End User Devices component, a new End User Devices group is
created with two tables: End User Devices (model table), End User Devices Master Data.

## Master data

For a description of the fields in the master data table, see the information on the CT Apps -
End User Devices component page in the product. To display the page:

1. Click the **Project** tab in the ribbon.
2. Click **Components**.
3. Click the **CT Apps - End User Devices** component.

## Upload the data

Upload your end user devices data. The required and recommended fields are listed below. All of
the fields can be mapped to the End User Devices Master Data table.

- Asset ID Number (recommended)
- Device Count (required)
- Device Type (required)

## Map the data

After uploading the communications data, map the table to the End User Devices Master Data
table.

After you map the data, there should be value allocated from IT Resource Towers and
Communications to End User Devices, and from End User Devices to Business Services in the Cost
model.
