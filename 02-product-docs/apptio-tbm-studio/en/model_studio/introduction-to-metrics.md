---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "model_studio"
title: "Create and manage metrics"
breadcrumb: []
source_path: "model_studio/introduction-to-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Create and manage metrics

Applies to: TBM Studio 12.0 and later

Metrics are calculations that define measurements for reports. The metrics defined for each
project are available for all reports in the project across all time periods. The metrics are listed
in the Metrics section of Project Explorer. To define a new metric, open the
New menu on the Home tab, and click Metric.

## Types of metrics

There are two types of metrics:

- Modeled metrics. A model is itself a metric. A model calculates a numeric
  value such as cost, quantity, or budget. A model can have multiple metrics. Models also are referred
  to as modeled metrics.
- Calculated metrics. A calculated metric uses a formula to derive a
  numeric value. For example, you could create a calculated metric called
  Budget\_Variance defined as the Budget-modeled metric minus the Cost-modeled
  metric.

The values calculated by metrics usually are displayed in reports using charts. Metrics, once
defined, are available to all reports in a project and in all time periods.

There are several key differences between modeled and calculated metrics:

- When grouping, model metrics sum numbers. Calculated metrics recalculate.
- Calculated metrics can calculate across time. Modeled metrics cannot.

Following are several guidelines that may help you determine the type of metric to create:

- If you have an attribute that will apply across several different areas, then create a
  modeled metric. A prime example is Cost, which is the default model metric in
  the application. A Cost model can be used to review the cost for many areas at different levels in
  your organization.
- If you want to allocate a numeric value from one element in your organization to another, then
  create a modeled metric. For example, if you want to allocate the cost of
  servers to applications, this is best done with a modeled metric.
- If you have an attribute that will be used for only one calculation, create a
  calculated metric. An example might be the number of servers or the number of
  trouble tickets.

## Create a metric

To create a metric:

1. On the Home tab, in the Document group, click
   New, and then click Metric.
2. Enter a name for the metric, and then click OK.
3. Complete the fields in the Properties pane. See the following detailed
   field-level descriptions under Metric properties.
4. Click Save.

## Delete a metric

To delete a metric:

1. In Project Explorer, click Metrics.
2. Click the metric you want to delete.
3. Check out the metric if it is not already checked out.
4. In the Home tab, in the Document group, click
   Delete, then click Save.
5. Check in the metric.

## Select metrics to improve performance

You can use the Edit Metrics button in the Tier Editor to specify which metrics you want
to apply to a model report. The selected metrics are saved upon check-in, which speeds up
calculations in the Staging and Production environments. Selecting fewer metrics results in faster
calculations.

To select (edit) model metrics for a new report:

1. In TBM Studio, click New > Model Report.
2. Click Edit Metrics to open the Model Report
   dialog.

   ![](../../resources/images/studio_images/studioimages/modelreport_edit_button.png)
3. (Optional) Click None to clear the checklist.
4. Select the metrics you want to apply to your new model report.

   ![](../../resources/images/studio_images/studioimages/modelreport_dialog.png)
5. (Optional) Add a Description.
6. Click OK.
7. Click View > Show Document.Note that the options available in the
   **Select a metric** picker are now limited to the metrics you selected in the Model
   Report dialog.

To limit the metrics calculated for an existing model report:

1. Open the report, then click View > Show Document > Edit Metrics.
2. Select only the metrics you want to apply to the report, then click
   OK.You cannot modify the report name.

## Metric properties

Metric properties control the behavior of a metric in the project. Using metric properties, you
can select the metric name, type, format, and whether the metric appears in unit tables. Metric
properties are described below. Properties that apply to calculated metrics only are flagged with an
asterisk (\*).

- Default View - If the metric is displayed in a report as a link, clicking
  on the link will display the report entered in this field.
- Model Type - When creating a metric, select the model type.
  - Model - Creates a new model in the modeler.
  - Calculated - Displays the Value Calculation field,
    in which you enter a formula or function to define how the metric is derived. After the metric is
    created, this field becomes read-only.
