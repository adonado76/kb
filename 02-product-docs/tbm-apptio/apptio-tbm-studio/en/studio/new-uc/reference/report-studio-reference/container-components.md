---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Container Components"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Layout Options"
source_path: "studio/new-uc/reference/report-studio-reference/container-components.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Container Components

Container components will group related elements and provide organizational structure to reports.

**Group Boxes**

Group boxes visually and logically group report components together. Components within a group
box move as a unit when the group is repositioned.

**Key behaviors:**

- Slicers inside a group box apply only to tables and charts within that group box (and any nested
  groups).
- Slicers outside group boxes apply to all tables and charts in the report.

**To add a group box:**

1. On the Report tab, click the Group icon.
2. Move and resize the box as needed by dragging the header (to move) or borders (to resize).

**Group Layout Options (available on the Group tab):**

|  |  |
| --- | --- |
| **Layout** | **Behavior** |
| **Manual** | Position components anywhere; they stay where placed |
| **Vertical** | Automatically aligns components in a vertical column |
| **Horizontal** | Automatically aligns components in horizontal rows |
| **Spacing** | Opens a dialog to set vertical and horizontal spacing between components |

Tip: Use Vertical or Horizontal layouts when components may be conditionally hidden
based on user roles. The remaining components will automatically fill the space left by hidden
components.

**Tabbed Components**

Tabbed components organize multiple components into selectable tabs, conserving report space
while providing access to related content.

To add a tabbed component: On the Report tab, click the Tabs icon.

**Working with tabs:**

|  |  |
| --- | --- |
| **Action** | **How To** |
| **Add a tab** | Click the tab with the + sign; enter a name and press Enter |
| **Add component to a tab** | Create the component on the report surface and drag it into the tabbed group |
| **Remove component from tab** | Drag the component out or click the delete icon in its upper-right corner |
| **Change tab order** | Select a tab and click the left/right double arrow icons (<< / >>) |
| **Delete a tab** | Select the tab and click the Delete icon |
| **Resize the tabbed group** | Click and drag the borders |
| **Set tab background color** | Right-click in the tab → Properties → Tab Background Color |

**Controlling Tab Visibility with Dynamic Text:**

You can use dynamic text expressions to control tab visibility based on data or user roles:

|  |  |
| --- | --- |
| **Value** | **Behavior** |
| **enabled** | Tab is visible and selectable |
| **hidden** | Tab is not visible |
| **disabled** | Tab is visible but not selectable |

Note: All components except group boxes can be placed on a tab.

**Parent topic:** [Layout Options](../../../../studio/new-uc/reference/report-studio-reference/layout-options.html)
