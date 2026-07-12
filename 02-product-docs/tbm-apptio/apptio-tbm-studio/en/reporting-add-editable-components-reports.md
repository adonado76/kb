---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Add Editable Components to Reports"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Advanced Reporting"
  - "Add Editable Components to Reports"
source_path: "SSWRJM/studio/new-uc/howtoguides/create-reports/add-et-rep.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Add Editable Components to Reports

Objective: Embed editable tables in reports to enable end-user data entry workflows, allowing users to input or modify data directly from the reporting surface without requiring TBM Studio access.

When to use: When users need to enter or update data such as labor mappings, cost center attributes, budget entries, or variance explanations.

Time estimate: 15-25 minutes

## Understanding Editable Components

Editable tables in reports create a data entry layer that feeds into TBM Studio's transform tables and ultimately the cost model. They support scenarios such as:

- Labor mappings (mapping personnel to solutions, categories, or cost pools)
- Cost center attributes (adding metadata or classifications)
- Budget variance explanations (capturing commentary from cost center owners)
- Direct data corrections (allowing controlled edits to source data)

Prerequisites

- An existing editable table created in Data Studio (see Section 3.1.3 for creating editable tables)
- A report to add the editable component to
- Appropriate permissions (users need Dev access and Stage access to publish changes)

## Steps

Step 1: Add the editable table component

1. Open the target report in Report Studio and check it out.
1. On the Report tab, click Editable Table. An editable table component is added to the report, and the Component Configuration panel opens.
1. From the table selector dropdown at the top of the Component Configuration panel, select the editable table you want to display.

Step 2: Configure visible columns

1. Drag columns from the Project Explorer into the Included Columns area of the Component Configuration panel.
1. Arrange columns in the desired display order by dragging them up or down in the list.
1. Columns not included remain available in the editable table but are hidden from the report view.

Step 3: Configure editable behavior

1. Right-click the editable table component and select Properties.
1. On the Data Edit tab, configure: Enable adding rows: Allows users to add new rows (for blank editable tables) Enable deleting rows: Allows users to delete rows (only for blank editable tables) Enable duplicate row: Allows users to duplicate existing rows Enable carry forward: Automatically copies numeric values forward when tabbing between cells
1. Click OK to save the configuration.

Step 4: Add upload capability (optional)

To allow users to upload data via Excel:

1. Scroll to the bottom of the editable table component in the report.
1. The Open In Excel and Click or Drag File options appear automatically for editable table components.
1. Users can download current data to Excel, make changes, and upload the modified file.

Step 5: Save and check in

1. Position and resize the editable table component as needed.
1. Save and check in the report.

## User Workflow for Data Entry

Once you've configured an editable component, end users follow this workflow:

1. Navigate to the report containing the editable table.
1. Click in cells to edit values directly. Dropdown columns display allowed values.
1. Click Save to save edits locally (edits are stored client-side until published).
1. Click Publish at the bottom of the report to commit changes to the underlying transform table.
1. Enter a description and click Check In to complete the publish.

## Special Columns for Audit Tracking

Editable tables include special audit columns you can show or hide:

- .pk column: The primary key column. Show this to support consistent copy/paste operations and sorting.
- .Username column: Shows who made the last change to each row.
- .EditDate column: Shows when the last change was made to each row.

To show these columns: hover over the column header, right-click, and select Show from the menu.

## Concurrency and Locking

Editable tables enforce cell-level locking to prevent conflicts:

- When a user begins editing a cell, that cell is locked for other users
- The lock persists until the user saves or cancels
- Other users can edit different cells in the same table simultaneously

## Expected Results

- Editable cells are highlighted when users click in them
- Dropdown columns display configured allowed values
- Validation errors display as warnings or errors near affected cells
- Save and Publish buttons appear at the bottom of the component

## Common Pitfalls

- Users cannot add/delete rows: Only blank editable tables support adding and deleting rows. Enriched editable tables (derived from transform tables) do not allow row deletion because the rows come from the source transform.
- Changes not appearing in model: Users must Publish changes, not just Save. Saved changes are client-side only until published.
- Validation errors blocking publish: Invalid rows cannot be published. Users must fix validation errors before the publish can complete.

## Related Tasks

- Create editable tables (Section 3.1.3)
- Configure dropdown lists for editable columns (Section 3.1.3)
- Set up recurring publish schedules (Section 6.1)
- Configure Row-Level Security (Section 4.4)