- Ignore for Internal Filtering\* - When checked, calculated metrics are
  excluded in the evaluation for filtering out rows that have all zeros. This evaluation happens even
  if the metrics are hidden. Rows with zeros in all columns can be included by clearing the
  option.
- Can Sum\* - If it is valid to add the values of this computation together
  instead of recomputing the formula when calculating, check the box.
- Include in Virtual Models\* - If you want the metric included in filtered
  and recursive models, check the box.
- Metric Type - If the metric values are monetary from a fully costed
  source such as a general ledger, select Costing. If you select
  Costing, you also should set the table format to
  Currency.
  - If the metric is associated with a price x quantity model, select
    Pricing.
  - If the metric values are in any other format, select Numeric.
- Hidden - Hides the metric in model object unit tables.
- Value Calculation\* - Enter a formula that defines the value of the
  calculated metric (see [Formulas and functions](../formulas-and-functions/introduction-to-formulas-and-functions.html "Applies to: TBM Studio 12.0 and later")).
  - To refer to a column in a table, use the format table.column name.
  - To refer to a column in a table in another project, use the format **project!table:column
    name**.
  - To retrieve the sum of all values in a table column, use the format **table:column
    name**.
  - To retrieve the sum of values in a column where a second column is equal to a specific value,
    use the format table:column[column2="value"].
  - To retrieve the sum of values in a column where a second column is equal to the value of the
    current row's table.column value, use the format **table:column[column2=table.column
    name]**.
  - You can refer to the current metric using $\_ instead of having to type
    out the full metric name. This is useful if you want to use the same formula in multiple metrics.
    You can copy and paste the formula without having to replace the metric name every time.
- Table Format - Specifies the format for the value of the metric when
  displayed in report tables. You can specify formats in HTML or use the [NumberFormat](../formulas-and-functions/functions/numberformat.html "Applies to: TBM Studio 12.0, 12.1") function.
  - To display values as dollars in models, enter: =Currency($\_).
  - To specify formats using a dialog box instead of code, click the Table
    Format icon ![](../../resources/images/studio_images/studioimages/table+format%20icon.png).
  - If you select Advanced, you must enter a formula manually, just as you do in the **Table
    Format** field of the Properties pane. If you select another format, the
    dialog box displays appropriate formatting choices. For the Number and Currency formats, you can
    choose to include "thousands" separators (comma, period, etc.) by selecting the Use
    Grouping Separator option.
- Applicable Templates - This field is used by the Apptio Applications
  group only and relates to the templates.apptio.com project. DO NOT edit this
  field.
- Time Behavior - Specifies the operation when the metric is viewed in an
  aggregate time period, such as a quarter.
  - Sum - Calculates each period separately and then adds the periods
    together.
  - Average - Calculates each period separately, adds the periods together,
    and then divides the result by the number of periods.
  - Recalculate - Computes the aggregated values in all columns referenced by
    the calculated metric, then reruns the metric’s formula.
- Chart Format - Enter a pattern to use in formatting numbers on the chart
  axis. The syntax is the same as for the patterns and negative patterns used by the
  NumberFormat function but without the function name or quotes. For example,
  to have numbers displayed in a format like $5,000,000, you would enter
  $#,###. You cannot use a formula in this field.
  - If you wish to format the numbers as currency such that the currency symbol will reflect the
    locale selected for the project, preface the format statement with the universal currency Unicode
    symbol (¤). The easiest way to do this is to copy the symbol from the previous sentence and paste it
    into the field.
  - For more information on formatting numbers, see the function.
- Chart Prefix - A prefix to be added to the metric when displayed in
  charts. For example, a $ sign.
- Chart Suffix - A suffix to be added to the metric when displayed in
  charts.
- Time Interval\* - None,
  Quarterly, or Yearly. If you set this to
  Quarterly or Yearly, the metric will be pulled from
  the first period in the time interval rather than being calculated. For example, if you select
  Yearly, the metric will go back and look up the values from January instead
  of recalculating based on the current time period.
