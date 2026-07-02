---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Enhanced Forecast"
breadcrumb:
  - "Cloudability Premium"
  - "Plan"
source_path: "product/efp-forecast.html"
images:
  - "images/efp-minigraph.jpg"
  - "images/efp-model-settings.jpg"
  - "images/efp-save-budget.jpg"
  - "images/efp-settings.jpg"
  - "images/efp-summary.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Enhanced Forecast

Use the Enhanced Forecast page to generate and analyze cloud spend forecasts. It uses Intelligent
Forecasting to generate forecasts from historical actuals and provides flexible controls for
analyzing results by spend driver. You can compare forecast models, review model accuracy, and
adjust model selection for individual forecast line items. This helps improve forecast accuracy,
makes the forecast easier to understand, and gives you more control when needed.

To learn more about how Intelligent Forecasting works, see
[Intelligent Forecasting](intelligent-forecasting.html)

The Enhanced Forecast page has the following components:

- **Summary** – shows KPIs and a summary chart of actual and forecasted spend, with optional
  budget comparison
- **Details** – shows forecast line-item detail in a table for analysis by spend driver
- **Forecast controls** – used to generate forecasts, save results to a budget, and apply a
  budget for comparison

These component is described in more detail below.

## Summary

Select the **Summary** tab to review high-level forecast results.

![](../../../../03-media/cloudability-premium/images/efp-summary.jpg)

KPIs

The KPI cards show totals for the actuals and estimates displayed in the summary chart, along
with a separate total for the current fiscal year. If a budget is applied, a budget variance KPI is
also displayed.

Summary chart

The summary chart displays:

- Actuals for historical periods
- Estimates for forecasted periods
- Budget amounts, if a budget is applied

In this view, **Actuals** are recorded historical spend amounts and **Estimates** are
projected future spend amounts generated from those actuals by the Intelligent Forecast engine.
Together, they make up the overall **forecast**.

The estimates are shown with a **Confidence Range** that reflects the high and low values for
a given period. The **Confidence Range** is based on a statistical range and can grow wider over
time as uncertainty increases farther into the forecast horizon.

The current fiscal year is shown as a highlighted region on the chart so that you can clearly see
how actual and forecasted spend contribute to the current fiscal year total.

You can interact with the chart in several ways:

- Hover over a data point to view detailed values.
- Click a legend item to hide or show its associated chart element.
- Click the expand icon, shown as a double arrow, to expand the chart to full-page size.

## Details

Select the **Details** tab to review and analyze
forecast line-item details.

Forecast line-item details are shown in a table, where each row
represents the historical spend and estimated future spend for a unique combination of selected
spend driver values. For each line item, the table also shows the selected forecast model and its
accuracy score. You can sort, filter, and group the table by spend driver and other table values to
compare results, focus on specific spend patterns, and analyze the forecast from different
perspectives. You can also show or hide table columns by using the Columns Chooser in the table
sidebar or from the column header menu.

Estimated values for future periods are generated from
historical actual values using the Intelligent Forecast engine, which evaluates multiple statistical
forecast models and automatically selects the model that best fits the input data series.

To
learn more about supported models and model selection, see
[Intelligent Forecasting](intelligent-forecasting.html)

![](../../../../03-media/cloudability-premium/images/efp-minigraph.jpg)

Forecast line mini-graph

To examine a specific forecast
line item more closely, click the expand icon next to the row to open its mini-graph.

You can
interact with the mini-graph in similar ways to the summary chart:

- Hover over data points to view details.
- Hide or show chart elements by clicking legend entries, for example, to hide the **Confidence
  Range** display.

You can also view details about the forecast model used to generate the forecast values,
compare alternate model results, and change the selected model.

Model
Settings

Click **Model Settings** in the mini-graph to open forecast model
settings for the selected forecast line.

The **Model Settings** page displays line graphs
for all forecast model results. Models are listed in the selection panel in descending order by
accuracy. The currently applied model is highlighted in both the chart display and the model
list.

