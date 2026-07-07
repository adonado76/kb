---
source_system: "apptio-billing-standard"
practice: "tbm"
language: "en"
doc_type: "billing"
title: "Implementation Checklist"
breadcrumb:
  - "How to Use This Guide"
  - "Implementation Checklist"
source_path: "SSV8ML/boit/billing/getting-started/checklist.html"
images: []
capability_ids: []
last_updated: "2026-07-06"
summary: ""
---
# Implementation Checklist

*For anyone planning or changing a Billing implementation, this high-level checklist ties the guide together. Later sections provide the detailed steps.*

Confirm Billing edition and components in use

- Determine whether the organization is using Billing Essentials or Billing Standard.
- Verify the correct Component Template version is selected. See Release Notes for applicable versions.

Review prerequisites

- Verify that Costing is deployed and stable.
- Confirm that required master tables and datasets exist or have a plan to be populated.

Align roles and access

- Identify Admins, Analysts, Service or Product Owners, Senior Leaders, and other stakeholders.
- Confirm that appropriate access is granted in the front end and, where applicable, in TBM Studio.

Plan environments and promotions

- Decide how changes are developed and tested in In Development and Staging.
- Define the promotion process and approvals for moving builds into Production.

Design the billing cycle

- Agree on billing periods, timelines, and validation checkpoints.
- Define who validates, who approves, and who receives final outputs.

Choose the configuration path

- Use Configuring Billing Essentials (Implementation) for Billing Essentials.
- Use Configuring Billing Standard (Implementation) for Billing Standard.

Plan training and onboarding

- Use the Role-Based Training Guide to map which roles need which sections and reports.

Once these points are in place, the rest of the guide can be read selectively, using the edition notices and section summaries to find the depth needed for a given task.
