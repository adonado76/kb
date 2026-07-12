---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Multi-Level Masters"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
  - "Multi-Level Masters"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/multi-level-masters.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Multi-Level Masters

TBM Studio allows you to apply master reports to other master reports, creating a potential hierarchy. However, this practice is not recommended .

Why Multi-Level Masters Are Discouraged

- Complexity : Multiple levels of inheritance make it difficult to track which elements come from which master
- Maintenance burden : Changes to any master in the chain can have cascading effects
- Troubleshooting difficulty : Visual issues become harder to diagnose with multiple inheritance layers
- Performance considerations : Additional rendering layers may impact report load times
