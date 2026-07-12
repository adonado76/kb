---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Cost Sharing for Reports and Dashboards"
breadcrumb:
  - "Setup"
  - "Sharing Cost in Cloudability"
  - "Cost Sharing for Reports and Dashboards"
source_path: "SSVCLNQ/product/cost-sharing-for-reports-and-dashboards.html"
images:
  - "03-media/apptio-cloudability-standard/costsharing14.png"
  - "03-media/apptio-cloudability-standard/costsharing15.png"
  - "03-media/apptio-cloudability-standard/costsharing16.png"
  - "03-media/apptio-cloudability-standard/costsharing1.png"
  - "03-media/apptio-cloudability-standard/costsharing2.png"
  - "03-media/apptio-cloudability-standard/costsharing3.png"
  - "03-media/apptio-cloudability-standard/costsharing4.png"
  - "03-media/apptio-cloudability-standard/costsharing5.png"
  - "03-media/apptio-cloudability-standard/costsharing6.png"
  - "03-media/apptio-cloudability-standard/costsharing7.png"
  - "03-media/apptio-cloudability-standard/costsharing8.png"
  - "03-media/apptio-cloudability-standard/costsharing10.png"
  - "03-media/apptio-cloudability-standard/costsharing11.png"
  - "03-media/apptio-cloudability-standard/costsharing12.png"
  - "03-media/apptio-cloudability-standard/costsharing13.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Cost Sharing for Reports and Dashboards

## Overview

A new Cost Sharing toggle in the Cloudability Reports and Dashboard Widget Editor lets users generate data visualizations from report data with allocated (shared) costs applied. When enabled on a report or widget, results reflect allocated costs according to rules configured in Cloudability → Cost Sharing .

1. Open any report or widget editor.
1. Look for the Cost Sharing button in the header section.
1. Toggle the button to see your data with allocated costs.
1. Explore the new Cost Type and Allocation Source measures.
1. Save your widget and watch for the allocation badge on the title.

- Users can toggle Cost Sharing on/off per report or supporting widget.
- Previewing or saving a report or widget shows how data changes with Cost Sharing applied.
- Additional measures are now available which are only supported when Cost Sharing is enabled.

- Allocation rules are created and managed in the Cost Sharing feature.
- Rules apply only to Business Dimensions . (Non-business dimensions are not allocation targets.)

- Each supported widget type has a Cost Sharing toggle (Applied / Not Applied) in the header portion of the Create/Edit report and widget drawer.
- Toggling updates the query parameters used for Widget preview and save.
- The widget title displays an allocation badge when Cost Sharing is applied, so users can see at a glance that allocation rules affected the result set.
- Business Dimensions that have allocations applied to them show an allocation icon in all dimension selection components.

Measures Available with Cost Sharing

When Cost Sharing is Applied , the following new measures are now supported:

- Cost Type Indicates whether a dimension value has Direct or Shared cost.
- Allocation Source Breaks down where shared costs are attributed across business dimensions.

Dimension & Metric Support

- Some dimensions/metrics are supported only when Cost Sharing is Applied .
- Conversely, others are not supported in that state.

Behavior in the editor:

- Supported items remain selectable and usable.
- Unsupported items are: Marked with an error icon if previously selected and the user toggles Cost Sharing into a state where they’re invalid. Disabled in selectors to prevent new selection.

Preview/Save Request Sanitization

To prevent backend errors when Cost Sharing is toggled:

- On Preview or Save , any unsupported dimensions/metrics/filters (given the current toggle state) are removed from the request .
- This avoids failed requests due to invalid combinations and ensures the visualization renders successfully with supported fields.
- A user is notified on creation of Report or Dashboard Widget of the unsupported measures that have been removed in the process of saving.

Report Creation from Chart Widget

- A Chart Widget tooltip can navigate a user to a Report. In Widget Preview, we ensure only supported measures are included in the Report generated from Chart Widget data.

Filters

- Filters cannot target unsupported dimensions.
- If a user previously set such a filter and then toggles to an unsupported state: The filter shows an error icon in the editor. Unselected options are disabled. The filter is omitted from Preview/Save requests.

Validation & Notifications

- Reports require at least one dimension and one metric .
- If toggling Cost Sharing makes the configuration invalid (e.g., the sole dimension becomes unsupported), the user cannot produce a valid report. The UI shows a toast error notification explaining the configuration is unsupported with the current Cost Sharing state.

If a user is attempting to use the new ‘Allocation Source’ measure, the supported config for this request is to include with ‘Allocation Source’ at least one Business Dimension, and one other dimension.

- The UI shows a toast error notification explaining the configuration is unsupported if these conditions are not met.

State Persistence Rules

- While editing, the UI retains unsupported selections visually (marked with errors) so users can quickly toggle Cost Sharing on/off and compare results with the same intended configuration .
- On Save : Unsupported items are not persisted to the widget definition (because such a configuration cannot produce a valid report). Users keep the ability to toggle and preview while editing, but saved widgets never include invalid fields.

Cost Sharing in Reports

- All functionality is consistent across CLDY Reports and Dashboards. Widgets can be configured with Cost Sharing applied directly from a Report and copied to a user dashboard.
- Reports and Widgets can be exported and shared using existing Report Export functionality.
- A Report with Cost Sharing applied can also be subscribed to via the Report subscription drawer.
- A Report can be copied to Dashboard, persisting the Shared Cost value applied in the created widget.

Summary of Expected User Experience

1. User opens a widget, chooses dimensions/metrics, and optionally enables Cost Sharing .
1. Editor shows: Allocation icons on applicable Business Dimensions. Error icons on any fields that become unsupported when toggling the Cost Sharing state.
1. On Preview/Save: Unsupported fields/filters are automatically removed from the request. If removal makes the configuration invalid, an error toast informs the user.
1. After saving: The widget title shows an allocation badge if Cost Sharing is applied. The saved widget contains only supported fields for its Cost Sharing state.

Example Widgets:

1. Table showing the Business Dimension w/ allocated rule applied and the Allocation Category of this metric’s values:

Stacked Bar Chart showing the Cost Type of the values of a Business Dimension w/ allocated rule applied, stacked, showing cost(total) and cost(amortized) metrics:

Comparison of two Pie Charts rending the same Business Dimension, showing how the cost(total) metric varies when shared cost is applied or not applied:

![costsharing13](../images/costsharing13.png)
