---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Organize Your Cloud Spend"
breadcrumb:
  - "Setup"
  - "Organize Your Cloud Spend"
source_path: "SSVCLNQ/admin/tag-data.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Organize Your Cloud Spend

Native cloud billing data is inherently granular, provider-specific, and optimized for metering, not for business analysis. To make cloud costs meaningful for the various teams and personas within your FinOps practice, Cloudability provides a set of organize features that transform raw billing data into consistent, business-aligned views of spend.

At a high level, these features help answer questions such as:

- Who owns this spend?
- What is the cost by team, application, or business unit?
- How do we enforce consistency and governance for tagging across various parts of the business?
- How can we keep team, department, and group‑level cost reporting aligned as our reporting hierarchy evolves?
- What is the cloud cost per unit of business activity?

Cloudability organizes cloud spend using three complementary capabilities:

Tag & Label Mapping – normalizes inconsistent tagging

Tag & Label Mapping allows you to standardize multiple versions of the same tag into a single, consistent dimension. This ensures that logically equivalent tags are treated as one, even when they differ in format or source. For example, mapping various tag keys of "Env", "ENV", and "enviro" to a single dimension named "Environment".

Account Groups – structures spend by cloud account hierarchy (linked accounts, projects, subscriptions)

Account Groups allow logical grouping of cloud accounts across vendors into meaningful collections, such as environments or departments. By organizing spend at the account level, Account Groups provide a stable, easy-to-understand way to segment costs at a high-level.

Business Mappings – applies custom business logic to allocate and categorize costs

Business Mappings provide a rules-based engine that evaluates billing and usage data and assigns costs to Business Dimensions aligned with your organizational taxonomy. These mappings translate vendor-specific metadata such as tags, account names, regions, or services into business categories optimized for analytics and decision-making. This ensures that every dollar is categorized and allocated appropriately.

Furthermore, Hierarchical Business Mappings can be used to define and maintain parent‑child relationships between related Business Dimensions, enabling scalable cost rollups and consistent reporting across organizational levels as structures change.

Business Metrics – applies custom, rules‑based arithmetic calculations to cloud cost and usage data to produce business‑specific financial metrics

Business Metrics extend Cloudability’s standard cost metrics by allowing you to define custom financial calculations that translate raw cloud cost and usage data into business‑relevant measures. Using configurable formulas and conditional logic, Business Metrics enable teams to model chargeback rates, unit costs, efficiency ratios, and other organization‑specific KPIs.
