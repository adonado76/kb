---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Getting Help"
breadcrumb:
  - "TBM Studio"
  - "Troubleshooting and Support"
source_path: "studio/new-uc/ts-support/get-help.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Getting Help

When self-service troubleshooting doesn't resolve your issue, use these resources to
get additional assistance.

## Internal Resources

Before contacting support, check the Recommendations panel for automated suggestions. Many
issues can be fixed automatically with the guided troubleshooting wizards. Use the Report
Search feature to find metrics, labels, dimensions, or components across the project.

## Contacting Support

**When to Contact Support:**

- Self-service troubleshooting hasn't resolved the issue
- You need to recover legacy configurations
- System-level issues are suspected
- You need assistance with rollback or complex recovery operations

**Preparing for Support Contact - Gather this information:**

- Exact text of any error messages
- Steps to reproduce the issue
- Environment (Development, Staging, or Production)
- When the issue first appeared
- Any configuration or data changes made recently
- Calc Explorer data (if performance-related)
- Screenshots showing the issue

## Escalation Path

|  |  |
| --- | --- |
| **Level** | **Actions** |
| **Level 1: Self-Service** | Use Recommendations panel, review Errors panel, check Calc Explorer, consult documentation |
| **Level 2: Team** | Coordinate with other TBM Studio users, review with internal administrator, check for known issues |
| **Level 3: Support** | Submit support ticket with detailed information, include diagnostic data from Calc Explorer |
| **Level 4: CSM** | For complex or recurring issues, strategic guidance on model optimization, feature requests |

## 7.4.4 Rollback a Configuration

When something goes wrong and you need to restore a previous configuration, use the
rollback feature. Consider rollback when something checked in is causing performance
problems, something was deployed prematurely, or configuration changes have broken
functionality.

Attention: **Important Considerations Before Rolling Back**

- Any running calculations will be stopped
- All check-ins after the rollback point will be discarded
- A full-stage calculation will need to run
- If other project calculations are running, rollback may be queued

**Rollback Procedure:**

- Select the document in Project Explorer
- On the Build tab, select Check In History
- Right-click on the check-in you want to rollback to and select Rollback To
- Enter a descriptive reason for the rollback
- Click Rollback Check In and monitor build status
- When complete, refresh workspaces via Home > Update Workspace
