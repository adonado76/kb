---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Vendor Insights Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Vendor"
source_path: "cost-transparency/it-financials/vi-getstar.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Vendor Insights Getting Started

Vendor Insights provides analytics and decision support across the vendor management
lifecycle, including vendor spend visibility, purchase order controls, contract analysis, and
ARC/RRC monitoring. Vendor Insights is delivered through modular components that can be
installed incrementally based on the level of insight required.

Before enabling Vendor Insights reports, ensure the required foundational components are
installed and that the necessary vendor, accounts payable, and related datasets are available
and mapped correctly.

## Prerequisites

- **CTF – Cost Source**
- Provides foundational financial actuals and budget data required for vendor spend
  analysis.
- **CTF – Vendor**
- Enables vendor master data and vendor-level attribution of spend.

Additional Vendor Insights components build on this foundation and introduce more advanced
reporting capabilities.

**Vendor Insights Components**

Vendor Insights components are installed incrementally, with each component enabling a
specific set of reports and analyses.

## Vendor Insights – Foundation

The **Vendor Insights Foundation** component provides core vendor spend visibility and
rationalization capabilities. It enables analysis of vendor distribution, spend trends, and
portfolio concentration.

Key capabilities enabled:

- Vendor Insights (Dashboard)
- Vendor Summary
- Vendor Detail
- Vendor spend by vendor type and cost pool
- Data quality analysis between vendor and accounts payable data

This component requires:

- Accounts Payable data (invoices and spend details)
- Vendor master data (vendor names, hierarchy, categorization)

## Vendor Insights – Purchase Orders (PO)

The **Vendor Insights PO** component extends vendor analysis into purchase order
visibility and controls.

Key capabilities enabled:

- PO Burndown
- Spend without POs
- Purchase Order Detail
- PO-to-AP relationship analysis

This component requires:

- Purchase Order data
- AP-to-PO mapping data

**Note:** The Foundation component must be fully installed and configured before
installing the PO component.

## Vendor Insights – Contracts

The **Vendor Insights Contracts** component enables contract-level analysis and renewal
planning.

Key capabilities enabled:

- Contract Summary
- Contract Expiration
- Contract Expiration Notification
- Contract to Applications
- Contract Detail

This component requires:

- Contract master data
- PO-to-Contract mapping
- Contracts-to-Applications mapping
- Application master data

**Note:** The PO component must be installed before enabling Contracts.

## Vendor Insights – ARC/RRC

The **ARC/RRC** component supports analysis of consumption-based vendor contracts with
additional resource charges and reduced resource credits.

Key capabilities enabled:

- ARC RRC Summary
- ARC RRC RU Reconcile
- Resource unit consumption and pricing analysis

This component is installed after Contracts and requires ARC/RRC-specific contract and
resource unit data.

## Common Sources of Data

Vendor Insights typically integrates data from financial, procurement, and contract
management systems. Common source applications include:

- **Accounts Payable / Financial Systems:** SAP ECC/AP, Oracle Financials,
  NetSuite
- **Procurement Systems:** SAP Ariba, Coupa, Oracle Procurement Cloud
- **Vendor & Contract Management:** ServiceNow Vendor Management, SAP ERP,
  Oracle

The scope and quality of source data determines the attributes available for reporting,
such as vendor names, categories, spend amounts, purchase orders, contracts, applications
supported, and ARC/RRC metrics.

## Master Datasets

Depending on the components installed, Vendor Insights uses the following master
datasets:

- **Vendor Master Data** – Vendor attributes, hierarchy, categorization
- **Accounts Payable Master Data** – Invoice-level spend and attribution
- **Purchase Orders Master Data** – PO values, status, and commitments
- **Contracts Master Data** – Contract terms, expiration, commitments
- **Contracts to Applications Master Data** – Mapping of contracts to supported
  applications
- **ARC/RRC Master Data** – Resource unit quantities, thresholds, and pricing

These datasets must be uploaded and mapped correctly to ensure accurate vendor reporting
and analysis across all Vendor Insights reports.
