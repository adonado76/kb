---
source_system: "apptio-billing"
practice: "tbm"
language: "en"
doc_type: "boit"
title: "Implementation Checklist"
breadcrumb:
  - "Billing"
  - "How to Use This Guide"
source_path: "boit/billing/getting-started/checklist.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Implementation Checklist

For anyone planning or changing a Billing implementation, this high-level checklist ties
the guide together. Later sections provide the detailed steps.

**Confirm Billing edition and components in use**

- Determine whether the organization is using Billing Essentials or Billing Standard.
- Verify the correct Component Template version is selected. See [Release Notes](../release-notes/whats-new.html "This section describes changes to the out-of-box Billing content only, not the underlying platform. For platform-level updates such as TBM Studio and Client server behavior, readers should review TBM Studio’s Release Notes and consider applicable changes alongside what is documented here.") for applicable versions.

**Review prerequisites**

- Verify that Costing is deployed and stable.
- Confirm that required master tables and datasets exist or have a plan to be
  populated.

**Align roles and access**

- Identify Admins, Analysts, Service or Product Owners, Senior Leaders, and other
  stakeholders.
- Confirm that appropriate access is granted in the front end and, where applicable, in TBM
  Studio.

**Plan environments and promotions**

- Decide how changes are developed and tested in In Development and Staging.
- Define the promotion process and approvals for moving builds into Production.

**Design the billing cycle**

- Agree on billing periods, timelines, and validation checkpoints.
- Define who validates, who approves, and who receives final outputs.

**Choose the configuration path**

- Use [Configuring Billing Essentials
  (Implementation)](../config-be/be-overvie.html "This section describes how Billing Essentials is configured in a Costing Essentials project, from installing components through to first usable bills. It assumes that Costing Essentials is already deployed and stable.") for Billing Essentials.
- Use [Configuring Billing Standard
  (Implementation)](../config-bs/bs-overview.html "This section describes how Billing Standard is configured on top of a Costing Standard project, from installing components through to first usable domain-rich bills. It assumes that Costing Standard is already deployed and stable.") for Billing Standard.

**Plan training and onboarding**

- Use the [Role-Based Training Guide](../role-based-tg/train-objectives.html "This section outlines how to train different audiences so Billing is actually used and trusted, not just technically deployed. Use it to design onboarding, recurring training, and handoffs when people change roles.")
  to map which roles need which sections and reports.

Once these points are in place, the rest of the guide can be read selectively, using the
edition notices and section summaries to find the depth needed for a given task.
