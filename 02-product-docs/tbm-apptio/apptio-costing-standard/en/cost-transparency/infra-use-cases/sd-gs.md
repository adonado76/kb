---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Service Desk Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Infrastructure Use Cases"
  - "Service Desk"
source_path: "cost-transparency/infra-use-cases/sd-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Service Desk Getting Started

## Getting Started - Service Desk Cost Overview

The Service Desk Cost Overview capability enables organizations to understand and allocate
help desk and support costs across applications, services, and business units based on ticket
volume, priority, impact, and effort. By linking service desk activity data with financial
cost data, this component provides transparency into the true cost of support delivery and
helps organizations manage service desk efficiency, demand, and cost drivers more effectively.

This component is a prerequisite for deeper operational and analytical reporting available
through Service Desk Insights.

**Components Install**

CT Apps– Service Desk

The CT Apps– Service Desk component provides the foundational data structure required for
service desk cost allocation. It captures incident and request handling activity, including
ticket volumes, priorities, impact levels, and time spent resolving issues.

**Prerequisite**

You must install the following components before installing the Service Desk component:

- CTF – Cost Source
- CTF – Labor
- CTF – IT Towers

**Common Sources of Data**

Service desk cost and activity data is typically sourced from a combination of financial
systems and IT service management platforms. Cost and budget data usually comes from the
general ledger, while ticket volume, severity, priority, and resolution effort are sourced
from ITSM and support tools. The level of detail available depends on the data captured in
these systems and mapped to the service desk master data.

**Datasets**

To enable Service Desk Cost Overview reporting, upload service desk input data and map it to
the master data tables provided with the component.

Tickets Master Data contains the complete list of service desk tickets, including impact,
priority, associated applications or services, assignee details, and time spent resolving
issues.

When you install the CT Apps – Service Desk component, a Service Desk table group is created
with a Tickets model table and a Tickets Master Data table. After mapping the data, service
desk costs are allocated from IT Resource Towers to tickets within the cost model, enabling
accurate support cost attribution and reporting.

## Getting Started – Service Desk Insights & Optimization

Service Desk Insights & Optimization builds on the foundational Service Desk cost model
to deliver deeper operational and financial analysis of service desk performance. This
capability provides visibility into service desk ticket volumes, costs, and efficiency
across locations, priorities, and categories, enabling organizations to move from basic cost
tracking to data-driven service optimization

This capability is built on top of **CT Apps– Service Desk** component

**Components Install**

**BI– Service Desk Insights**

Service Desk Insights is delivered through the **BI – Service Desk Insights** component.

**Prerequisite**

Before installing the Service Desk Insights component, ensure the following prerequisite
components are installed and configured in the correct order:

- CTF- Cost Source
- CTF- IT Towers
- CT Apps- Service Desk
