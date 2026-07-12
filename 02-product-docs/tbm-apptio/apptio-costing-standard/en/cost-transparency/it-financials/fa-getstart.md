---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Fixed Asset Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Fixed Assets"
source_path: "cost-transparency/it-financials/fa-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Fixed Asset Getting Started

**Getting Started**

Use the Fixed Assets capability to track capitalized IT assets, monitor depreciation, and
support informed asset management decisions. The **CTF – Fixed Assets**component enables
reporting on depreciation costs and remaining asset value, helping IT Finance and Service
Owners understand asset lifecycle and financial impact.

Before using Fixed Assets reports, install the required component and load fixed asset data
into the master data table.

## Components Install

**CTF- Fixed Assets**

The CTF- Fixed Assets component provides the structure required to analyze fixed asset
cost, depreciation, and remaining value over time.

**Prerequisites**

- CTF- Cost Source

After installing the component, you must upload fixed asset cost data and map it to the
**Fixed Asset Master Data** table to populate depreciation and asset-related reports.

## Common Sources of Data

Fixed asset data is typically sourced from enterprise asset management systems or
configuration management databases (CMDBs) that maintain a fixed asset registry. These systems
track assets used to deliver goods or services and usually include details such as purchase
date, purchase cost, asset life in months, and depreciation values.

Commonly used sources include **SAP Enterprise Asset Management**, **Oracle**,
**PeopleSoft**, **BMC Asset Management / BMC Atrium CMDB**, **ServiceNow Asset
Management**, and **Workday Financial Management**

**Master Datasets**

The Fixed Asset Master Data table defines the data required for fixed asset cost and
depreciation reporting. To populate this table, upload a fixed asset data set containing cost
and depreciation information and map it to the appropriate fields in the master data table.

Typically, you upload a **single fixed asset data set**, which is appended to and mapped
into the Fixed Asset Master Data table. The data set must include fields that align with the
required master data structure to support accurate depreciation and lifecycle reporting.
