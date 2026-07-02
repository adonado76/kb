---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Configuration and change policies"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Operations and Governance"
source_path: "it-benchmarking/operations-governance/configuration-change-policies.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Configuration and change policies

You do not want people quietly flipping peer groups, Costing projects, or TBM versions for each
meeting.

**What requires formal approval**  
Changes that should need TBM Lead approval:

- Changing the TBM version in Benchmarking
- Changing the primary Costing project used for benchmarks
- Changing the **default peer group** used in executive reporting
- Adding or removing major cost categories from IT scope used in Benchmarking
- Changing infra domain settings

These changes impact comparability and executive material.

**What can be handled by TBMA discretion**  
Analysts should be free to:

- Create alternative peer groups for **analysis** as long as they are clearly labeled
- Adjust tower mapping details for minor corrections
- Add or refine infra-related Resource Sub-Towers where it does not break existing published
  views

Expectation:

- Every change with non-trivial impact is noted in a simple change log
- Benchmarking Owner re-runs a small validation set after each significant mapping update

**Documentation minimums**  
Bare minimum “paper trail”:

- One-page configuration summary per environment including:
  - Costing project name
  - TBM version
  - Default peer group definition
  - Domains changed (Industry, OpEx, Infra)
  - Current benchmark year
- Lightweight change log with:
  - Date
  - Change
  - Reason
  - Approver (if required)

If a configuration change can materially alter a slide in front of leadership, it deserves a
line in this log.
