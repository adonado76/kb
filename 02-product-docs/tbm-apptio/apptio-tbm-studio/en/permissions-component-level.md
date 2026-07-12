---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Component-Level Permissions"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
  - "Component-Level Permissions"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/component-level-permission.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Component-Level Permissions

Hiding Components by Role

Individual report components can be hidden from specific roles while remaining visible to others. This allows creating multi-purpose reports that display different information based on user role.

Configuring Component Visibility:

1. Select the component in the report
1. On the Report tab, in the Advanced group, click Visibility
1. Select User's current role is option
1. Choose the roles that should see the component
1. Save and check in the report

Visibility Options

The Report Component Visibility dialog offers multiple visibility conditions:

| Option | Behavior |
| --- | --- |
| Option | Behavior |
| Component contains data | Hide component if it has no data |
| User's current role is | Show only to selected roles |
| Dynamic text does not evaluate to "hidden" | Conditional visibility based on formula |
