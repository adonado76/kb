---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Create Drill-Through Reports"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Advanced Reporting"
  - "Create Drill-Through Reports"
source_path: "SSWRJM/studio/new-uc/howtoguides/create-reports/drill-thru-reports.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Create Drill-Through Reports

Objective: Enable users to click on summary data and navigate to detailed reports, providing progressive data exploration from high-level views to granular detail.

When to use: When users need to explore data hierarchies interactively, such as clicking a business unit to see its applications, or clicking a cost category to see individual line items.

Time estimate: 20-30 minutes per drill-through configuration

## Understanding Drill-Through Navigation

Drill-through reports allow users to click values in tables or elements in charts to navigate to more detailed reports. When configured, linked values appear as blue text in tables. Charts can also link to reports when users click on pie slices or bar segments.

TBM Studio provides several drill-through patterns:

- Grouped data drilling: When you use the GROUPBY function on a table, grouped entries automatically become clickable links that reveal underlying detail.
- Configured navigation links: You can explicitly configure table columns or chart elements to navigate to specific reports with optional filtering.
- Button navigation: Use button components to provide explicit navigation between reports.
- Coded links: Use Wiki-style syntax in HTML text boxes for custom navigation with dynamic text.

Prerequisites

- Source report with summary data (the report users will start from)
- Target report with detail data (the report users will navigate to)
- Data relationships established through the Apptio Inference Engine
- Ad hoc tables or charts (navigation only works with Ad Hoc components, not legacy components)

## Method 1: Configure Navigation Links on Table Columns

This method creates clickable links in table columns that navigate to a target report, optionally passing filter context.

1. Open the source report and check it out.
1. Select the table column you want to make clickable (for example, Business Unit).
1. On the Ad Hoc tab, click Drill in the Navigation section. The navigation properties panel appears.
1. Check Enable Navigation to activate links for this column.
1. In the Navigate To field, select the target report from the dropdown. You can also click New Report to create the target report.
1. Configure context options to control what information passes to the target report: Filter on selected row: Filters the target report by the value the user clicked Filter on applied slicer selections: Carries any active slicer filters to the target report Include current report's filters: Passes filters defined in the Component Configuration dialog Add currently selected column: Adds the clicked column to the target report if not already present
1. (Optional) Check Open as Modal to display the target report as a popup instead of navigating to a new browser page.
1. Save and check in the report.

## Method 2: Configure Chart Navigation

Enable users to click on chart elements (pie slices, bar segments) to navigate to detailed reports.

1. Select your chart and switch to the chart configuration tab.
1. In the Navigate (Drill) section, check Enable Navigation. This makes chart elements clickable.
1. (Optional) Check Use Per Metric Drills to enable clicking on the numeric values displayed on bars or pie slices, not just the segments themselves.
1. In the Navigate field, enter the name of the target report. The report must be a child of the current report.
1. Save and check in the report.

## Method 3: Button Navigation

Add explicit navigation buttons that take users to specific reports.

1. On the Report tab, click Button. A button component is added to the report.
1. Click the small triangle in the button's upper-left corner and select Properties.
1. On the Button tab, enter descriptive text in the Button Text field (for example, "View Application Details").
1. On the Actions tab, configure the navigation: Navigate: Enter a Wiki-style link to the target report Change Date: Optionally change the time period when navigating Back Button: Check this to create a "Back" button that returns to the previous report
1. Click OK to save the button configuration.

## Wiki-Style Link Syntax

Use this syntax in HTML text boxes or button navigation fields:

[[report|display-text|tooltip]]

| Syntax | Description |
| --- | --- |
| Syntax | Description |
| [[ReportName]] | Link to a child report with the report name as link text |
| [[ReportName|Click Here]] | Link with custom display text |
| [[..]] | Navigate up one level in the report hierarchy |
| [[/]] | Navigate to the default report for the project |
| [[//ProjectName/Report]] | Link to a report in a different project |
| [[dialog:report:ReportName]] | Open the report as a modal popup |
| [[tab:TabName/ReportName]] | Link to a report on a specific tab |

## Common Drill-Through Patterns

Pattern 1: Business Unit to Applications

A cost summary report shows costs by business unit. Users click a business unit to see all applications owned by that unit. Configure the Business Unit column with Enable Navigation checked and Filter on selected row selected. This passes the selected business unit as a filter to the Applications report.

Pattern 2: Category to Line Items

A chart shows cost by category (pie chart). Users click a pie slice to see the individual line items that make up that category. Enable navigation on the chart and specify the Line Items report as the target.

Pattern 3: Multi-Level Hierarchy

Report A shows Business Units. Clicking a unit navigates to Report B showing that unit's cost centers. Clicking a cost center navigates to Report C showing the cost center's applications. Configure each level's navigation to filter on the selected row and include applied slicer selections to maintain context through the drill path.

## Expected Results

- Linked values in tables appear as blue underlined text
- Clicking a link navigates to the target report
- Filter context is passed based on your configuration
- Breadcrumbs appear showing the navigation path

## Common Pitfalls

- Navigation not working: Verify you're using ad hoc tables/charts, not legacy components. Navigation only works with Ad Hoc Component Configuration components.
- Target report shows no data: Ensure data relationships are established through the Apptio Inference Engine. The source and target data must be linked.
- Performance issues: Be cautious when linking to reports that require significant calculation time. This can impact system performance.

## Related Tasks

- Create report collections
- Add slicers and filters
- Configure component visibility
