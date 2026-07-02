---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Vendor Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Vendor"
source_path: "cost-transparency/it-financials/vendor-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Vendor Getting Started

Use the Vendors capability to analyze IT vendor spend across the organization and
support vendor transparency, consolidation, and optimization decisions. Vendor reporting is
enabled by installing the **CTF – Vendors** component and loading vendor spend data into the
Costing Standard project.

Before using the Vendor reports, install the required components and ensure vendor data is
uploaded and mapped to the Vendor Master Data table.

## Components Install

- **CTF – Vendors** - The **CTF – Vendors** component enables vendor-level spend
  analysis within Costing Standard. It is not installed automatically and must be added
  explicitly to the project.

This component enables:

- Visibility into vendor spend across the organization
- Analysis of vendor concentration and fragmentation
- Vendor spend reporting across cost centers, projects, and IT resource towers

After installing this component, vendor data must be uploaded and mapped to the Vendor
Master Data table to populate Vendor reports.

**CTF- Vendors NX Reports (Additional Component)**

This component provides
predefined NX reports based on vendor data for cost analysis across vendors, categories, and time
periods.

Use this component when:

- You need standard vendor cost reports
- You want to compare actuals and budgets
- You require consistent vendor reporting

## Prerequisites

**CTF – Cost Source** - Provides the foundational cost data required to associate spend
with vendors.

**Common Sources of Data** - Vendor data is typically sourced from the general ledger or
vendor master data maintained in financial systems. These systems provide the vendor
identifiers and associated spend required for vendor-level reporting.

## Master Datasets

- **Vendor Master Data** - The Vendor Master Data table stores vendor identifiers and
  related attributes used for vendor-level analysis. Typically, a single vendor data table
  is uploaded and appended to this master data table.

The uploaded dataset must include fields that can be mapped to the Vendor Master Data
structure to enable accurate reporting.
