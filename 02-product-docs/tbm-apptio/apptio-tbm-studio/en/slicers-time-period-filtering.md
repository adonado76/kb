---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Time Period Filtering"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Filters and Slicers"
  - "Time Period Filtering"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/time-period-filter.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Time Period Filtering

Date Picker Functionality

While TBM Studio doesn't have a dedicated date picker component, you can create date selection functionality using Column Pickers or Buttons.

Option 1: Column Picker as Date Picker

1. Add a Column Picker to the report
1. Configure with time-based values from the Time perspective
1. Set to Single Selection mode

Users can select from options like Current Month, Current Quarter, Current Half, or Year To Date.

Data Time Period Configuration

For charts and tables, the Data Time Period setting controls which period's data displays:

| Setting | Behavior |
| --- | --- |
| Setting | Behavior |
| Current Project Date (default) | Displays data for date shown in report header date picker |
| Start of Current Fiscal Year | Locks to first period of current fiscal year |
| Start of Current Fiscal Quarter | Locks to first period of current quarter |
| Specific date | Locks to an explicitly specified period |
