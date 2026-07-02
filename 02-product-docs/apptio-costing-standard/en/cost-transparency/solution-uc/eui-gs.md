---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "End User Insights Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Solution Use Cases"
  - "End User"
source_path: "cost-transparency/solution-uc/eui-gs.html"
images:
  - "resources/images/ct_images/euigs.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# End User Insights Getting Started

The End User Devices component provides visibility into the cost of end user devices
such as PCs, laptops, smartphones, tablets, and other client computing equipment, and enables
allocation of those costs to the company’s workforce.

This is an independent solution that does not require configuration of the core cost model.
All required data is uploaded directly into the input tables as outlined in the configuration
guide.

## Components Install

**End User Devices**

The **End User Devices** component installs the End User Devices model, required master
and feed tables, allocation logic, and pre-built reports to analyze device inventory,
lifecycle, compliance, and estimated refresh costs.

**Note:** This component is available in templates **v110 and later**.

## Prerequisites

There are no prerequisites as the solution can bei installed and independently

## Common Sources of Data

End User Devices data is typically sourced from a combination of identity, workforce, and
asset systems. Active Directory or similar directory services provide device usage and login
activity, while HR or Labor systems supply employee, cost center, and organizational
attributes. Device inventory and asset management tools contribute hardware, ownership,
lifecycle, warranty, and refresh information for PCs, laptops, mobile devices, and other
endpoints.

## Datasets

The component installs the required datasets and master tables. Configuration requires
creating 3 input tables to ensure relevant details are uploaded and then map them to the
corresponding master tables.

- **Active Directory**
- **End User Devices**
- **Labor Data**

  Sample for Reference: Name of the tables can be customer specific

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/euigs.png)

For more details on the configuration steps, go [here.](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=configuration-configure-end-user-devices "(Opens in a new tab or window)")
