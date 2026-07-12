---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Network Devices Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Network Devices"
source_path: "cost-transparency/infra-use-cases/nd-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Network Devices Getting Started

Use the Network Devices Cost Overview components to load, model, and allocate network
infrastructure costs across the enterprise. This capability enables organizations to allocate
LAN, WAN, Voice, and other network device costs from data centers and office locations to the
consumers of those services, providing transparency into how network costs are incurred and
consumed across IT and the business.

**Components Install**

CT Apps– Network Devices

The Network Devices component installs a new object, supporting datasets, and recommended
allocation strategies for apportioning network infrastructure costs. These costs are allocated
to the following typical consumers:

Mainframe

Network equipment supporting mainframes in enterprise data centers.

Physical Servers

Network equipment supporting server infrastructure in enterprise data centers.

Storage Devices

Network equipment supporting storage platforms in enterprise data centers.

End User Devices

Network equipment supporting wired and wireless connectivity for PCs, laptops, and mobile
devices in office locations.

**Prerequisites**

You must install the following components before installing the Network Devices component:

CTF- Cost Source

CTF- IT Towers

**Common Sources of Data**

Network device data is typically sourced from financial systems such as the general ledger
for cost and budget information, combined with network management and monitoring tools (for
example SolarWinds, Cisco DNA Center, SNMP-based tools), CMDB platforms, and asset management
systems. Together, these sources provide visibility into network inventory, costs,
utilization, and relationships required for accurate network cost allocation and reporting.

**Datasets**

The primary dataset required is the Network Devices Master Data, which captures device
attributes such as location, type, purpose, sourcing, and supported infrastructure. This
dataset is populated using data extracted from network management, monitoring, CMDB, and
financial systems and is used to allocate network costs to Physical Servers, Storage Devices,
End User Devices, and Mainframes within the cost model.
