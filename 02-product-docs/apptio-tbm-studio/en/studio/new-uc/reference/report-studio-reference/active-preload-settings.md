---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Active and Preload Settings"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Properties"
source_path: "studio/new-uc/reference/report-studio-reference/active-preload-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Active and Preload Settings

These settings control whether a report participates in system calculations and whether it's
pre-computed for faster user access.

|  |  |
| --- | --- |
| **Setting** | **Description and Impact** |
| Active | When checked, the report is included in system calculations and its data is preloaded. When unchecked, the report is disabled and not calculated. Use this to temporarily disable a report without deleting it, or to prevent incomplete reports from being calculated. |
| Preload | Reports with the Active option enabled have their data pre-calculated during builds. If your domain is configured to require preloading, users cannot view reports that have not been preloaded. Preloading improves user experience for data-intensive reports by ensuring calculations are complete before users access the report. |

**Location:** Report tab > Advanced group > Active checkbox

**Parent topic:** [Report Properties](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
