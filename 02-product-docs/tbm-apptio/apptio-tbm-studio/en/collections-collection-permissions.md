---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Collection Permissions"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Collections"
  - "Collection Permissions"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/collection-permissions.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Collection Permissions

Permission Model Overview

TBM Studio supports permissions at both the collection level and the individual report level. Understanding how these permissions interact is essential for properly securing your reports.

| Permission Level | Description |
| --- | --- |
| Permission Level | Description |
| Collection-Level | Controls which roles can see and access the collection as a whole. Users without access to a collection will not see it in the navigation. |
| Report-Level | Controls which roles can view specific reports within a collection. A user may have access to a collection but not to all reports within it. |
| Component-Level | Controls visibility of specific components (tables, charts, groups) within a report based on user role. |

Permission Inheritance

When a user attempts to access a report in a collection, TBM Studio evaluates permissions in the following order:

- Collection Access: The user must have access to the collection to see it in navigation
- Report Access: The user must have permission to view the specific report
- Component Visibility: Individual components may be hidden or shown based on role

Report-level permissions do not automatically inherit from collection-level permissions. You must configure both if you want to restrict access at multiple levels.

Setting Collection Permissions

Collection permissions are configured through the Manage Report Collections dialog. Administrators can specify which roles have access to view reports within each collection.

For detailed information on configuring report permissions, see Work with report permissions in the TBM Studio documentation.

Component Visibility by Role

For scenarios where different roles need to see different components within the same report, you can use report groups with role-based visibility. This allows you to create a single report that displays different content to different user roles.

- Add one report group per role containing the components visible to that role
- Configure each group to be visible to only one role
- Layer the groups on the reporting surface so the user's role determines which group they see
