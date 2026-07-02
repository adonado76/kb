---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Common Patterns"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/common-patterns.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Common Patterns

The following patterns represent typical implementations of editable table components.

**Budget Entry Workflow**

Enable cost center managers to enter budget forecasts:

1. Create a blank editable table in Data Studio with columns for cost center, account, period, and
   amount
2. Configure RLS so each manager sees only their cost center
3. Add the editable table component to a budget entry report
4. Include a Total Row Validator to ensure amounts sum correctly
5. Configure a recurring publish schedule to update the model daily

**Data Enrichment Workflow**

Allow users to add classifications to imported data:

1. Create an enriched editable table based on the source transform (e.g., GL data)
2. Add editable columns for classification fields (e.g., Solution, Category, Subcategory)
3. Configure cascading dropdowns to enforce valid combinations
4. Set source columns as read-only to preserve original data
5. Users enrich data without modifying the original import

**Approval Workflow Integration**

Track approval status and comments:

1. Add Status and Approver columns with dropdown values (Pending, Approved, Rejected)
2. Configure Edit Row Permission to restrict approval to authorized roles
3. Use the Show Changes feature to track who made approval decisions
4. Enable .Username and .EditDate columns to display audit information

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
