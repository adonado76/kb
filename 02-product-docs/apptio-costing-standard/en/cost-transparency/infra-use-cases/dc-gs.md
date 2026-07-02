---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Data Centers TCO - Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Data Centers"
source_path: "cost-transparency/infra-use-cases/dc-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Data Centers TCO - Getting Started

The Data Center TCO solution enables organizations to understand the total cost, capacity,
utilization, and operational constraints of their data center footprint. It provides visibility into
facility costs, power and cooling consumption, rack density, and infrastructure allocations to
support optimization, consolidation, and long-term investment planning.

## Component Install

**Data Centers TCO**

The Data Centers TCO component provides the foundational framework required to model, allocate,
and report on data center costs, capacity, utilization, and operational constraints. The component
installs the datasets, editable tables, metrics, allocation logic, and core data structures required
to analyze data center operations and establish defensible unit economics across locations and
facilities.

This component is required before installing either of the reporting components below:

- **Data Centers TCO Reporting** – Installs the Classic reports for Data Center TCO reporting
  and analysis
- **Data Centers TCO NX Reporting**– Installs the NX reports for Data Center TCO reporting and
  analysis.

Customers can install either the Classic or NX reporting component based on their reporting
experience preference. However, the base Data Centers TCO component must be installed first in all
scenarios.

## Prerequisites

You must install the following components before installing the Data Centers TCO solution:

- CTF – Cost Source
- CTF – IT Towers
- CTF – Labor
- CTF – Vendors

Optional supporting components include:

- CT Apps – Servers
- CT Apps – Storage
- CT Apps – Mainframes
- CT Apps – Applications
- CT Apps – Services
- Product TCO

## Common Sources of Data

Data center cost, utilization, and operational data is typically sourced from:

- General ledger and financial systems
- Data Center Infrastructure Management (DCIM) platforms
- Power and cooling monitoring systems
- CMDB and asset management platforms
- Facilities management systems
- Vendor and procurement systems

These sources provide financial, capacity, infrastructure, and operational metadata used for
allocation, utilization analysis, and unit economics reporting.

## Datasets

The primary dataset for the solution is the Data Centers Feed table. Upload and map data center
operational, financial, and capacity data into the Data Centers Master Data provided with the
component.

Common dataset attributes include:

- Data Center ID and Name
- Region and Facility Type
- Rack Unit Capacity and Usage
- Power Capacity and Consumption
- Cooling Capacity and Utilization
- Square Footage Capacity and Occupied Space
- Manager, Tier, and Operational Metadata

After loading and mapping the data, validate allocations to ensure data center costs flow
correctly to compute, storage, and supporting infrastructure objects for downstream reporting and
analysis.
