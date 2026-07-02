---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Set chart properties"
breadcrumb: []
source_path: "reports/set-chart-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Set chart properties

Applies to: TBM Studio 12.0 and later

There are a wide range of properties available for charts that control the look and feel of
charts. The Chart Properties dialog is shown in the following image:

![](../../resources/images/studio_images/studioimages/reports/rep173.png)

## Display the Properties dialog

To edit the properties for a chart, display the Properties dialog by performing one of the
following actions:

- Select the chart and click the Properties icon ![](../../resources/images/studio_images/studioimages/icons/properties_icon_21x21.png) on the
  Author tab.
- In the top-left corner of the chart, click the small triangle ![](../../resources/images/studio_images/studioimages/icons/arrow-down-greyicon.png) next to the
  chart name to display the Actions menu. From the Actions menu, select
  Properties.
- Right-click in the title bar of the chart and select Properties from the pop-up
  menu.

## Chart properties for charts

The Chart properties are shown below. To see all properties, you may need to scroll the
display.

![](../../resources/images/studio_images/studioimages/reports/rep173.png)

Chart fields descriptions follow. NOTE: some charts will have a subset of these
fields. Fields marked with an asterisk (\*) apply only to legacy charts and not to ad-hoc charts.

- X Axis Tag - Select the source column for the X-axis values in the chart.
- Y Value Tag - Select the source column for the Y-axis values in the chart.
- Y Axis Scale - Select Linear or Logarithmic.
- Chart Style\* - Select the Pie, Bar, Horizontal Bar, Stacked Bar, Stacked Horizontal Bar,
  Filled Radar, Radar with Markers, or Trend (line) option.
- Color Spec - Enter a color formatting string to change the color of an entity on the
  chart. For more information, see [Setting the default colors for metrics on charts](set-default-colors-charts.htm "(Opens in a new tab or window)").
- Chart Number Format - Enter a pattern to format the numbers on the chart axis. The syntax
  is the same used by the NumberFormat function but without the function name or quotes. For example,
  to display numbers as $5,000,000, enter #,###. You cannot use a formula in this field.
  - To remove all formatting from the numbers, enter #.
  - If you are displaying a metric calculation in the chart, the chart formatting overrides the
    metric formatting. If you leave this field (and the Number Prefix and Number Suffix fields) blank,
    the default format specified for the metric being displayed will be used.
  - To format numbers as currency using the currency symbol for the locale selected for the project,
    preface the format statement with the universal currency Unicode symbol (¤). The easiest way to do
    this is to copy the symbol from the previous sentence and paste it into the field.
  - For more information on formatting numbers, see the [NumberFormat function](../formulas-and-functions/functions/numberformat.htm "(Opens in a new tab or window)") in the *Studio Guide*.
- Chart Number Prefix - Enter text to be displayed before all numbers in the chart (for
  example, $ for dollars).
  - If you want dollar figures to be displayed in the format $#.##M (for example, $7.28M), enter a $
    sign in this field and clear all formatting from the Chart Number Format field.
  - To format numbers as currency using the currency symbol for the locale selected for the project,
    enter the universal currency Unicode symbol (¤) in the field instead of the $ sign. The easiest way
    to do this is to copy the symbol from the previous sentence and paste it into the field. Use the
    Unicode symbol in this field or the Chart Number Format field, but not both.
  - If you leave this field blank, the default format specified for the metric being displayed will
    be used.
- Chart Number Suffix - Enter text to be displayed after numbers in the chart (for example,
  M for millions).
- If you leave this field blank, the default format specified for the metric being displayed will
  be used.
- Show Data Values - Select this option to display data values for each data point in the
  chart.
- Multicolor Single Series Charts - In a chart with a single series of values, for example,
  Cost per business unit, the series is displayed in a single color. Select this option to
  display each element in the series in a different color.
- Reverse Order - Reverses the order of the series displayed on the x or y axis.
- Hide X axis - Hides the X axis.
- Hide Y Axis - Hides the Y axis.
- Hide Grid Lines - Hides horizontal and vertical grid lines.
- Legend Location - Select a location for the chart legend or select Hidden to make
  the legend invisible. The default location is South (below the chart).
- Include zero on the y-axis - If selected, this option forces the Y axis to start at 0. If
  cleared, the Y axis can start on a larger number to better display small variations.
- Share Axis - Used only with overlay charts. Makes the scales on the left and right axes
  the same.
- Exploded Slice - Enter the name of one of the slices to be offset slightly (exploded)
  from the rest of the chart. In the example below, the New York slice is exploded. You also can
  explode a slice by selecting a slice in a pie chart, right-clicking, and then selecting
  Explode.

  ![](../../resources/images/studio_images/studioimages/reports/rep061.png)

## Data properties for charts

The Data properties shown in the following image control the data displayed in the chart:

![](../../resources/images/studio_images/studioimages/reports/rep175.png)

The data fields descriptions follow.

Note: Some charts will have a subset of these fields. Fields marked with an (\*) apply only to legacy
charts and not to ad hoc charts.

