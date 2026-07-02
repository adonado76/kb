---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Multi-Level Masters"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
source_path: "studio/new-uc/reference/report-studio-reference/multi-level-masters.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Multi-Level Masters

TBM Studio allows you to apply master reports to other master reports, creating a potential
hierarchy. However, **this practice is not recommended**.

**Why Multi-Level Masters Are Discouraged**

- **Complexity**: Multiple levels of inheritance make it difficult to track which elements come
  from which master
- **Maintenance burden**: Changes to any master in the chain can have cascading effects
- **Troubleshooting difficulty**: Visual issues become harder to diagnose with multiple
  inheritance layers
- **Performance considerations**: Additional rendering layers may impact report load times

Note: If you find yourself needing multi-level masters, consider redesigning your master structure
to use a single, comprehensive master report that includes all necessary elements.

**Parent topic:** [Master Reports](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
