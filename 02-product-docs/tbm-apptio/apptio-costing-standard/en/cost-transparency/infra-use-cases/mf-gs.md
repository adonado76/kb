---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Mainframe Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Mainframe"
source_path: "cost-transparency/infra-use-cases/mf-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Mainframe Getting Started

Use the Mainframe TCO components to load and manage the mainframe cost and consumption
data required for comprehensive reporting. The solution requires integration with IBM
IntelliMagic Vision for accurate usage data and connection to your General Ledger for complete
cost information.

Install and configure the Mainframe TCO components before loading your mainframe cost,
consumption, and allocation datasets. After installation, upload your data and map it to the
appropriate master data tables to enable reporting.

## Components Install

**CT Apps- Mainframes**

The Mainframes component is part of Cost Transparency Applications and Services module. It
is used to understand the TCO of the Mainframes and to allocate the Mainframe costs to the
Applications object.

**BI- Mainframe Insights**

The BI-Mainframe Insights component provides enhanced visibility into Mainframe Total Cost
of Ownership(TCO) and utilization, including a detailed analysis of unit costs and usage
measured in Million Services Units (MSUs) , with breakdowns across GCP MSUs and zIIP MSUs.

**Note:** This component is available in templates **v120 and later**.

**BI- Mainframe Insights NX Reports (Additional Component)**

This component
provides predefined NX reports based on mainframe data for analysis across applications, usage, and
time periods.

Use this component when:

- You need standard mainframe reports
- You want to review usage and cost trends
- You require consistent mainframe reporting

## Prerequisite Components

- CTF- Cost Source
- CTF- IT Towers
- CT Apps- Applications

## Common Sources of Data

Mainframe TCO data typically comes from multiple sources across the mainframe environment and
enterprise systems. Common data sources include:

- **IBM IntelliMagic Vision:** Primary source for mainframe utilization data including GCP MSU,
  zIIP MSU, Allocated Storage, Used Storage, workload consumption, and application usage metrics.
- Other Mainframe performance or telemetry solutions such as zPCA, etc
- **General Ledger:** Source of actual costs for mainframe hardware, software, facilities, and
  depreciation expenses categorized by cost center and account.
- **HR Systems:** Labor costs and headcount for mainframe operations, development, and support
  staff.
- **Vendor Management Systems:** Costs for mainframe software licenses, maintenance agreements,
  and outside services.
- **Asset Management Systems:** Mainframe hardware inventory, configurations, and asset
  lifecycle information.
- **Application Portfolio:** Application names, owners, and business unit associations for cost
  allocation.

## Master Datasets

The Mainframe TCO solution requires multiple master data tables to be populated with mainframe
cost and consumption data. Upload data to these tables and ensure all required fields are mapped
correctly.

**Mainframe Master Data:** GCP MSU consumption, zIIP MSU consumption, Allocated Storage, Used
Storage, workload category, workload type, product line, product name and application name from IBM
IntelliMagic Vision.

For additional information on Mainframe TCO configuration and setup, go [here](../reports/mainframe-config-guide.html)
