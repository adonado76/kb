---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Dependency summary"
breadcrumb:
  - "Billing"
  - "Administration and Operations"
  - "Solution Architecture and Dependencies"
source_path: "boit/billing/sol-arch-depend/depend-summary.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Dependency summary

The table below summarizes key dependencies for each edition.

|  |  |  |
| --- | --- | --- |
| **Area** | **Billing Essentials** | **Billing Standard** |
| **Costing requirement** | Costing Essentials project deployed | Costing Standard project deployed |
| **Component Template** | Version 200 | Version 120 and earlier |
| **Billing components** | Billing – Charge, Billing – Charge Reporting | Multiple components (Foundation, Units, Applications, Cloud, etc.) |
| **Endpoint** | No separate Billing endpoint; uses Costing Essentials | Separate Billing endpoint in addition to Costing Standard |
| **Front-end entry point** | Costing Essentials front end, Billing report collection | Dedicated Billing Standard application/endpoint |
| **TBM Studio dependency** | Same project as Costing Essentials | Same project as Costing Standard |

This architecture and dependency view should be checked before any configuration or
troubleshooting work. If one of the prerequisites is missing or misaligned, Billing behavior
in later sections of the guide will not match what is described.
