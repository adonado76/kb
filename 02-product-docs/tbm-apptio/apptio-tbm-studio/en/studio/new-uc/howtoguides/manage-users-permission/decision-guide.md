---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Decision Guide: Choosing the Right Access Control"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "Access Control"
source_path: "studio/new-uc/howtoguides/manage-users-permission/decision-guide.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Decision Guide: Choosing the Right Access Control

Use this decision framework to determine which access control mechanism (or combination)
best fits your requirements:

**When to Use Report Permissions**

- You want to hide entire reports or dashboards from certain roles
- Different roles need access to different report collections
- You need role-specific views of the same underlying data (using component visibility)
- You want to restrict report creation capabilities by role

**When to Use Row-Level Security**

- Users should see only data relevant to their organizational scope (business unit, region,
  cost center)
- Multiple tenants or divisions share the same TBM Studio instance
- Data restrictions must apply consistently across all reports and tables
- You need fine-grained data filtering based on user identity

**When to Use Editable Table Permissions**

- Distributed teams need to maintain their own data (e.g., cost center managers entering
  budgets)
- You want to restrict who can upload data to specific tables
- Different users should edit different editable tables based on their role
- You need audit control over data entry activities

## Combining Access Controls

For comprehensive security, combine multiple layers. A typical enterprise configuration
might include:

- **Report permissions** to control which dashboards each role can access
- **RLS** to ensure business unit managers see only their own cost data
- **Editable table permissions** so each team can maintain their own mapping
  tables

Important: RLS does not protect data from Admin users. Admins have access to
Studio mode and can author reports that bypass RLS, add themselves to RLS mapping tables, or
disable RLS entirely. Design your security model with this limitation in mind.

**Parent topic:** [Access Control](../../../../studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html)
