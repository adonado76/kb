---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Project view of Technology spend"
breadcrumb:
  - "Design Patterns and Use Cases"
  - "Project view of Technology spend"
source_path: "SSV8ML/boit/billing/design-uc/uc-project.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Project view of Technology spend

Problem

Portfolio or PMO teams want to understand Technology charges by project for a given period or year.

Inputs

- Project master data (ID, name, owner, type)
- Mappings from costs/usage to projects (labor, infrastructure, cloud, etc.)
- Billing configuration that either: Bills projects directly, or Tags charges with project attributes

Steps

1. Verify project mappings : Confirm labor, infrastructure, and cloud usage are linked to projects where relevant.
1. Run Billing Standard models for the period.
1. Open the Project Billing report : Filter to the current period. View charges by project and service.
1. Apply additional filters as needed: Sponsor, portfolio, project type.
1. Export or further slice: Top projects by Technology spend. Project charges by business unit or consumer.

Key reports

- Project Billing summary (Project × Service × Period)
- Project detail report (with underlying contributors)
- Portfolio dashboard highlighting top projects by spend
