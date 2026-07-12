---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Access Control"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "Access Control"
source_path: "SSWRJM/studio/new-uc/howtoguides/manage-users-permission/access-control-intro.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Access Control

| Content Type | How-To Guides |
| --- | --- |
| Content Type | How-To Guides |
| Target Audience | Administrators, Power Users |
| Time to Complete | 45-60 minutes (varies by guide) |
| Prerequisites | Users and roles configured (Section 3.4.1), Admin or Power User role |

## Overview

TBM Studio provides multiple layers of access control to ensure users see only the reports and data appropriate to their role. This section covers three complementary approaches: report permissions (who can see which reports), row-level security (which data rows users can view), and editable table permissions (who can modify specific data).

These access control mechanisms work together to create a comprehensive security model. You can combine them based on your organization's requirements. For the conceptual foundation of TBM Studio's security architecture, see Section 4.4: Security Model . For data-layer implementation details of RLS, see Section 3.1.4: Data Security .

## Understanding Access Control Layers

TBM Studio implements access control at three distinct layers, each serving a different purpose:

| Layer | What It Controls | Best For |
| --- | --- | --- |
| Layer | What It Controls | Best For |
| Report Permissions | Visibility of entire reports and report components | Restricting access to specific dashboards or report collections by user role |
| Row-Level Security (RLS) | Which data rows a user can view across all reports | Multi-tenant scenarios where different users should see different subsets of data (e.g., by business unit or cost center) |
| Editable Table Permissions | Who can edit, upload, or delete data in editable tables | Distributed data entry where different teams maintain their own mapping or classification data |
