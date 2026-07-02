---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configure Dynamic Sizing and Positioning"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Advanced Reporting"
source_path: "studio/new-uc/howtoguides/create-reports/dynamic-sizing.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configure Dynamic Sizing and Positioning

**Objective:** Create responsive report layouts that adapt to different screen sizes and
accommodate role-based component visibility without leaving empty spaces.

**When to use:** When reports are viewed on different screen sizes, when components are
conditionally visible based on user role, or when you need precise control over component
arrangement.

**Time estimate:** 15-20 minutes

## Understanding Layout Options

TBM Studio provides flexible layout tools on the Format tab for arranging report
components. You can position components manually or use group boxes with automatic layout
options that adjust when components are hidden or shown.

## Method 1: Manual Component Positioning

**Move components:**

1. Click and hold the component header (the title bar at the top of the component).
2. Drag the component to the desired location.
3. Release to drop the component in place.

**Resize components:**

1. Hover over the edge or corner of a component until the resize cursor appears.
2. Click and drag to resize the component.

**Precise positioning:**

1. Right-click the component and select Position and Size.
2. Enter exact pixel values for X position, Y position, width, and height.
3. Click Apply to preview, then OK to save.

Tip: Use negative X-position values (up to -24 pixels) to hide a component's
header and position it flush against the edge of a group box.

## Method 2: Alignment and Distribution Tools

Use the Format tab tools to align and distribute multiple components:

1. Select multiple components (Ctrl+click on Windows, Alt+click on Mac).
2. On the Format tab, use the Align group:
   - **Left/Center/Right:** Align components horizontally
   - **Top/Middle/Bottom:** Align components vertically
3. Use the Distribute group:
   - **Horizontal:** Space components evenly left to right
   - **Vertical:** Space components evenly top to bottom
4. Use Match Size to make components the same width, height, or both (uses the first
   selected component as the standard).

## Method 3: Group Boxes with Automatic Layout

Group boxes provide automatic layout that adjusts when components are hidden:

1. On the Report tab, click Group. A group box is added to the report.
2. Drag components into the group box.
3. Select the group box and click the Group tab to access layout options:
   - **Manual:** Components stay where you place them
   - **Vertical:** Components arrange in a single column, automatically filling gaps
     when components are hidden
   - **Horizontal:** Components arrange in rows, automatically filling gaps when
     components are hidden
4. Click Spacing to configure the gap between components in pixels.

## Method 4: Auto-Sizing Group Boxes

Configure group boxes to resize dynamically based on their contents:

1. Select the group box.
2. On the Group tab, use the Auto Sizing options:
   - **Fixed:** Group box maintains its size regardless of content (may show scroll
     bars)
   - **Auto Width:** Group box width adjusts to fit content
   - **Auto Height:** Group box height adjusts to fit content
   - **Auto Both:** Both dimensions adjust dynamically

## Method 5: Component Visibility Settings

Configure components to show or hide based on conditions:

1. Select the component.
2. On the Report tab in the Advanced group, click Visibility.
3. Configure visibility conditions:
   - **Component contains data:** Hide when the component has no data to display
   - **User's current role is:** Show only for specific user roles
   - **Dynamic text does not evaluate to "hidden":** Use a formula to control
     visibility

**Example:** To show a variance explanation component only when variance is negative,
use dynamic text:

`<%=IF(Variance<0,"visible","hidden")%>`

## Method 6: Tabbed Component Groups

Use tabbed groups to organize many components in a compact space:

1. On the Report tab, click Tabbed Group.
2. Drag components into the tabbed group. Each component appears on its own tab.
3. Use the arrow buttons below the tab area to reorder tabs.
4. To remove a component, drag it out of the tabbed group.

## Method 7: Dynamic Layout Options

For advanced responsive layouts, use the Dynamic menu options:

- **Center Horizontally:** Centers the component in its container as the container
  resizes
- **Maintain Distance from Top/Bottom:** Keeps the component's position relative to
  container edges
- **Stretch with Container:** Component resizes proportionally as the container changes
  size
- **Anchor Right/Bottom:** Component maintains its position relative to the right or
  bottom edge

## Screen Size Considerations

When creating a report, you select the target screen size:

- **Standard:** 1024 pixels wide
- **Widescreen:** 1440 pixels wide

Choose based on your users' typical screen resolutions. Use dynamic layout options to
ensure reports display well on screens that differ from the design target.

## Snap to Grid

On the Format tab, check Snap to Grid to make components align to an invisible grid when
positioned. This helps create neat, aligned layouts quickly.

## Z-Order (Front/Back)

When components overlap, control which appears in front:

1. Select the component.
2. On the Format tab in the Position & Size group, click Bring to Front or Send to
   Back.

## Expected Results

- Components align precisely using alignment tools
- Group boxes with Vertical/Horizontal layout automatically rearrange when components are
  hidden
- Visibility conditions show/hide components based on user role or data conditions
- Tabbed groups provide compact navigation between multiple components

## Related Tasks

- Create report templates (Section 3.3.1)
- Configure print layouts (this section)
- Set component permissions by role (Section 3.4)

**Parent topic:** [Advanced Reporting](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
