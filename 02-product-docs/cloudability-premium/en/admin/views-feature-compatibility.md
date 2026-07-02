---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "admin"
title: "Views Feature Compatibility"
breadcrumb:
  - "Cloudability Premium"
  - "Administration"
  - "Create and Manage Views"
source_path: "admin/views-feature-compatibility.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Views Feature Compatibility

While Views provide you with powerful capabilities to organize and control how cloud cost and
usage data is shared among Cloudability users, their support currently varies across different
Cloudability features. Some features offer full Views support, while others have partial support or
specific limitations.

This document provides a reference guide to help you understand which Cloudability features
support Views, to what extent, and any specific limitations or caveats when using Views with certain
features. Use this guide when planning your Views strategy or troubleshooting unexpected behavior in
specific features.

|  |  |  |
| --- | --- | --- |
| **Feature** | **Views Support** | **Limitations** |
| Dashboard and Reports | Full Support |  |
| TrueCost Explorer | Full Support |  |
| Containers  and  Container Rightsizing | Partial Support | Only Views based on Account Id, Account Name, Account groups and Vendor dimensions are supported. |
| Advanced Container | Not Supported | We’ll start Partial support (similar to containers) soon. |
| Tag Explorer | Full Support |  |
| Anomaly Detection | Partial Support | Only Views based on Account Id, Account Name, Service, Usage family and Top 5 BM (as detected by Anomaly algorithm) are supported. |
| Resource Inventory | Full Support |  |
| Commitment | Partial Support | Views based on Account Id, Account groups and Vendor dimensions.  Additionally, if a view is facilitated via a business mapping, and the business mapping is based on some combination of accounts or vendors, it would be supported. |
| Rightsizing | Full Support, Except one caveat → | Caveat: When a View is based on a Business Mapping, Accounts drop-down shows all the accounts including the ones that should be restricted by the view. Alternatively, you can use Account Groups based filter in Views. |
| Rightsizing ROI | Full Support, Except one caveat for RS Policy → | Caveat: When creating a Rightsizing Policy (Settings > Rightsizing Policies), ‘Views’ dropdown only contain Shared views. |
| Budget | Full Support | Budgets are scoped to Views. The View selected at the top determines which budgets are displayed. Selecting **“Show All Data”** displays budgets from all Views. |
| Forecast | Full Support |  |
| Plans | Full Support |  |
| Scorecards | Full Support |  |
| Workload Planning | Not Supported | Views are not applicable on this feature. |
| Governance | Not Supported | Views are not applicable on this feature. |

**Parent topic:** [Create and Manage Views](../admin/create-and-manage-views.html)
