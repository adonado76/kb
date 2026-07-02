---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Troubleshooting Permission Issues"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Permissions"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshoot-permission-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Troubleshooting Permission Issues

**Common Permission Problems**

|  |  |  |
| --- | --- | --- |
| **Problem** | **Likely Cause** | **Solution** |
| Report not visible | Wrong role assignment | Add role to report permissions |
| Empty report components | RLS filtering | Add user to RLS mapping tables |
| Cannot check out | Already checked out | Wait for other user or contact admin |
| Components missing | Component visibility | Verify role is included in visibility settings |
| Cannot export | Export permissions | Check role-level export permissions |
| Cannot subscribe | Missing permission | Grant EmailSubscriptionsCreate permission |

**Permission Verification Checklist**

Before releasing reports to production, verify:

- Report permissions configured for appropriate roles
- RLS mapping tables include all necessary users
- Component visibility settings tested for each role
- Report appears in correct collection(s)
- Report is active and calculating
- Email subscriptions configured correctly (if applicable)
- Export and print functionality tested

**Parent topic:** [Report Permissions](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
