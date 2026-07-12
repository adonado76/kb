---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Common Patterns"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
  - "Common Patterns"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/common-patterns.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Common Patterns

The following patterns represent typical implementations of editable table components.

Budget Entry Workflow

Enable cost center managers to enter budget forecasts:

1. Create a blank editable table in Data Studio with columns for cost center, account, period, and amount
1. Configure RLS so each manager sees only their cost center
1. Add the editable table component to a budget entry report
1. Include a Total Row Validator to ensure amounts sum correctly
1. Configure a recurring publish schedule to update the model daily

Data Enrichment Workflow

Allow users to add classifications to imported data:

1. Create an enriched editable table based on the source transform (e.g., GL data)
1. Add editable columns for classification fields (e.g., Solution, Category, Subcategory)
1. Configure cascading dropdowns to enforce valid combinations
1. Set source columns as read-only to preserve original data
1. Users enrich data without modifying the original import

Approval Workflow Integration

Track approval status and comments:

1. Add Status and Approver columns with dropdown values (Pending, Approved, Rejected)
1. Configure Edit Row Permission to restrict approval to authorized roles
1. Use the Show Changes feature to track who made approval decisions
1. Enable .Username and .EditDate columns to display audit information
