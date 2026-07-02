---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Resource Tower Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Financial Use Cases"
  - "Resource Towers"
source_path: "cost-transparency/it-financials/rt-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Resource Tower Getting Started

Use IT Resource Towers to analyze IT spend by functional towers and sub-towers,
enabling consistent review of cost distribution, trends, and alignment with budget. The **CTF –
IT Towers** component is part of the Costing Standard and provides the master data structure
required to support tower-level reporting and analysis.

Before using the IT Towers reports, install the required components and ensure cost data is
mapped to the IT Resource Towers taxonomy.

## Components Install

- **CTF- IT Tower** - The **CTF – IT Towers** component provides insights into the
  costs of IT resource towers and sub-towers and supports comparison of spend against budget
  for operational and strategic reviews. Installing this component creates the **IT
  Resource Towers Master Data**, which is required for all IT Towers reporting.

This component enables you to:

- Identify month-to-month and quarter-to-quarter changes in IT tower spend
- Identify IT towers with significant variance against budget
- Manage IT tower spend at a functional level
- Analyze primary cost sources contributing to each tower

**Prerequisites:**

- **CTF – Cost Source**
  *(Mandatory)*
- Provides the foundational cost data used to allocate spend to IT resource towers.
- **CTF – Labor**
  *(Optional)*
- Enables mapping of labor costs to IT resource towers and sub-towers.
- **CTF – Vendor**
  *(Optional)*
- Enables mapping of vendor spend to IT resource towers and sub-towers.
- **CTF – Fixed Assets**
  *(Optional)*
- Enables mapping of fixed asset costs to IT resource towers and sub-towers.

## Common Sources of Data

The IT resource tower and sub-tower taxonomy is defined by the **Apptio TBM Unified Model
(ATUM)** and is loaded automatically with the Costing Standard project in the **IT
Resource Towers Resource List**.

Not all costs are automatically allocated to towers through other components. To ensure
accurate tower reporting, organizations typically:

- Map cost centers to IT resource towers and sub-towers
- Define allocation percentages when a cost center maps to multiple towers
- Define separate allocation logic for actuals and budget data

Apptio automations can help streamline and accelerate the mapping process. Contact your
Customer Success Manager to learn more about the available options.

**Example Mapping Scenarios**

The following examples illustrate common approaches to mapping cost data to TBM Technology
Resource Towers and Sub-Towers:

- A cost center responsible for data center operations may be mapped to Data Center →
  Enterprise Data Center.
- Roles such as network engineers or LAN administrators can be mapped to Network → LAN,
  while storage administrators may be mapped to Storage → Online Storage.
- Vendor costs for managed security services may be mapped to Security → Digital Security,
  while ITSM or service desk vendors may be mapped to Delivery → Service Management.

## Master Datasets

**IT Resource Towers Master Data**

The IT Resource Towers Master Data defines the structure used to classify costs by tower
and sub-tower. This master data is installed with the **CTF – IT Towers** component.

To support complete allocation and reporting, other datasets should include the following
fields where applicable:

- Cost Source Master Data
  - Cost Center
  - IT Resource Tower
  - IT Resource Sub-Tower
- Labor Master Data *(if installed)*
  - IT Resource Tower
  - IT Resource Sub-Tower
- Fixed Assets Master Data *(if installed)*
  - IT Resource Tower
  - IT Resource Sub-Tower
- Vendor Master Data *(if installed)*
  - IT Resource Tower
  - IT Resource Sub-Tower

If sufficient data is not available to allocate costs accurately, leave those costs in the
Cost Source object rather than applying incomplete or incorrect allocations.
