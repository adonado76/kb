---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Cost Ownership"
breadcrumb:
  - "Configuring Cloudability Financial Planning"
  - "Cost Ownership"
source_path: "SSVWBC/cloud-financial-planning/admin/cost-ownership.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Cost Ownership

*Every plan must include a cost ownership dimension, and this dimension must be a Cloudability dimension.*

The primary role of the cost ownership dimension is to divide the plan into distinct ownership segments, which can then be employed to filter the plan's contents and control what users can edit when the plan is shared among multiple users. This allows you to create a consolidated forecast for your entire organization while still having the flexibility to share specific segments of the forecast with individual users for their viewing and editing.

For instance, if your cost ownership dimension is "Account," you can assign individual users to different accounts when sharing the plan. Each user will only be able to modify forecast line items associated with their assigned account(s). They can filter the plan to display only the costs related to "their" accounts. In this way, the cost ownership dimension provides a replacement for individual Cloudability views when working with a consolidated forecast.

Furthermore, it is crucial to recognize that the cost ownership dimension also determines the level of detail for budgets within the plan. Each cost ownership value corresponds to one budget line item.
