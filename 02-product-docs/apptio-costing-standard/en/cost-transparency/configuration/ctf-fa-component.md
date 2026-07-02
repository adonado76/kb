---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "CTF - Fixed Asset component: install and configure"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-fa-component.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Fixed Asset component: install and configure

Use the CTF - Fixed Asset component to gain insights into your depreciation costs and
empower your decisions about asset management. The Fixed Asset Master Data table defines the data
required to populate the cost and budget related reports. To populate the data set, you must upload
fixed asset cost figures and map them to the Fixed Asset Master Data table.

Applies to: Costing Standard on TBM Studio 12.4 and later

## Uses

Use the CTF - Fixed Assets component reports to do the following:

- Manage depreciation costs
- Identify resource allocation
- Align asset management with business objectives
- Align asset management to strategy
- Confirm write-offs resulting from budget changes

## Install the component

The CTF - Fixed Assets component is not installed with the standard Costing Standard project.

To install the CTF - Fixed Assets component:

1. Open the Costing Standard project.
2. On the Project tab, click **Components**.
3. Click **Install**.

## Typical data sources

Fixed asset figures usually are pulled from an asset management or CMDB (Configuration Management
Data Base) application such as BMC Asset Mgmt, BMC Atrium CMDB,HP Univ Config Mgmt, Sage,
AssetWorks, SAP Enterprise Asset Mgmt, CA Unicenter, SAP, Lawson, Oracle, or PeopleSoft.

The applications usually include a fixed asset registry. The fixed asset registry tracks assets
such as machines, office equipment, buildings, etc for the purpose of production of goods or
services. Often tracked in the Fixed Asset registry is the life in months of the asset, the purchase
date, purchase amount, and monthly depreciation.

## One upload

Typically you upload a single fixed asset data set that is appended and mapped to the Fixed Asset
Master Data table. The data set must contain fields that can be mapped to the appropriate fields in
the Fixed Asset Master Data table.

## Master data

For a description of the fields in the master data table, see the information on the CTF - Fixed
Assets component page in the product. To display the page:

1. Click the **Project** tab.
2. Click **Components**.
3. Click the **CTF - Fixed Assets** component.

## Required and recommended fields

The required and recommended fields needed to light up the standard Costing Standard fixed asset
reports are listed below.

- Acquisition Date (required)
- Age (required)
- Asset Count (required)
- Asset Number (required)
- Asset Type (recommended)
- Category (recommended)
- Class (required)
- Cost Center (recommended)
- Depreciation Amount (required)
- Description (required)
- Fixed Asset Depreciation LIM (required)
- Fixed Asset Initial Cost (required)
- Fixed Asset Ledger ID (required)
- In Service (required)
- In Service Date (required)
- IT Resource Sub-Tower (required)
- IT Resource Tower (required)
- Location (required)
- Object Identifier (required)
- Vendor (required)

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
