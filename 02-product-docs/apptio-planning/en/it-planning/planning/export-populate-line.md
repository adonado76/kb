---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Export Plan Data"
breadcrumb:
  - "Planning"
  - "Working with Plans"
source_path: "it-planning/planning/export-populate-line.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Export Plan Data

In any Expense table view that displays line-item tables (for example, Summary, Labor,
Labor Activity, Contracts, Assets or Other), users with the appropriate permissions can export
that data to a .csv file.

There are **three export modes** available:

|  |  |
| --- | --- |
| **Export Mode** | **Description** |
| **Export All** | Exports the full dataset, including all dimensions and attributes defined in the plan schema. |
| **Export Layout** | Exports only the data currently visible in your layout, including applied columns, filters, and groupings.If Groupings are applied, the export will include group-level subtotals instead of individual child line items. |
| **Export for Re-import** | Exports all editable fields in a format suitable for reimporting changes. This option ignores filters and time selectors (but respects permission constraints). Note: Additional Name columns and system-generated fields are included in the Export for Re-Import format to enhance readability. These fields are not required, and you may safely ignore any warnings related to them during the import process. |

## Before You Export

- Export results are limited by your data access — for example, cost object ownership
  scope or user role permissions.
- To control which fields are included or how data is organized, first adjust and save
  your table layout.
- Admins and the Budget Process Owner can curate a default layout for all users.

## How to Export Line-Item Data

1. In the plan, select the Department you want to export.
2. Optionally, choose the relevant Layout from the **Layout** menu.
3. Pick the appropriate tab (e.g., Summary, Labor, Labor Activity, Contracts, Assets, or
   Other).
4. Click the **Actions** menu in the upper-right and select **Export...**
5. Choose your preferred export mode (Export All, Export Layout or Export for Re-Import)
   and export format settings (Comma delimiter, Date format, Date separator, Decimal symbol,
   Decimal precision, Percentage display, Character encoding).
6. Click **OK**.
