---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Quick Pivot component"
breadcrumb: []
source_path: "reports/quick-pivot.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Quick Pivot component

Applies to: TBM Studio 12.0 and later

The Quick Pivot component groups table entries by values in a selected column.

When the user selects a column from the Quick Pivot drop-down menu, that column becomes the first
in the table.

![](../../resources/images/studio_images/quickpivot.png)

The rows are ordered by the values in the selected column.

![](../../resources/images/studio_images/quickpivot1.png)

## Create a Quick Pivot

1. Open the report with the table you want to pivot.
2. On the Report tab, click QuickPivot. The application adds a QuickPivot
   object to the report and displays the QuickPivot Configuration pane.
3. Using the field at the top of the pane, select the table you want to pivot.
4. From the Project Explorer, drag one or more fields into the Pivots area of the
   QuickPivot Configuration panel.The fields you drag into the area will be available from the
   QuickPivot drop-down list. Locked fields give the most predictable results. However, generally you
   will get satisfactory results if you use unlocked fields.
5. On the QuickPivot tab, choose one of the selection options.
   - Selection Not Required: A "none" option will be available in the QuickPivot
   - Selection Required: A "none" option will not be available in the QuickPivot
