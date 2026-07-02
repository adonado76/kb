---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Pre-go-live readiness checklist"
breadcrumb:
  - "Billing"
  - "Go-Live Playbook"
source_path: "boit/billing/go-live/gl-checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Pre-go-live readiness checklist

This is the minimum you should have in place before you even schedule a go-live
date.

**Data and model readiness**

- Costing model:
  - Allocations are stable for at least one or two prior periods.
  - No critical open issues that regularly break runs.
- Billing inputs:
  - Services / offerings catalog is reviewed and approved.
  - Consumer master is complete for all entities to be billed.
  - Consumption feeds cover all in-scope services and consumers.
  - Rate or price tables are loaded for the go-live period and the next few periods.

**Environment and release readiness**

- In Development:
  - All Billing configuration work is checked in.
  - No half-finished experiments left hanging.
- Staging:
  - Contains a complete build with all Billing changes included.
  - Staging build used for dress rehearsal.
- Production:
  - Free of any test and POC content that could confuse users.

**Report and access readiness**

- Reports:
  - Core Billing reports identified for go-live (not every single report).
  - Report filters and prompts behave as expected.
  - Key views have been reviewed with stakeholders.
- Access:
  - Admins and Analysts can reach the relevant project/endpoint.
  - Service or Product Owners can see the reports they need.
  - Finance can access journal exports where applicable.
