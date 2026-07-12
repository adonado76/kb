---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Component Positioning"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Layout Options"
source_path: "studio/new-uc/reference/report-studio-reference/component-positioning.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Component Positioning

**Manual Positioning (Drag and Drop)**

The primary method for positioning components is drag and drop:

- **Move a component:** Click the component's header and drag it to a new location.
- **Resize a component:** Drag the left, right, or bottom borders and corners.
- **Precise positioning:** Right-click the component header and select Position and Size to
  open the Set Position and Size dialog.

The Set Position and Size dialog allows you to specify exact coordinates:

- **X coordinate:** Horizontal position from the left edge (in pixels)
- **Y coordinate:** Vertical position from the top edge (in pixels)
- **Width:** Component width
- **Height:** Component height

**Dynamic Positioning Options**

For responsive layouts, use the Dynamic menu on the Format tab. These options control how
components position themselves relative to their container (the report surface, a group box, or a
tabbed component).

|  |  |
| --- | --- |
| **Option** | **Description** |
| **Dynamic Off** | Turns off dynamic sizing and positioning; component stays where placed |
| **Center** | Positions the component in the center of its container without changing size |
| **Center and Grow** | Centers the component and allows it to grow symmetrically from the center |
| **Fill Right** | Extends the component to the right border of its container |
| **Fill Right and Bottom** | Extends the component to both the right and bottom borders |
| **Dock Right** | Moves the component so its right edge touches the container's right border |
| **Dock Bottom** | Moves the component so its bottom edge touches the container's bottom border |

**To apply dynamic positioning:**

1. Select the component.
2. Open the Dynamic menu on the Format tab.
3. Select one of the positioning options.

Note: Only one dynamic positioning option can be applied to a component at any given time.

**Parent topic:** [Layout Options](../../../../studio/new-uc/reference/report-studio-reference/layout-options.html)
