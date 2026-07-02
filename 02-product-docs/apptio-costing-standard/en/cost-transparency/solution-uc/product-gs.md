---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Products Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Solution Use Cases"
  - "Products"
source_path: "cost-transparency/solution-uc/product-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Products Getting Started

The Product TCO component enables organizations to model, calculate, and analyze total
cost of ownership (TCO) for products across their entire lifecycle. It provides end-to-end
transparency into product costs by connecting financial and operational data, allowing Product,
Finance, and Technology teams to understand cost drivers, track lifecycle spend, and align
investment decisions with strategic outcomes. This component is part of the Product Content
Suite and supports consistent, product-centric financial governance across the
portfolio.

## Component Installation

The Product TCO solution is enabled via two new components created for the solution. They
are:

- Product TCO
- Product TCO Reporting

**Note:** These components are available in templates **v120 and later**.

## Prerequisite

You must install the following components before installing the Product TCO component:

- CTF- Cost Source
- CTF- Labor
- CTF- IT Towers
- CT Apps- Applications
- CT Apps- Services
- CT- Business Units

## Common Sources of Data

Product TCO leverages financial and operational data from multiple enterprise systems. Cost
data is typically sourced from the general ledger, including OpEx and CapEx across cost
pools and accounts. Supporting data commonly comes from application portfolios, project and
investment management systems, labor and time tracking tools, and vendor or contract
management platforms. These sources enable accurate attribution of costs to products and
support lifecycle and portfolio-level analysis.

**Datasets**

You may have to upload Product Catalog Feed table and map to the All Business Services
master dataset provided within the component.

Also, to classify offerings as products, select **All Business Services** as the
destination and set **Service Offering Type = Product** in the Service Offering
field.
