---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Services Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Solution Use Cases"
  - "Services"
source_path: "cost-transparency/solution-uc/services-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Services Getting Started

Use the Services component to consolidate and analyze technology costs by service. The
CT Apps - Services component provides the data structure and model objects necessary for service
cost reporting and analysis.

Install and configure the Services component, then upload your service data including service
definitions, service ownership, consumption metrics, and service categorization. After the
component is installed, map your data to the appropriate tables.

## Component Install

The CT Apps– Services component provides visibility into IT spending on Services, enabling
organizations to understand total service costs, track month-to-month spend changes, and
measure performance against plan. It consolidates underlying technology, application, labor,
and vendor costs into a service-level view, supporting consistent service cost transparency
and portfolio analysis.

## Component Installed

**CT Apps – Services**

The CT Apps – Services component installs the foundational data structures, datasets, metrics,
and reports required to analyze Business Service costs, trends, and budget performance across the
enterprise.

**CT Apps- Services NX Reports (Additional Component)**

This component provides
predefined NX reports based on services data for analysis across services, categories, and time
periods.

Use this component when:

- You need standard services reports
- You want to review cost and usage trends
- You require consistent services reporting

## Prerequisites

You must install the following components before installing the Services component:

• CTF- Cost Source

• CTF- IT Towers

• CT Apps- Applications

## Common Sources of Data

Business service data typically comes from service catalogs, CMDB systems, application
portfolio management tools, and service management platforms. The data you use will
determine the level of detail available for service cost analysis and consumption
tracking.

Common data sources include:

- **Service Management Platforms:** Service definitions, service catalog data, and
  consumption metrics (ServiceNow, BMC Remedy, Cherwell).
- **Configuration Management Database (CMDB):** Service-to-application relationships
  and service dependency mapping.
- **Application Portfolio Management:** Service ownership, service lifecycle stage, and
  application-to-service mappings (ServiceNow APM, LeanIX).
- **IT Business Management Systems:** Service cost data, service consumption volumes,
  and service-level metrics.
- **Service Catalogs:** Published service definitions, service descriptions, and
  service categorization.

## Datasets

You will need to upload service data and map it to the All Business Services table. While
there is no separate master data table for the CT Apps - Services component, the All
Business Services table serves a similar function and contains all service definitions and
attributes.

**All Business Services**

This table defines all business services in your service portfolio. It contains service
identification, categorization, ownership, consumption metrics, and allocation
configuration. All service data should be mapped to this table.
