---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Storage Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Storage"
source_path: "cost-transparency/infra-use-cases/storage-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Storage Getting Started

## Getting Started – Storage Cost Overview

The Storage Cost Overview solution enables organizations to establish foundational cost
transparency for storage infrastructure by allocating storage costs to applications and
services to understand true storage total cost of ownership. It provides visibility into
storage spend across on-premises and cloud environments and serves as the prerequisite for
advanced storage analytics and optimization available through Storage Insights.

**Components Install**

**CT Apps- Storage** - The Storage Cost Overview solution is enabled by installing the
**CT Apps- Storage**component. This component installs the core data structures,
metrics, and foundational storage reports required for storage TCO analysis and application
cost allocation.

**Prerequisite**

Before installing the CT Apps-Storage component, the following components must already be
installed:

- CTF- Cost Source
- CTF- IT Towers

**Common Sources of Data**

Storage cost and inventory data typically comes from a combination of infrastructure and
financial systems. Common sources include asset management systems for storage devices and
LUN inventory, storage management platforms for capacity and tier information, configuration
management databases for application relationships, and the general ledger for
storage-related hardware, software, labor, and support costs.

**Datasets**

To enable storage cost reporting, data must be uploaded and mapped to the core storage
master datasets installed with the CT Apps-Storage component. These datasets include storage
device master data containing physical storage attributes and storage master data capturing
logical units, capacity, tiering, sourcing, and environment information. Once populated,
these datasets support foundational storage TCO reporting and downstream storage insights.

## Getting Started – Storage Insights & Optimization

Storage Insights & Optimization extends foundational storage cost visibility with
deeper operational, capacity, and utilization analytics. It enables organizations to analyze
storage cost efficiency, utilization patterns, and lifecycle health across on-premises,
cloud, and hybrid environments. This capability supports operational reviews, optimization
initiatives, and technology refresh planning by combining financial, capacity, and
utilization data into a single analytical view.

**Components Install**

BI- Storage Insights

This component provides enhanced analysis of storage infrastructure, including visibility
into unit costs, utilization and efficiency.

**Prerequisite**

It requires the following components to be installed prior to enablement:

- CTF- Cost Source
- CTF- IT Towers
- CT Apps- Storage

**Common Sources of Data**

Storage Insights & Optimization relies on data from multiple infrastructure and
enterprise systems to provide a complete view of storage cost and utilization, including:

- On-premises storage infrastructure data covering storage devices and logical units
  (LUNs)
- Datacenter and infrastructure inventory systems
- VMware vCenter for private cloud environments, collected via Apptio Datalink (Classic)
  connectors where applicable
- Public cloud billing data from AWS, Azure, or Google Cloud, collected via Apptio
  Datalink (Classic) connectors where applicable
- Storage utilization data capturing raw, allocated, and used capacity
- Operational metrics including average and peak utilization indicators

**Datasets**

Storage Insights & Optimization requires the following datasets to be populated and
mapped correctly:

- Storage Master Data – Logical storage units (LUNs), capacity, allocation, tier, and
  environment attributes
- Storage Devices Master Data – Physical storage device inventory, type, model, vendor,
  location, and lifecycle details
