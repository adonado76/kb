---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "RLS Inheritance and Flow"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Row-Level Security (RLS)"
source_path: "studio/new-uc/concepts-architecture/security-model/rls-inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# RLS Inheritance and Flow

Understanding how RLS flows through the data pipeline is critical for avoiding security gaps.

**RLS in Model Allocations**

When costs are allocated from one table to another, the RLS configuration on the source and
target tables are independent. Consider an example where BU 3 allocates costs to BU 2:

- If Bob (who can see only BU 2) views the allocation results, he will see costs allocated to BU
  2—including costs that originated from BU 3.
- Bob cannot see the BU 3 source data directly, but he can see the effects of allocations into his
  permitted business units.

This is expected behavior—RLS filters visible rows, but it does not prevent allocated costs from
flowing through the model.

**RLS in Report Aggregations**

When a report displays aggregated data (totals, sums, averages), the aggregation reflects only
the rows visible to the current user. If Bob can see only BU 2, a total cost column in his report
shows only BU 2’s costs—not the full organizational total.

**RLS and Editable Table Publishing**

When a user publishes changes from an editable table, RLS ensures that only the rows visible to
that user are editable. Critically, hidden rows are preserved during publishing—they are not deleted
or overwritten. This means multiple users can edit different subsets of the same editable table
without interfering with each other’s data.

Note:

**Testing RLS**

Use the Preview Filter in the RLS pipeline step to test your configuration. Enter a user’s email
address to see exactly which rows that user would see. You can also use the impersonation feature
(available to administrators) to view reports as a specific user.

**Parent topic:** [Row-Level Security (RLS)](../../../../studio/new-uc/concepts-architecture/security-model/row-level-security.html)