- Maximum Rows - Determines the number of elements displayed in the chart.
  - In bar charts, it controls the number of bars.
  - In pie charts, it controls the number of slices.
  - In line charts, it controls the number of elements on the X axis.
  - If the number of elements exceeds the number specified in this field, the remaining elements
    will be grouped into an element called Other.

  Tip: Before you can view this data, go to Reports > Data, then for the
  Sum option, select Show Other Row.
- Include Columns\* - Restrict displayed columns to those selected from this list.
- Exclude Columns\* - Allow all columns to display except those selected from this
  list.
- Show rows for which all metric values are 0\* - Override the default behavior by allowing
  zero-value rows to display.
- Pivot Data Set\* - Pivots the data contained in the chart, switching the X and Y axes.
  This option only applies to legacy charts.

## General properties for charts

The General properties are shown in the following image. As you change the settings, you
can preview your changes by clicking Apply.

![](../../resources/images/studio_images/studioimages/reports/rep176.png)

The General fields descriptions follow.

- Name - Enter a name to be displayed in the chart header above the component. The name is
  displayed when the Show Header option is selected.
- Caption - Enter additional information about the chart. The information is displayed
  based on the setting of the Caption Position field. You can use HTML code in this field, but
  the HTML code cannot include links. The restriction on the HTML code is for security reasons.
- Caption Position - From the list, select a caption position relative to the chart. The
  information: Top, Bottom, Left, or Right, or select Hide to not
  display the caption at all.
- Show Border - Select this option to display a border around the chart. When the border is
  hidden, you can pause the mouse pointer on the chart to display it when in Edit mode.
- Show Header - The component header displays the contents of the Name field. Select
  this option to make the chart header visible (the default). When the header is hidden, you can pause
  the mouse pointer in the chart to display it when in Edit mode.
- Wrap Title - Wraps the text entered in the Name field to accommodate the width of
  the chart.

## Advanced properties for charts

The Advanced properties control several display options for charts. The tab is shown in
below:

![](../../resources/images/studio_images/studioimages/reports/rep177.png)

Advanced fields descriptions follow.

Note: Some charts will have a subset of these fields. Fields marked with an (\*) apply only to legacy
charts and not to ad hoc charts.

- Data URL\* - Displays the path to the table that supplies the data for this report. You
  can enter a table function in this field by clicking the Edit Data Path icon to the right of
  the field. The application displays the Edit Path dialog. WARNING: do not edit the
  path if you are not thoroughly familiar with data paths.
- Auto Refresh when Calculations Finish - When the application displays a chart, it
  displays it with the calculated data that is currently available. In many cases, the application may
  be calculating new values in the background. If you want the results displayed when the calculations
  are complete, check this option.
  - This option is available when the Calculation Policy for a project (in the **Project
    Calculation** dialog) is set to Dynamic Publishing.
- Data Time Period - Determines the time period applied to the chart. The default
  Current Project Date displays data for the date displayed in the date picker. There are many
  other options available from the drop-down list.
- Hide Time Lock Warning - If you have set the Data Time Period field to a value
  other than Current Project Time, a lock icon is displayed in the lower-right corner of the
  chart. Checking this option hides the icon.
- Hide Hydration Warning - If you place a chart on an object report that is based on a
  different unit than the report itself, the application displays a warning ![](../../resources/images/studio_images/studioimages/icons/hydration_warning.png) icon and a
  text message in the lower-right corner of the component in Edit mode. These are not displayed in
  View mode. If you select this option, the warnings will not be displayed in Edit mode.
  - For example, assume you have a Business Units object and you drill down to a Business Unit A
    report with a chart and table that display data about Business Unit A. In the same report, you want
    to display information about Business Unit B for comparison purposes. You add components to the
    report to display this information. Because you did this intentionally, you do not want the
    application to display the hydration warning, so you select the Hide Hydration Warning
    option.
- Auto Shorten New Dotted Column Names - Displays only the part of a column name that
  follows the "." dot. For example, if the column name is Data Center Costs.Data Center Hosting Cost,
  the name would be displayed as Data Center Hosting Cost.
- Lines Per Row - This field is used with tables and does not apply to charts. Leave the
  field blank.
- Max. Columns to Display - Determines the maximum number of columns processed in the
  source table. This does not impact the data displayed in the chart.
- Pivot Row Col\* - The column in the source table that provides the values for the first
  column in the pivoted table.
- Pivot Col Col\* - The column in the source table that provides the headings for the data
  columns in the pivoted table.
- Pivot Val Col\* - The column in the source table that provides the values for the cells in
  the pivoted table.
- Include PK Column - Will include the default column in the chart, whether or not it is
  specified in the normal "columns to include" list. For charts displaying ungrouped data, this is
  typically the identifier of the object backing the report component. For charts displaying grouped
  data, it is typically the column used for the grouping.
- Use Column Aliases - In circumstances where you have two objects with the same columns
  displayed in the same table such as Consumer.Master Table.L0 Name and Provider.Master Table.L0 Name,
  checking this option makes is possible to correctly configure the columns in the table.
  Recommendation: Leave this option selected.
