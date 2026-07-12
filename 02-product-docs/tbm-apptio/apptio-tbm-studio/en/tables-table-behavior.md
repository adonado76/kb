---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Table Behavior"
breadcrumb:
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Tables"
  - "Table Behavior"
source_path: "SSWRJM/studio/new-uc/reference/report-studio-reference/table-behavior.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Table Behavior

Freezing Columns

Freeze columns to keep them visible while scrolling horizontally. Frozen columns move to the far-left edge.

To freeze a column:

- Select the column and click the Freeze icon on the Data tab, OR
- Right-click the column header > Formatting > Freeze Column.

To unfreeze: Right-click the column header > Formatting > Unfreeze Column.

Pagination

Tables with many rows display a paging bar for navigation. Configure pagination using Maximum Rows in the Properties dialog.

| Option | Behavior |
| --- | --- |
| Option | Behavior |
| Maximum Rows = 20 | Shows 20 rows per page with paging bar. |
| Hide Paging Bar = Yes | Shows only the first Maximum Rows with no navigation. |
| Use case | Top 10 lists, summary tables where scrolling is undesirable. |

Drill-Through Configuration

Enable navigation from table values to detailed reports. Links appear as blue text.

To configure drill-through:

1. Select a column in the table.
1. Click the Ad Hoc tab and click Drill in the Navigation section.
1. Configure navigation properties.

| Property | Description |
| --- | --- |
| Property | Description |
| Enable Navigation | Makes values in the column active as links. |
| Open as Modal | Opens the target report as a pop-up. User closes to return. |
| Target Report | The report to navigate to when clicked. |
| Context Includes | What data context to pass: Row filter, Column values, Selection. |

Note: Report links only work with object-based tables. Transform tables do not support drill-through navigation.

Export Options

Tables can be exported as part of reports in multiple formats.

| Format | Details |
| --- | --- |
| Format | Details |
| PDF | Export via Home tab > Export > PDF. Use Print Layout mode for custom layouts. Multi-page tables supported with Print All Pages option. |
| Excel | Columns maintain report configuration order. Unconfigured columns appended. Tree tables export as flat tables with indentation. |
| Email | Reports can be emailed as PDF attachments or links. Configure via Email Subscription. |

Deferred Refresh

For complex reports with many interactive controls, configure refresh behavior to avoid excessive screen updates.

| Option | Description |
| --- | --- |
| Option | Description |
| Refresh Delay: 3s | System waits 3 seconds before refreshing after user interaction. Default setting. |
| Manual Refresh | User must click Refresh to update. Best for reports with numerous slicers and pickers. |

Configure globally: Project tab > Project Settings > Deferred Refresh. Override per report: Checkout report > Report tab > Refresh settings.
