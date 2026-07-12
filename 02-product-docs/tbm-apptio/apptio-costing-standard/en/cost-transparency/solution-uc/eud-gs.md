---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "End User Devices Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Solution Use Cases"
  - "End User"
source_path: "cost-transparency/solution-uc/eud-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# End User Devices Getting Started

The End User Devices component enables organizations to understand the total cost of
ownership of workforce devices such as PCs, laptops, smartphones, tablets, and other client
compute equipment. This component supports accurate allocation of end user device costs to
consuming services and business units.

## Components Install

**CT Apps – End User Devices**

The CT Apps – End User Devices component installs the foundational data structures,
datasets, and recommended allocation strategies required to calculate End User Device TCO.
It supports allocation of device costs to end user services and specific business services
where distributed compute resources are used.

## Prerequisite

You must install the following components before installing the End User Devices
component:

CTF- Cost Source

CTF- IT Towers

## Common Sources of Data

End user device cost and inventory data is typically sourced from general ledger systems,
asset management platforms, endpoint management tools, and procurement systems. These
sources determine the level of detail available for device cost, ownership, and allocation
analysis.

## Datasets

When you install the CT Apps – End User Devices component, a new End User Devices group is
created with the following tables:

• End User Devices (model table)

• End User Devices Master Data

After uploading your end user device data, map the dataset to the End User Devices Master
Data table. Once mapped, costs flow from IT Resource Towers and Communications to End User
Devices, and from End User Devices to consuming business services within the cost model.
