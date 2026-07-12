---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Component-Level Visibility"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Security Model"
  - "Report and Component Permissions"
source_path: "studio/new-uc/concepts-architecture/security-model/component-level-visibility.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Component-Level Visibility

For more granular control, you can configure individual report components to show or hide based
on conditions.

**Visibility Options**

Each report component supports several visibility settings:

- **Component contains data:** Hides the component if it does not contain or calculate data.
- **User’s current role is:** Shows the component only to users with specific roles. This
  allows you to create a single report that displays different components to different audiences.
- **Dynamic text evaluates to “hidden”:** Hides the component based on a calculated
  condition—for example, hiding a variance component when variance is positive.

**Role-Based Component Visibility Pattern**

A common pattern is to create report groups that contain role-specific components, then stack
these groups on the same report surface. Each group is set to be visible to one role only. When a
user opens the report, they see only the components for their role.

Note:

**Multiple Roles**

If a user has two of the roles that different groups are visible to, they will see the components
for the role whose group is on top of the stack. Design your report group layering carefully to
handle users with multiple roles.

**Parent topic:** [Report and Component Permissions](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
