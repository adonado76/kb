---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Project view of Technology spend"
breadcrumb:
  - "Billing"
  - "Design Patterns and Use Cases"
source_path: "boit/billing/design-uc/uc-project.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Project view of Technology spend

Note: **Applies to Billing Standard only.**

**Problem**

Portfolio or PMO teams want to understand Technology charges by project for a given period or
year.

**Inputs**

- Project master data (ID, name, owner, type)
- Mappings from costs/usage to projects (labor, infrastructure, cloud, etc.)
- Billing configuration that either:
  - Bills projects directly, or
  - Tags charges with project attributes

**Steps**

1. Verify **project mappings**:
   - Confirm labor, infrastructure, and cloud usage are linked to projects where
     relevant.
2. Run Billing Standard models for the period.
3. Open the **Project Billing report**:
   - Filter to the current period.
   - View charges by project and service.
4. Apply additional filters as needed:
   - Sponsor, portfolio, project type.
5. Export or further slice:
   - Top projects by Technology spend.
   - Project charges by business unit or consumer.

**Key reports**

- Project Billing summary (Project × Service × Period)
- Project detail report (with underlying contributors)
- Portfolio dashboard highlighting top projects by spend
