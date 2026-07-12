---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Report Properties"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
source_path: "studio/new-uc/reference/report-studio-reference/report-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Report Properties

Report properties control the behavior, appearance, and accessibility of reports across TBM
Studio. These settings affect how data is displayed, who can access reports, how time periods are
handled, and how reports appear when printed or exported. This reference provides comprehensive
documentation for all report-level configuration options.

## Report Metadata

Report metadata defines the basic identification and organizational properties of a report. These
settings are configured when creating a report and can be modified afterward.

**Basic Properties**

|  |  |
| --- | --- |
| **Property** | **Description** |
| Report Name | The display name of the report. Appears in Project Explorer, report tabs, and navigation. Names should be descriptive and follow organizational naming conventions. |
| Description | Optional text describing the report's purpose and contents. Displayed as a tooltip when users hover over the report name. Use this field to explain what data the report contains and its intended use. |
| Report Collection | The organizational container for the report. Report collections group related reports and can have their own permission settings that cascade to saved reports. |
| Viewable By | Controls which roles can view the report. Options include 'Everyone' or specific roles. This setting determines initial access when the report is created. |
| Create as Top Level | When saving a report created through drill-down navigation, this option places the report at the top of the reporting hierarchy rather than nested under its parent. |

**Screen Size Configuration**

When creating a report, you choose the screen size that determines the report's default layout
width:

|  |  |  |
| --- | --- | --- |
| **Option** | **Width** | **Best For** |
| Standard | 1024 pixels | Traditional monitors, tablet displays, reports with fewer wide tables |
| Widescreen | 1440 pixels | Modern widescreen monitors, dashboards with multiple columns, complex layouts |

Note: *The screen size affects the default editing canvas. Components can extend beyond these
boundaries but may require horizontal scrolling on smaller displays.*

- **[Time Period Configuration](../../../../studio/new-uc/reference/report-studio-reference/timeperiod-config.html)**
- **[Display Settings](../../../../studio/new-uc/reference/report-studio-reference/display-settings.html)**
- **[Active and Preload Settings](../../../../studio/new-uc/reference/report-studio-reference/active-preload-settings.html)**
- **[Master Report Setting](../../../../studio/new-uc/reference/report-studio-reference/master-report-settings.html)**
- **[Security Settings](../../../../studio/new-uc/reference/report-studio-reference/security-settings.html)**
- **[Print and Export Settings](../../../../studio/new-uc/reference/report-studio-reference/print-export-settings.html)**
- **[Email Subscription Settings](../../../../studio/new-uc/reference/report-studio-reference/email-sub-settings.html)**
- **[Breakdown and Advanced Display Options](../../../../studio/new-uc/reference/report-studio-reference/breakdown-advanced-display.html)**
- **[Localization Settings](../../../../studio/new-uc/reference/report-studio-reference/localization-settings.html)**
