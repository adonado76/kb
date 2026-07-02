---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Arrange report components"
breadcrumb: []
source_path: "reports/arrange-report-components.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Arrange report components

Applies to: TBM Studio 12.0 and later

TBM Studio R12 provides flexible layout tools for placing and organizing components on a report.
Most of these layout tools are in the Format tab:

![](../../resources/images/studio_images/studioimages/reports/studio_reports_arrange_reports.png)

## Select components

At least one component must be selected to activate the commands on the Format tab. To get
started, click on the header of the component you wish to modify. By default, the report header
displays the name of the component.

A few layout tools require multiple components to be selected. To select more than one component:

- In Windows: Hold down the Ctrl key, then click the header of each component you
  wish to modify.
- In MacOS: Hold down the Alt key, then click the header of each component you wish
  to modify.

## Move report components

In a report, you can reposition components.

- Click and hold the report component header and then drag the component to a new location.

If you move a component to a position where it overlaps with another component, you can select
which components should be in front of the other.

1. Select the component.
2. On the Format tab, in the Position & Size group, click either **Bring to
   Front** or Send to Back.

   ![](../../resources/images/studio_images/studioimages/reports/studio_report_components_front_back.png)

## Align components

Use the commands in the Align group of the Format tab to control how two or more components
appear relative to each other. These commands are active only after you select two or more
components in a report.

1. Select the two or more components you wish to align.
2. In the Align group of the Format tab, click the alignment options you
   want.

   ![](../../resources/images/studio_images/studioimages/reports/studio_report_components_align.png)

The Left, Center, and Right commands control the horizontal alignment of the
selected components. The Top, Middle, and Bottom commands control the vertical
alignment of the selected components.

## Resize report components

Resize a report component by dragging the bottom, sides, or corners of a component's border.

1. Hover the mouse pointer over the bottom, side, or corner of a component's border. The mouse
   pointer will change to a Resize icon.If the border is hidden, position the mouse pointer anywhere
   over the component to see its border.
2. When the Resize icon appears, click and drag the border to change the height or width of the
   component.

## Distribute components

To evenly space components horizontally or vertically in a report, use the commands in the
Distribute group. The application uses the outer components to set the boundaries, then distributes
the components evenly within the boundaries. If necessary, the application will overlap
components.

![](../../resources/images/studio_images/studioimages/reports/studio_report_components_horiz-vert.png)

## Make components the same size

To make charts and tables in a report the same size, use the commands in the Match Size
group. The application uses the first component you select as the standard and resizes all other
components to match. You can resize the width, the height, or both.

![](../../resources/images/studio_images/studioimages/reports/studio_report_components_width_height.png)

## Snap to Grid

When Snap to Grid is selected, components will snap to the nearest point on an invisible
grid.

![](../../resources/images/studio_images/studioimages/reports/studio_report_components_snap_to_grid.png)

## Set component position and size with coordinates

To position or size components precisely, use Set Position and Size. Components can be
positioned relative to the report window or to a group box.

Both position and size numbers are displayed in pixels. You also can use negative numbers (up to
-24 pixels) in the X-position field. This is useful if you want to hide the component's header and
move the component to the top border of the group box.

1. Right-click the component you wish to move, then click Position and Size.
2. Enter the position and size values (in pixels) you want.

   ![](../../resources/images/studio_images/studioimages/studio_arrange%20report%20components_set%20position%20and%20size.png)
3. Click Apply to save the changes, and then click OK to close the window.

## Set component visibility

You can control whether entire components appear under certain criteria.

1. Select a component.

   ![](../../resources/images/studio_images/studioimages/reports/studio_reports_visibility_1100x167.png)
2. In the Advanced group of the Report tab, click Visibility.

   The options in the
   Report Component Visibility box vary, depending on the type of component you have
   selected.

   ![](../../resources/images/studio_images/studioimages/studio_component%20visibility_report%20component%20visibility.png)

Options may include:

Component contains data: Will hide the selected component if it does not contain or
calculate data.

User's current role is: Allows you to choose specific roles that can view the selected
component.

Dynamic text does not evaluate to "hidden": Hides the component if the argument resolves
to "hidden."

Example: I want a component to be visible if variance is negative. If variance if
positive, set as "hidden."

## Printed page settings

To set the orientation and page size for printed reports, and to see the report in Page view, use
the Print Layout tools. To learn more, see [Print and export reports](printexportreports.dita "(Opens in a new tab or window)").
