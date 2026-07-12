---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Drill-Through Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Navigation"
source_path: "studio/new-uc/reference/report-studio-reference/drill-through-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Drill-Through Configuration

Drill-through navigation is a core feature in TBM Studio reporting, enabling users to explore
data at increasing levels of detail. Properly configured drill-through paths help users understand
cost flows, investigate variances, and trace transactions to their source.

**Drill-Through from Table Rows**

Configure table columns to act as drill-through links. When a user clicks a value in the
configured column, they navigate to the target report with appropriate filters applied.

**Configuration Steps**

1. Select the column you want to enable as a drill-through link
2. Open the Ad Hoc tab and click Drill in the Navigation section
3. Check Enable Navigation to activate links
4. Select the target report in the Navigate To field
5. Configure context passing options to control what filters are applied

**Drill-Through from Chart Elements**

Charts can also provide drill-through navigation. When enabled, clicking a bar, slice, or other
chart element navigates to the target report filtered by the selected data point.

**Important:** In charts, navigation must be keyed to the value column, not the label column.
Configure drill-through on the numeric measure, not the dimension labels.

**Context Passing Options**

Control what data context is passed to the target report:

- **Filter on all Rows columns:** Passes all row dimensions as filters
- **Filter only on Grouped columns:** Passes only grouped dimensions
- **Filter only on currently selected column:** Passes only the clicked column value
- **Filter on applied slicer selections:** Includes current slicer filter values
- **Include current report's filters:** Passes predefined report filters

Tip: For drill-through to work correctly, the data in the source and target reports must
be linked through the inference engine. Ensure both reports use tables with proper relationships
defined in the model.

**Multi-Level Drill-Through**

Create cascading drill-through paths that allow users to progressively explore data across
multiple levels. For example, a user might drill from a summary report to business unit details,
then to cost center details, and finally to transaction-level data.

**Example: Three-Level Drill Path**

**Level 1 - Summary Report:**

- Business Unit Costs table with drill-through on Business Unit column
- Configure Filter on selected row with Filter on all Rows columns

**Level 2 - Business Unit Detail Report:**

- Receives filter from Level 1, showing only selected business unit
- Cost Centers table with drill-through to Level 3

**Level 3 - Cost Center Detail Report:**

- Shows transaction-level detail for the selected cost center

**Parent topic:** [Report Components: Navigation](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
