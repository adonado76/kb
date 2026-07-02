---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Place components on tabs"
breadcrumb: []
source_path: "studio/reports/place-components-on-tabs.html"
images:
  - "resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png"
  - "resources/images/studio_images/studioimages/studio/aug151.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Place components on tabs

**Applies to**: TBM Studio 12.0 and later

If you have a series of related components you want to put in a report, but do not want to spread
them out over a large area of the report, you can place the components in a tabbed group. The user
then can select a tab to display a specific component or components. All components except grouping
boxes can be placed on a tab. A sample tabbed group is shown in the following image:

![components on tabs](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/aug151.png)

## Add a tabbed group

From the **Report** tab, click the **Tabs** icon.

## Take actions in tabbed groups

The actions you can take in a tabbed group are described below:

| To: | Do this: |
| --- | --- |
| Add a tab to the group | Click the tab with the + sign and enter a name for the tab in the **Edit Tab** field. To save the tab, press Enter. |
| Add a component to a tab | Create the component on the reporting surface and drag it into the tabbed group. You can add more than one component to a tab. |
| Remove a component from a tab | Drag the component out of the tabbed group or click the delete icon in the upper-right corner of the component. |
| Change the order of the tabs | Select a tab and click the left/right double arrow icons (<<) (>>) below the tabbed group box. |
| Delete a tab | Select the tab and click the **Delete** icon below the tabbed group box. |
| Resize the group box | Click and drag the borders. |
| Add background color to a tab | Right-click in the tab and select **Properties** from the pop-up menu. On the **General** tab of the **Properties** dialog, select a color from the **Tab Background Color** field. You can select a different color for each tab. |

## Set the properties

To set the properties for the tabbed group, display the **Properties** dialog by doing one of
the following:

- In the upper-left corner of the tabbed group, click the small triangle ![small triangle](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) next to the component name to display the **Actions** menu. From the
  **Actions** menu, click **Properties**.
- Right-click anywhere within the borders of the component and click **Properties** from the
  pop-up menu.

## General properties

- **Name** - Enter a name to be displayed in the component header above the component when
  **Show Header** is selected.
- **Caption** - Enter additional information about the component. The information is displayed
  based on the setting of the **Caption Position** field.
- **Caption Position** - From the list, select a caption position relative to the button:
  **Top**, **Bottom**, **Left**, or **Right**, or select **Hide** to not display the
  caption.
- **Show Header** - The component header displays the contents of the **Name** field. Select
  this option to make the component header visible (the default). When the header is hidden, you can
  pause the mouse pointer on the component to display it when in Edit mode.
- **Show Border** - Select this option to display a border around the table. When the border is
  hidden, you can pause the mouse pointer on the component to display it when in Edit mode.
- **Wrap Title** - Wraps the text entered in the **Name** field to accommodate the width of
  the component.
- **Tab Background Color** - Select a color for the background of the tabs. This setting
  applies to all tabs in the group.

## Advanced properties

**Auto Refresh when Calculations Finish** - When the application displays a tab component, it
displays it with the calculated data currently available. In many cases, the application may be
calculating new values in the background. If you want the results displayed when the calculations
are complete, check this option.

## Place components in a tabbed group

Ideally, you want components in a tabbed group to move with the group if you reposition it. For
components to move with the group, they must be positioned well within the borders of the group. To
ensure they are placed correctly:

- Right-click on the object heading and click **Position and Size** in the pop-up menu.
- In the **Set Position and Size** dialog, set the X and Y coordinates to zero.

Use the resulting margins as starting points for positioning the object. You can increase the
margins and the object will move with the group. If you decrease the margins, the object will be
decoupled from the group.

## Control the display of tabs

When you add a tabbed group to a report, you can use dynamic text to control which tabs are
displayed. Dynamic text can reference a data set, or it can use an If statement with filters.

The options for controlling the tabs are:

- **enabled**: tab is visible and selectable
- **hidden**: tab is not visible
- **disabled**: tab is visible but not selectable

The options can be applied to all tabs in a group except the first tab. The first tab will always
be visible and selectable.

The example below uses the value "hidden" from a data set called TabStatus:

> `<%=TabStatus:Hidden%>`

The example below shows a simple option to hide the tab:
> <%="hidden"%>

The data set might look like the following with a header row and a value row:

| Enabled | Hidden | Disabled |
| --- | --- | --- |
| enabled | hidden | disabled |

An example If statement is shown below:

> `<%=If(GetLastFilterValue()="Sales","hidden","enabled")%>`

The above example will only work on a filtered report.

To make tabs conditionally enabled or hidden based on the user's role, use the following IF
statement:

> ```
> <%=IF(eval("{$CurrentUser}:{Users.Role}")
>       ="Admin","enabled","hidden")%>
> ```

To specify the settings for the tabs:

1. Select the tabbed group.
2. From the **Tabs** tab, click **Visibility**.
3. Enter a reference to a data set or an If statement for each tab (except Tab 1 which is always
   visible).
4. Click **Save**.
