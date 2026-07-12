---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Component-Level Permissions"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
source_path: "studio/new-uc/reference/report-studio-reference/component-level-permission.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Component-Level Permissions

**Hiding Components by Role**

Individual report components can be hidden from specific roles while remaining visible to others.
This allows creating multi-purpose reports that display different information based on user role.

**Configuring Component Visibility:**

1. Select the component in the report
2. On the Report tab, in the Advanced group, click Visibility
3. Select User's current role is option
4. Choose the roles that should see the component
5. Save and check in the report

**Visibility Options**

The Report Component Visibility dialog offers multiple visibility conditions:

|  |  |
| --- | --- |
| **Option** | **Behavior** |
| **Component contains data** | Hide component if it has no data |
| **User's current role is** | Show only to selected roles |
| **Dynamic text does not evaluate to "hidden"** | Conditional visibility based on formula |

**Parent topic:** [Report Permissions](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