![Show all model results in mini-graph](../../../../03-media/cloudability-premium/images/efp-model-settings.jpg)

Use the **Select Model** list to
preview and choose a different forecast model. When you select a model from the list, the
corresponding line in the chart display is highlighted and the information pane updates to show
details about that model.

Select **Update** to apply the selected model. When you do, the
forecast line-item values are updated using that model’s results.

Select the
**Recommended** model to return to the Intelligent Forecast engine’s recommended model.

To
close the **Model Settings** page and return to the forecast line-item details, select
**Cancel** or press **Esc**.

Export

To export
forecast line-item detail, open the table overflow (3-dot) menu and select **Export**. The export
file is generated in CSV format.

## Forecast controls

The page header includes forecast controls
shared by both the **Summary** and **Details** tabs. Use these controls to generate a
forecast, save the results to a budget, and apply an existing budget for
comparison.

Forecast Settings

Select **Forecast
Settings** to generate a new forecast. This opens a panel where you can choose the forecast
parameters. When you select **Apply**, the forecast is generated using the selected parameters. A
progress bar is displayed while the forecast is being generated. After generation is complete, the
results are available on both the **Summary** and **Details** tabs.

![Forecast Settings panel](../../../../03-media/cloudability-premium/images/efp-settings.jpg)

Forecast settings include the following:

| Setting | Description |
| --- | --- |
| Cost Metric | Cost metric for the forecast. Available options include standard Cloudability cost metrics and any custom cost metrics. |
| Actuals start | Select the first month of historical actuals to include in the forecast input series. This defines the lookback period used by the forecast engine. You may choose any start month, but it must be at least 12 months before the current month.  The selected start period can affect seasonality detection. Although not required, using the start of a fiscal year or fiscal quarter can help align repeating spend patterns to your fiscal calendar. In general, more historical data improves forecast accuracy. |
| Duration | Select how far into the future to forecast. Options include forecasting to the end of the current fiscal year, to the end of the next fiscal year, or for fixed durations such as 12, 18, or 24 months. |
| Excluded Spend | Optionally exclude **Credits**, **One-time Charges**, or both from the forecast calculation. |
| Spend Drivers | Select the dimensions used to break the forecast into line-item detail. Available choices include Cloudability dimensions such as Business Dimensions, Tags, Account Groups, and Vendor. Each unique combination of selected dimension values becomes a line item in the forecast details table. |

Note: The forecast details table supports up to 1,000 items. If the forecast produces
more than 1,000 detail lines, the table shows the top 1,000 items plus an **Other** row that
contains the sum of the remaining line items.

Save forecast as Budget

Use **Save** to create a
budget from the current forecast. This opens the **Save Budget** panel, prepopulated with
forecast values that can be edited before saving.

![Save Budget Panel](../../../../03-media/cloudability-premium/images/efp-save-budget.jpg)

The Save Budget panel shows the View and Cost Metric used for the new budget,
along with default values for the required inputs: budget name, budget start period, and
duration.

When creating a budget from the current forecast:

- the budget cost metric matches the forecast and cannot be changed
- historical periods are populated with actuals
- future periods are populated with estimates
- periods outside the current forecast range are set to zero

Budgets created from the Enhanced Forecast page are aligned to fiscal year boundaries. The
budget start can be the current, prior, or next year, and duration can range from 1 to 3
years.

You can edit the prepopulated amounts before saving. Double-click a cell to enter a
new value. Values entered in summary periods, such as quarter or year totals, are automatically
spread across the included periods.

After saving, the budget can be managed from the Budgets
page. See [Budgets](bf-budgets.html) to learn
more.

Apply a Budget

Use the **Budget** selector to
apply an existing budget to the forecast summary. When a budget is applied, budget amounts are
displayed as a bar chart overlay on the summary chart to help visualize how actuals and estimated
values compare to budget. A Budget Variance KPI is also added.

- **[Intelligent Forecasting](../product/intelligent-forecasting.html)**
