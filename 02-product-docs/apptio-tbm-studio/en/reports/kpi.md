---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Key Performance Indicators (KPIs)"
breadcrumb: []
source_path: "reports/kpi.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Key Performance Indicators (KPIs)

Applies to: TBM Studio 12.0 and later

You can display key performance indicators (KPIs) on dashboards and other reports by adding a KPI
component.

![](../../resources/images/studio_images/studioimages/reports/rep250.png)

A KPI component displays whatever number of metrics you wish, and includes the following features:

- Arrows to show the variance from the previous period.
- Slicers to apply to KPI components.

## Add a KPI component

1. Display a report and check it out.
2. On the Report tab, in the Query group, click
   KPI. The KPI component is added to the report, and the KPI Configuration
   dialog appears:![](../../resources/images/studio_images/studioimages/studio/stu519.png)
3. Select a modeled object from the menu underneath KPI Configuration.
4. Drag fields you wish to view as KPIs from Tables,
   Calculations, and other perspectives to the KPIs
   area.
5. If added KPIs do not initially appear in the KPI component, there may not be enough space. Drag
   the edges of the KPI component to change its size and allow space for all values to be visible.

## Show and Hide KPIs

1. Select the KPI component.
2. In the KPI tab, click Show/Hide Panels, then select the KPIs you wish to
   be visible in the KPI component.The list of KPIs in Show/Hide Panels is fully
   dependent on the KPI Configuration of the component.

## Show KPI component border

To enable or disable the border for a KPI component, right-click the KPI component, click
Properties, select or unselect Show Border, and then
Apply. By default, KPI components do not have the border visible.

## Rename KPI Label in Reports (BETA)

Applies to: 12.11.6 and later

Admin can enable this feature via TBM Studio >
Project > Enable Features > Allow Renaming
KPIs.

![](../../resources/images/studio_images/rename-kpi_267x531.png)

To rename the KPI, do the following:

1. Add a KPI report component to a report
2. Drag metrics into the KPI configuration panel

   Right-click on the KPI and then select
   Rename.

   ![](../../resources/images/studio_images/kpi-1_706x440.png)
3. The Rename KPI popup appears.

   ![](../../resources/images/studio_images/kpi-popup.png)
4. Enter the appropriate name for the KPI and select OK. The KPI is renamed
   successfully.

   ![](../../resources/images/studio_images/kpi-rename_693x449.png)

## Filter the values

After adding values to a KPI, you can filter the values by dragging fields from the
Tables perspective into the Filters area. Filters
apply to all values displayed in the KPI. For example, assume you have a KPI component that displays
cost information for all business units. You can filter the KPI to display costs for a specific set
of business units.

To filter the KPI values for a specific set of business units:

1. Click the KPI.
2. Drag the Business Unit field from the Dimensions
   section of the Project Explorer into the Filters area.
3. Right-click the Business Unit field and click Edit
   Filter.
4. Select the business units you want to include in the KPI values.

## Add variance indicators

To indicate the variance in a value from the previous period, you can add a percent value and
indicator arrows to the KPI.

![](../../resources/images/studio_images/studioimages/studio_kpi_add%20variance%20indicators.png)

To add a variance indicator to a value in a KPI component:

1. Click the KPI component.
2. Click the KPI tab.
3. Click the value in the KPI component to which you want to add the indicator.
4. Click the Comparisons icon in the KPI toolbar.
5. Under Trend Type, select an option.
6. Select a display option.
7. Under Trend Direction, select one of the options for the indicator.
   - Up is Green: If the value of the current period is greater than the value of the previous
     period, display the arrow in green. For example, you might choose this option if the percentage of
     server up time has increased.
   - Up is Red: If the value of the current period is greater than the value of the previous period,
     display the arrow in red. For example, you might choose this option if the number of Help Desk
     tickets has increased.
8. To close the options drop-down, click outside of the drop-down box.
9. To save the changes, click Save on the Home tab.

## Add secondary values

A secondary value is a value displayed below the main value. In the image example, the secondary
value is Budget, and the (40%) value in red indicates the budget is 40% below the cost value.

![](../../resources/images/studio_images/studioimages/studio_kpi_secondary%20values.png)

To display a secondary value:

1. Click the KPI component.
2. Click the KPI tab.
3. Click the value in the KPI component to which you want to add the secondary value.
4. Click the Secondary icon in the KPI tab.
5. Select a value.
   - The secondary values are limited to the values currently displayed in the KPI. Usually when you
     add a secondary value, you hide the same value in the main part of the KPI.
   - To hide a value, click the Show/Hide icon in the KPI tab and select the value you want to
     hide.

## Add tertiary values

A tertiary value is a percentage value displayed to the right of the main value. A tertiary value
can compare the month-over-month (MoM) change in the main value, or the variance between the main
and secondary values (Over/Under). In the image example, the tertiary value is indicating that the
Cost is 66% over the budgeted amount:

![](../../resources/images/studio_images/studioimages/studio_kpi_business_unit_costs.jpg)

Note: Only KPIs with numeric fields in the Tables section or custom perspectives can have tertiary
values.

## Shorthand notation

You can display numbers in a KPI using K/M/B notation (thousand/million/billion). To use the
notation:

1. Click a value in the KPI component and click the Shorthand option on the KPI tab.
2. Select which values (primary/secondary) the shorthand should be applied to.
3. Select the target notation types for the shorthand notation.

## Change the KPI colors

You can change the colors of each element in a KPI by clicking Colors in the KPI
tab. Colors can be applied separately to each value in a KPI bar, or to the component as a whole if
no value is selected.

## Wrap Name Text

When selected, the name of the primary value will be wrapped if it is too long to fit within the
width of the KPI.

## KPI Properties

As with other report components, you can edit the properties for a KPI component. To edit the
properties for a KPI component, find the Properties menu by performing one of the following actions:

- In the top-left corner of the component, click the small triangle next to the component name to
  display the Actions menu. From the Actions menu, select Properties.
- Right-click anywhere within the borders of the component and select Properties.

General properties

- Name: Enter a name to be displayed in the note header above the component. The name is
  displayed when Show Header option is selected.
- Caption: Enter additional information about the note. The information is displayed based
  on the setting of the Caption Position field. You can use HTML code in the field, but the
  HTML code cannot include links. The restriction on the HTML code is for security reasons.
- Caption Position: From the list, select a caption position relative to the note: Top,
  Bottom, Left, or Right, or select Hide to not display the caption.
- Show Header: The component header displays the contents of the Name field. Select this
  option to make the component header visible (the default). When the header is hidden, you can pause
  the mouse pointer on the component to display it.
- Show Border: Select this option to display a border around the table. When in Edit mode,
  you can display a hidden border by pausing the cursor over the table.
- Wrap Title: Wraps the text entered in the Name field to accommodate the width of the
  KPI.

## Advanced Property

- Auto Refresh when Calculations Finish: When the application displays a note, it displays
  it with the calculated data that is currently available. In many cases, the application may be
  calculating new values in the background. If you want the results displayed when the calculations
  are complete, check this option. The option applies only to the currently selected table. This
  option is available only when the Calculation Policy (in the Edit Project dialog) for
  a project is set to Dynamic Publishing.

For more information on changing the type and formatting of KPIs, see [Tip: Type and
Format influence how KPIs appear](https://community.apptio.com/docs/DOC-5400 "(Opens in a new tab or window)").
