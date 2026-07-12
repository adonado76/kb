---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Print Layout Configuration"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Layout Options"
source_path: "studio/new-uc/reference/report-studio-reference/print-layout-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Print Layout Configuration

Print Layout mode provides separate controls for how reports appear when exported to PDF or
printed.

**Accessing Print Layout Mode**

1. Check out the report for editing.
2. From the Home tab, click View, then select Print Layout.
3. The Print Layout tab appears with layout controls.

To exit: On the Print Layout tab, click Exit Print Layout Mode.

**Page Setup Options**

|  |  |
| --- | --- |
| **Option** | **Description** |
| **Page Size** | Select paper size from the dropdown (Letter, A4, Legal, etc.) |
| **Flow** | Controls component placement (Manual, Vertical, or Horizontal) |
| **Margins** | Set page margins for printing |
| **Header** | Add header text; displayed on all pages or first page only. Supports HTML formatting and dynamic text |
| **Footer** | Customize footer text; does not support dynamic text |
| **Portrait** | Vertical page orientation |
| **Landscape** | Horizontal page orientation |
| **Scale** | Zoom level for the printed output |

**Flow Options**

Flow controls how components are arranged on the printed page:

|  |  |
| --- | --- |
| **Flow Setting** | **Behavior** |
| **Manual** | You position components manually; they remain where placed |
| **Vertical** | Components are arranged automatically in a single vertical column |
| **Horizontal** | Components are arranged automatically in rows, with maximum components per row |

**Component Print Options**

**Pin/Unpin Components:** Pin components to the end of a report for print output. This is
useful for moving slicers to the end to show applied filters or pinning all components of a specific
type.

**Show/Hide Components:** Control which components appear in the print output:

1. On the Print Layout tab, click Show/Hide Report Components.
2. Clear the checkboxes for components you want to hide.
3. Use the Filter field to find specific components in long lists.

**Configuring Tables for Multi-Page Printing**

To print a large table across multiple pages:

1. Enter Print Layout mode.
2. Move the table to its own page.
3. Select the table, then on the Print Layout tab, click Resize Component to Full Page.
4. With the table selected, on the Table subtab, select Print All Pages.
5. Save and exit Print Layout mode.

**Parent topic:** [Layout Options](../../../../studio/new-uc/reference/report-studio-reference/layout-options.html)
