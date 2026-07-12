---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Integration with Other Workflows"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
source_path: "studio/new-uc/concepts-architecture/integration-other-wf.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Integration with Other Workflows

The build lifecycle integrates with several other TBM Studio workflows. Understanding these
connections helps you plan your work effectively.

**Editable Tables and Auto-Promotion**

Editable tables allow end users to input data through reports. When published, this data flows
through the build lifecycle:

1. User edits data in a report exposing an editable table
2. Publish writes editable table data to its associated transform table
3. Transform table updates feed into model objects
4. Model recalculates during next staging or production build
5. Reports reflect updated allocations

Editable table schedules can trigger staging calculations automatically and, if configured,
auto-promote to Production. This creates a fully automated data-to-production pipeline.

**Data Freshness Rules**

Data freshness rules monitor table updates and integrate with the build lifecycle:

- Rules detect when expected data is missing or stale
- System sends notifications to administrators
- Administrators update tables and check in
- Next model calculation incorporates updated data

Freshness indicators are particularly critical during month-end close processes, helping to
diagnose whether stale model outputs are due to missing data updates.

**Time Periods and Versioning**

The active time period setting affects builds at every layer:

- **Data Studio:** Date partition filtering determines which month's data enters transforms
- **Model Studio:** Calculations use the version corresponding to the active period
- **Reports:** Values displayed reflect the active period's data
- **Closed periods:** Prevent updates but can still be reported on
