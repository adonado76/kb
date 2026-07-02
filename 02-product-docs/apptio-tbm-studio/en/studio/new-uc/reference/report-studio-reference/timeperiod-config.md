---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Time Period Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Properties"
source_path: "studio/new-uc/reference/report-studio-reference/timeperiod-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Time Period Configuration

Time period settings determine which data periods users see when viewing reports. These settings
interact with project-level time configuration and affect data displayed in tables, charts, and
KPIs.

**Project-Level Time Inheritance**

Reports inherit time period settings from the project configuration. The following project
settings affect all reports:

|  |  |
| --- | --- |
| **Project Setting** | **Effect on Reports** |
| Default Period | The time period shown to users when they first open a report. Typically set to the most recently closed fiscal period. Users can override this selection using the time selector. |
| Fiscal Year Definition | Determines fiscal calendar structure (e.g., January-December, October-September, Federal). Affects how periods are labeled and grouped in trend reports. |
| Project Start/End Period | Limits the range of available time periods. Data outside this range is not calculated, which improves performance for large models. |
| Closed Periods | Periods marked as closed remain viewable in reports but cannot have data modified. Essential for financial governance and audit trails. |

**To configure project time settings:** Navigate to Project tab > Time Settings.

**Report-Specific Date Restrictions**

Individual reports can override the project default period and restrict when they are visible.

**Earliest Applicable Date**

Restricts report visibility to dates on or after a specified period. This feature is useful for:

- Hiding reports still under development
- Releasing reports aligned with business cycles
- Preventing access to reports before required data is available

**To set the earliest applicable date:**

1. Check out the report
2. On the Report tab, click Start Date
3. In the Configure Earliest Applicable Date dialog, select a date
4. Save and check in the report

When users attempt to view the report before the earliest applicable date, they see a message
explaining that the report is not yet available, with a link to view the report at its first
viewable period.

**Component-Level Time Period**

Individual report components (tables and charts) can have their time period locked independently
of the report's current period. This is configured through the Data Time Period field in each
component's Advanced properties.

Use case examples:

- Display prior year comparison data alongside current period
- Show budget from a specific locked period
- Create trend charts with fixed start and end dates

**Parent topic:** [Report Properties](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
