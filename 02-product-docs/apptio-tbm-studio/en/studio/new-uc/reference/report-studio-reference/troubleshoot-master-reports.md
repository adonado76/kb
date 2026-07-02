---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Troubleshooting Master Reports"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
source_path: "studio/new-uc/reference/report-studio-reference/troubleshoot-master-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Troubleshooting Master Reports

**Common Issues and Solutions**

|  |  |  |
| --- | --- | --- |
| **Issue** | **Possible Cause** | **Solution** |
| Master not appearing in drop-down | Report not saved or checked in after enabling Master Report option | Save and check in the master report; wait for calculation to complete |
| Components placed inside master group box not grouped | Expected behavior - group boxes lose grouping functionality in child reports | Use group boxes in masters only for visual structure; add functional groups in child reports |
| Child content displays on all tabs | Components placed on top of tabbed component in child report | Add tab content in master only; avoid placing components on tabs in child reports |
| Cannot delete master report | Attempting to delete a standard (OOTB) master | Standard masters cannot be deleted; use Save As to create a custom version you can modify or delete |
| Master button navigates to wrong report | Wiki text button without Data URL uses current report context | Specify explicit Data URL for navigation buttons in master reports |

**Parent topic:** [Master Reports](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
