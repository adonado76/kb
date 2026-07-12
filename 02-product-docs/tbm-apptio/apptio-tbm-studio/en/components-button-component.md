---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Button Component"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
  - "Button Component"
source_path: "SSWRJM/studio/report-studio/components/button-comp.html"
images:
  - "03-media/apptio-tbm-studio/button.png"
  - "03-media/apptio-tbm-studio/but-for.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Button Component

*The Button component allows users to trigger actions directly from a report, enabling interactive and dynamic workflows. Buttons can be configured to perform tasks such as navigating to another report, executing scripts, or updating report context (for example, changing the date).*

## When to use buttons

Use buttons when you want to:

- Enable users to navigate between reports
- Trigger predefined actions or scripts
- Provide quick interactions without relying on filters or menus
- Simplify workflows by offering clear call-to-action elements

## Add button to a report

To add a button to your report:

1. Open the report in the editor.
1. From the Components pane in the toolbar, drag and drop the Button onto the canvas.
1. Select the button to configure its properties using the Data panel and Format panel.

Example

Button Data Panel

Use the Data panel to define the button’s behaviour:

- Button Text - Set the label displayed on the button.
- Enabled - By default, the button is enabled. You can define an enablement rule to conditionally disable the button.
- Server Action - Attach a server-side script that executes when the button is clicked.
- Change Date Action - Configure a specific date so that clicking the button updates the report to that date.
- Navigation Action - Select a target report to navigate to when the button is clicked.

Format Panel

Properties Tab

Customize the appearance and layout of the button:

- Icon Toggle
- Enable this option to include an icon. Default icon: Information icon Choose from a dropdown list of available icons Set icon placement: Left or Right
- Default Button Style
- Customize the appearance of the button in its default state: Font Text color Background color Border size and color Icon color and size
- Hover Button Style
- Define how the button appears when hovered, including the same styling options as the default state.

General Tab

- Alt Text
- Add descriptive text for accessibility.
- Position and Size
- Adjust placement and dimensions on the canvas.
- Style Padding (including per-side adjustments) Corner radius for rounded edges

The Button component enhances report interactivity by enabling users to take direct action. With flexible configuration for behavior and styling, it can be tailored to support a wide range of use cases - from navigation to automation - while maintaining a consistent user experience.
