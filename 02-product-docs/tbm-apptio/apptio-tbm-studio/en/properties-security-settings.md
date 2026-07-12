---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Security Settings"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Properties"
  - "Security Settings"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/security-settings.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Security Settings

Report security settings control which users and roles can view and interact with reports. Permissions can be configured at the report collection level and inherited by individual reports, or set specifically for each report.

Report Permissions

To configure report permissions:

1. Check out the report
1. Navigate to Report tab > Permissions (or Project tab > Advanced group > Permissions)
1. Select the roles that should have access
1. Click OK to apply

Permission options:

| Option | Description |
| --- | --- |
| Option | Description |
| Everyone | All users with access to the project can view the report. This is the most permissive setting. |
| Specific Roles | Only users assigned to the selected roles can view the report. Multiple roles can be selected. |

Report Collection Permissions

Permissions set at the report collection level apply to all reports within the collection unless overridden at the individual report level. This provides efficient permission management for groups of related reports.

Component Visibility

Individual components within a report can have visibility rules that control when and to whom they appear:

| Visibility Rule | Behavior |
| --- | --- |
| Visibility Rule | Behavior |
| Component contains data | Hides the component if it does not contain or calculate data |
| User's current role is | Shows the component only to users with specified roles |
| Dynamic text evaluates to "hidden" | Hides the component based on a formula or data condition |

To set component visibility: Select the component, then navigate to Report tab > Advanced group > Visibility
