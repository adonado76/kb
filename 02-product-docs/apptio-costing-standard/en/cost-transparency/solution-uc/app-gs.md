---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Applications Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Solution Use Cases"
  - "Applications"
source_path: "cost-transparency/solution-uc/app-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Applications Getting Started

The Applications component is part of the Cost Transparency Applications and Services
module. It enables organizations to allocate infrastructure and application-related costs to
applications in order to calculate accurate Application Total Cost of Ownership (TCO). This
component installs the required data structures, metrics, and reports needed to analyze
application costs across labor, infrastructure, projects, and supporting services.

## Components Install

**CT Apps– Applications**

The Applications component installs new data sets, metrics and reports, which helps to
allocate infrastructure and application related costs to determine the TCO of the company's
applications.

**CT Apps- Applications NX Reports (Additional Component)**

This component provides
predefined NX reports based on application data for analysis across applications, portfolios, and
time periods.

Use this component when:

- You need standard application reports
- You want to review cost and usage trends
- You require consistent application reporting

## Prerequisites

You must install the following components before installing the Applications component:

- CTF- Cost Source
- CTF- IT Towers

**Common Sources of Data**

Application cost and attribute data is typically sourced from general ledger systems,
application inventory or CMDB platforms, project and portfolio management tools, and IT
service management systems. Infrastructure-related cost inputs flow from compute, storage,
service desk, and project data sources already configured within the cost model.

## Datasets

When you install the CT Apps – Applications component, a new Applications group is created
with the following tables:

- Applications (model table)
- Applications Master Data

After uploading application data, map the dataset to the Applications Master Data table.
After mappingthe data, there should be value allocated from IT Resource Towers, Servers,
Tickets, and Projects to Applications in the Cost model.
