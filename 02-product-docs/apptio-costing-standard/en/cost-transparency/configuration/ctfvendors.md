---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "CTF Vendors component: install and configure"
breadcrumb: []
source_path: "cost-transparency/configuration/ctfvendors.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF Vendors component: install and configure

To configure vendors, install the CTF-Vendors component and upload data from your
organization's vendor master data file. The CTF-Vendors component is not installed automatically
with the standard Costing Standard project. The data to populate the Vendor Master Data table in the
Costing Standard application typically comes from the vendor master data file in your organization's
financial application such as Oracle Financials or SAP ERP Financials.

## About the keys

The keys for the Vendor Master Data table are all pre-defined and should not be altered.

| Key | Based on | Logic |
| --- | --- | --- |
| Cost Source\_Vendor Key | Vendor ID  Cost Source Key  Metafield | Append the text CS\_Vendor with the Vendor ID field and the Cost Source Key Metafield. |
| Vendor\_ITRT Key | Vendor CSP KeyIT Resource TowerIT Resource Subtower | IF Vendor\_CSP Key = Vendor\_CSP\_null THEN Append the text Vendor\_ITRT with IT Resource Tower and IT Resource Sub-tower ELSE Set the text to Vendor\_ITRT\_null |
| Vendor\_CSP Key | Is CSP  Vendor Name | IF Is CSP = yes THEN Append the text Vendor\_CSP with the Vendor Name ELSE Set the text to Vendor\_CSP\_null |

## Install the component

The CTF - Vendors component is not installed with the standard Costing Standard project.

To install the CTF - Vendors component:

1. Open the Costing Standard project.
2. Click the **Project** tab.
3. Click **Components** in the Ribbon.
4. Click the **CTF - Vendors** component.
5. Click **Install**.

## Typical data sources

Vendor figures usually are pulled from a general ledger.

## Uploads

Typically, you upload a single vendor table that is appended to the Vendor Master Data table. The
data set must contain fields that can be mapped to the appropriate fields in the Vendor Master Data
table.

## Populate the master data set

There is one master data set associated with the CTF - Vendors component: Vendor Master Data

## Required and recommended fields

The required and recommended fields needed to light up the standard Vendor reports are listed
below.

- Is CSP (required)
- IT Resource Sub-Tower (required)
- IT Resource Tower (required)
- Vendor Function (required)
- Vendor ID (required)
- Vendor Manager (recommended)
- Vendor Name (required)
- Vendor Service (recommended)
- Vendor Type (required)

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
