---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "CT Apps - Data Centers component"
breadcrumb: []
source_path: "configuration/datacenters.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CT Apps - Data Centers component

The Data Centers component is a foundational prerequisite component that is
used by the Data Centers Optimization component. The Data Centers component does not provide
reports. It provides metrics that are exposed in the reports of the Data Center Optimization
component.

Applies to: Costing Standard on TBM Studio 12.0 and later

Component
Icon:

![](../../resources/images/ct_images/6833_1.png)

## Supporting tables

When you install the CT Apps - Data Centers component, a new Data Center group is created with
two tables: Data Centers (model table), Data Centers Master Data.

## Master data

For a description of the fields in the master data table, see the information on the CT Data
Centers component page in the product. To display the page:

1. Click the Project tab in the ribbon.
2. Click Components.
3. Click the CT Apps - Data Centers component.

## Upload the data

Upload your data center data. The required and recommended fields are listed below. All of the
fields can be mapped to the Data Centers Master Data table.

- Certification Level (required)
- Data Center ID (required)
- Data Center Power Capacity (required)
- Data Center Power Usage (required)
- Data Center RU capacity (required)
- Data Center RU usage (required)
- Data Center Square Footage (required)
- Location (required)
- Manager (recommended)
- Name (required)
- Purpose (required)
- Region (recommended)
- Service Provider (recommended)
- Tier (required)

## Map the data

1. After uploading the storage data, map the table to the Storage Devices Master Data table and the
   Storage Master Data table.
2. On the model diagram, if you follow the Physical Server allocation by clicking the right arrow
   on the Physical Server object, you will be redirected to the Single Model view of Physical
   Servers.
3. Refresh the document by clicking Update Document in the Ribbon. Because there are now costs
   associated to all servers based on Location from Data Centers, you can see value flowing to
   Hypervisors.
4. To allocate the newly allocated Hypervisor costs to Servers, configure the Hypervisor to Server
   allocation using the settings shown in the following example.

   ![](../../resources/images/ct_images/6833_2.png)

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
