---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Report Canvas"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Working with Reports"
  - "Report Canvas"
source_path: "SSWRJM/studio/report-studio/create-first/canvas-layout.html"
images:
  - "03-media/apptio-tbm-studio/canvas-layout.png"
  - "03-media/apptio-tbm-studio/canvas-format-panel.png"
  - "03-media/apptio-tbm-studio/rs-filemenu.png"
  - "03-media/apptio-tbm-studio/rs-editmenu.png"
  - "03-media/apptio-tbm-studio/rs-viewmenu.png"
  - "03-media/apptio-tbm-studio/rs-arrangemenu.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Report Canvas

*The Report Canvas is where admins build and edit reports by adding components, configuring data, and arranging visualizations.*

## Canvas Layout

- Report Canvas Area – The main workspace where components and visualizations are placed and arranged.
- Top toolbar – Provides actions such as align, group, delete, undo and redo. Houses components and visualizations you can add.
- Layer Panel (left) : Shows the hierarchy of components in your report. From here, you can copy, paste, reorder, delete, or change group membership.
- Dimensions Explorer (right) : Lists Tables, Editable Tables, Metrics and Time. Use this to drag and drop dimensions into component configurations.

## Canvas Format Panel

The Canvas format panel lets you control the overall appearance of the report canvas. These settings apply to the entire report layout.

- Canvas Size Choose a predefined size or set custom dimensions Canvas size determines how content is laid out and how the report appears when exported to PDF.
- Canvas Background color Use Background color to set the background color of the report canvas. Applied consistently across the entire report

## Canvas Menu

The report canvas includes menus that provide access to common actions while creating or editing reports.

The File Menu contains report-level actions to manage report versions and save changes.

- Check In – Saves your changes and makes the report available to other users.
- Check Out – Locks the report for editing so you can make changes without conflicts.
- Revert Changes – Discards unsaved changes and restores the report to the last checked-in version.
- Save – Manually saves the current state of the report.
- Save As – Creates a new report by saving a copy of the current report under a different name.

The Edit menu provides actions for making changes to content on the report canvas.

- Undo – Reverses the most recent change.
- Redo – Reapplies the last undone change.
- Copy – Copies the selected component or visualization.
- Paste – Pastes the copied component or visualization on the canvas.

The View menu controls how the report canvas is displayed and how elements are positioned while designing a report.

- Actual size – Displays the canvas at its original scale.
- Fit to page – Scales the canvas so the entire page fits within the available view.
- Fit to width – Scales the canvas to fit the width of the workspace.
- Show grid – Displays a grid on the canvas to help align components.
- Show rulers – Displays horizontal and vertical rulers for precise positioning.
- Snap to grid – Automatically aligns components to the grid when moving or resizing them.
- Show Layers – Displays the layer panel to manage the stacking order of components.

The Arrange menu helps organize and position components and visualizations on the report canvas.

- Align – Aligns selected components along their edges.
- Distribute – Evenly spaces selected components horizontally (Shift+Alt+H) or vertically (Shift+Alt+V).
- Bring to Front – Moves the selected component to the top of the layering order.
- Send to Back – Moves the selected component to the bottom of the layering order.
- Bring forward – Moves the selected component forward one step
- Send backward - Moves the selected component backward one step

## Widget Header Overflow menu

Each widget includes an overflow menu in the header that provides quick actions to refresh and inspect data, convert to compatible visualizations, delete and other commonly used operations.

Update data

- Triggers a re-fetch of the latest data for the widget.
- Useful when underlying data has changed and you want to see updated results immediately.
- Does not require a full report reload.
- Use it after data updates, configuration changes, or if the widget appears out of sync.

Show Full Data Path

- Opens a modal showing the full data hierarchy and references.
- Helps understand how the widget data is sourced and processed.
- Useful for debugging, validation, and support investigations.
- Use it to trace data lineage or verify the data source powering the widget.

Open in /data

- Navigates to the /data URL associated with the widget.
- Shows the raw or debug-level data used by the component.
- Intended primarily for troubleshooting.
- Use it for deeper data inspection or debugging.
