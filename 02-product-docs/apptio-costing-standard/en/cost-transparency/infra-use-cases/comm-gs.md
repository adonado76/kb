---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Communications Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Communications"
source_path: "cost-transparency/infra-use-cases/comm-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Communications Getting Started

The Communications component enables organizations to allocate communication
infrastructure costs, such as circuits, voice services, and usage-based charges, to the
appropriate consumers. It supports transparent and defensible allocation of communication spend
to applications, services, and business units, helping establish accurate application and
service total cost of ownership (TCO).

## Components Install

**CT Apps – Communications**

The Communications component installs a new Communications object, supporting datasets, and
allocation logic used to distribute communication costs to consuming services. It supports
allocation of communication costs to servers supporting data centers, end-user devices
supporting office and workforce connectivity, and specific business services such as call
centers or retail kiosks.

You must install the following components before installing the Communications component:

CTF – Cost Source

CTF – IT Towers

## Common Sources of Data

Communication cost and usage data is typically sourced from the general ledger and telecom
or network expense systems. The level of detail available depends on the source data
provided and determines how costs are mapped to the Communications Master Data for
allocation and reporting.

## Datasets

When the CT Apps – Communications component is installed, a Communications group is created
with the following tables:

Communications (model table)

Communications Master Data

After uploading communication data, map it to the Communications Master Data table. Once
mapped, costs flow from IT Resource Towers to Communications, and from Communications to
Servers and Business Services within the cost model.
