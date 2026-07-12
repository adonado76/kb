---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Display Settings"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Properties"
  - "Display Settings"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/display-settings.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Display Settings

Display settings control the visual presentation and refresh behavior of reports.

Deferred Refresh

Deferred refresh controls how quickly reports are updated when users interact with filters, slicers, and pickers. This setting helps manage performance for complex reports.

| Option | Behavior |
| --- | --- |
| Option | Behavior |
| Refresh Delay: 3s | The system waits 3 seconds after a filter selection before refreshing the report. Allows users to make multiple selections before the refresh occurs. This is the default setting. |
| Manual Refresh | Report does not refresh until the user explicitly clicks Refresh. Recommended for large reports with numerous slicers and pickers where each refresh is time-consuming. |

Project-level default: Navigate to Project tab > Project Settings > Deferred Refresh to set the default for all reports.

Report-level override: Check out the report, then modify the refresh setting on the Report tab.

Color Palette

Reports can use custom color palettes for consistent branding across charts and visualizations. Color palettes are defined at the environment level by administrators and can be applied at both the report collection and individual report level.

Color palette hierarchy:

1. Report-level palette (if set) takes precedence
1. Report collection palette applies if no report-level override
1. Default Apptio colors apply if no custom palette is set

To apply a color palette:

1. Check out the report
1. Navigate to Report tab > Color Palette
1. Select from Custom palettes or Preset options
