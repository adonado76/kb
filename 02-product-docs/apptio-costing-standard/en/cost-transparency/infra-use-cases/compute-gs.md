---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Compute Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Compute"
source_path: "cost-transparency/infra-use-cases/compute-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Compute Getting Started

## Getting Started - Compute Cost Overview

Use the Compute Management components to load and manage server inventory, utilization,
cost, and lifecycle data required for compute cost transparency and application-level TCO
analysis. This capability establishes the foundational data model for analyzing compute
costs across physical, virtual, private cloud, and public cloud environments, and supports
downstream infrastructure and application cost reporting.

**Components Install**

CT Apps– Servers - The CT Apps– Servers component provides the core data structures,
metrics, and allocations required to model server infrastructure costs and associate them
with applications. This component is a prerequisite for advanced Server Insights reporting
and enables allocation of compute infrastructure costs to applications to support TCO
analysis.

**Prerequisites:**

• Cost Source

• IT Towers

**Common Sources of Data**

Compute data is typically sourced from a combination of infrastructure and enterprise
systems. Common sources include server monitoring tools for CPU, memory, and utilization
metrics; virtualization platforms such as VMware or Hyper-V for virtual machine and host
relationships; asset management systems for server inventory, configuration, and lifecycle
details; CMDBs for server-to-application relationships and environment classification;
service management tools for incident and support data; and general ledger systems for
compute-related hardware, software, labor, and support costs.

**Datasets**

The Compute Management solution requires multiple master datasets to be populated and
mapped correctly. These include Server Master Data for all physical and virtual servers,
Physical Server Master Data for physical hosts and hypervisors, and Hypervisor Master Data
for servers hosting virtual workloads. Server data is typically sourced from a single
inventory extract and transformed into separate datasets to ensure accurate modeling of
physical servers, virtual servers, and hypervisors, enabling correct cost allocation and
utilization analysis.

## Getting Started - Compute Insights & Optimization

Compute Insights & Optimization provides deep visibility into server cost, capacity,
utilization, and efficiency across hybrid infrastructure environments. This capability is
built on top of the foundational **CT Apps- Servers**component and extends it through
**BI- Server Insights**, part of the Infrastructure Insights module. Together, these
components enable advanced operational and financial analysis of physical and virtual server
environments, supporting optimization, standardization, and lifecycle decisions.

**Components Install**

**BI- Server Insights** - Compute Insights & Optimization is enabled through the
**BI - Server Insights**component. This component delivers enhanced analysis of
server infrastructure, including unit cost trends, utilization efficiency, and operational
performance across on-premises and cloud environments.

**Prerequisite**

The following components must be installed before installing
Server Insights:

• CTF- Cost Source

• CTF- IT Towers

• CT Apps –
Servers

**Common Sources of Data**

Compute and infrastructure data is typically
sourced from server inventory and monitoring systems, virtualization platforms such as
VMware vCenter, data center and asset management systems, and public cloud billing data
from providers such as AWS, Azure, and Google Cloud when applicable. Utilization metrics
include average and peak CPU and memory usage, along with storage utilization data where
available.

**Master Datasets**

The Server Insights capability relies on datasets populated through the CT Apps – Servers
component, including physical server, logical server (VM), and hypervisor master data,
combined with cost data from Cost Source and tower mappings from IT Towers. These datasets
enable detailed modeling of server costs, utilization, and allocation to applications and
services for optimization analysis.
