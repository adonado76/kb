---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "08-Plan-Budgets-and-Forecasts"
source_files_count: 6
last_updated: "2026-07-13"
---

# 08-Plan-Budgets-and-Forecasts

## Budgets and Forecasts

<!-- sub-header -->
- **breadcrumb:** Plan > Budgets and Forecasts
- **source_path:** SSVCLNQ/product/plan-and-manage-your-budgets-and-forecasts.html
- **original_file:** plan-budgets-forecasts.md
- **images:**
  - 03-media/apptio-cloudability-standard/using_the_cost_mceclip0.jpg
  - 03-media/apptio-cloudability-standard/using_the_cost_mceclip1.jpg
  - 03-media/apptio-cloudability-standard/using_the_cost_mceclip2.jpg

## Budgets and Forecasts

Budgets and Forecasts helps you understand and predict your cloud spends by:

- Creating forecasts based on historical spending patterns.
- Using forecasts to create budgets .
- Monitor and notify spending related to budgets.

These tools are all based around views, allowing you to separate individual Business Units and manage them independently. If you are currently on a Pro plan, you can only use these features at the organization level. See Views API for more information on creating views programmatically.

Some of the features of these tools are:

- Support for multiple accounting options, including Cash (recommended), Amortized (helpful if your organization buys Partial/All-Upfront RIs), Adjusted (reflecting any Custom Pricing agreements you have calibrated) and Adjusted Amortized .
- Set up periodic alerts to receive notifications and spendings for the current month.
- Simple views to analyze your budget,
- Paired with Anomaly Detection service.

Using the Cost (List) metric for budgeting and forecasting

Cost (List) allows you to budget and forecast your cloud spend using consistent cost metrics.

If an instance usage has been covered by an all-upfront reservation, the Cost (Total) will show $0 while the Cost (List) will show the on-demand cost for that particular usage. On the other hand, for recurring monthly fees and occasional one-time fees, Cost (List) will show $0 as these are likely the charges to be excluded for budget and forecasting exercises. For spot instances, the Cost (Total) displays the actual deeply discounted cost while Cost (List) shows the on-demand cost for that particular usage.

The FAQ explains how Cloudability generates Cost (List) values. The difference between Cost (List) and Cost (Total) or Cost (Adjusted) shows the overall benefits of reservations and custom pricing.

![budgets and forecasting screenshot  ](../images/using_the_cost_mceclip0.jpg)

If specific cost metrics are not exposed, use Cost (List) to provide chargeback to consumers (or business units, account groups, etc.).

![cost screenshot  ](../images/using_the_cost_mceclip1.jpg)

You can set up daily email notifications.

![cloud spend summary emails screenshot  ](../images/using_the_cost_mceclip2.jpg)

FAQ

Which Public Cloud Vendors does Cost (List) support?

Cost (List) supports AWS and GCP.

Why does Cost (List) sometimes show a lower value than the other cost metrics do?

The primary use case of the Cost (List) metric is around Budgets and Forecasting. Cloudability zeroes out the values of certain line items depending on transaction types and lease types to help reduce the noise in Budget and Forecasting work. The line items that Cloudability zeroes out include:

- Recurring RI Upfront Fees
- One-time RI Upfront Fees
- Custom Pricing Credits

Which items does Cloudability report as is for Cost (List) ?

Cloudability reports the extraordinary credits (ex. Billing error correction) as is for Cost (List). In the case of GCP, Cloudability zeroes out the credits for Committed Usage Discounts. The credits for Sustained Usage Discounts, however, get reported as is. Again, it’s all about the primary use case of the Cost (List) — Budget and Forecasting. The items being reported as-is for Cost (List) are the ones that consumers (or business units, account groups) need to account for Budget and Forecasting works.

---

## Budgets

<!-- sub-header -->
- **breadcrumb:** Plan > Budgets and Forecasts > Budgets
- **source_path:** SSVCLNQ/product/bf-budgets.html
- **original_file:** forecasts-budgets.md
- **images:**
  - 03-media/apptio-cloudability-standard/budgets-homepage.jpg
  - 03-media/apptio-cloudability-standard/new-budget.jpg

## Budgets

Budgets are scoped at the View level, making it simple to track Business Units independently. They are also tied to a particular cost basis. Most customers will start with Cash. If your organization buys a lot of partial or all-upfront RIs, you can use Amortized to have a better indication if your spending is trending differently. If you have Custom Pricing calibrated in Cloudability , you might prefer Adjusted or Adjusted Amortized.

Use Case

You can set up multiple sets of views - tracking Environment with one set of views (for example, Development, Staging, and Production) and feature-level divisions with another set of views (RI planner, Rightsizing, Workload Placement, Automation). You can also create multiple budgets for a given view, for example, showing Annual Budget as well as Quarterly Stretch Goal for the spending covered under the Engineering view.

Customize the Budgets Dashboard

Navigate to Plan > Budgets

To create a new budget, select New Budget button.

Enter the appropriate values and Save .

You can perform the following actions:

- Subscribe to set up notifications if you are on track to exceed your budget in the current month and if you have exceeded your budget in the current month.
- Edit a budget.
- Delete a budget.

Setting up Email Notifications for Budget

Follow these steps to set up the Email Notification for budget alerts:

1. Navigate to Plan > Budget > Click on Subscribe at top right.
1. On left panel, click 'Add Notification'.
1. Select the View and Budget for which you want to receive the alert. Select 'Expected to Exceed' and/ or 'Exceeded' and Save.
1. The frequency of alert would depend on Email preferences of the user (whether daily, weekly, monthly or quarterly).

---

## Current Month

<!-- sub-header -->
- **breadcrumb:** Plan > Budgets and Forecasts > Current Month
- **source_path:** SSVCLNQ/product/bf-current-month.html
- **original_file:** forecasts-current-month.md
- **images:**
  - 03-media/apptio-cloudability-standard/current-motnh-homepage.jpg

## Current Month

The parameters Service Name and Usage Family are used to identify Spending Drivers, making it easy for technical and business users to understand what is driving any changes. You can view your Spending Drivers in terms of the largest spend as well as the largest change relative to the previous month. However, in the online application, the miscellaneous Spending Drivers are grouped under Other .

Use Case

Many vendors systematically back-date certain types of charges. When you notice this pattern in your historical spending, you can adjust the total for the previous month to reflect these late-breaking charges. You can tell this has happened by the yellow info bubble. With the availability of Cost basis, you can put your current month into context, using the previous month as well as any budget you have selected. Using the Month-to-Date chart, you can also see approximately when you are projected to exceed your budget for the month.

Customize the Current Month Dashboard

Navigate to Plan > Current Month

Select appropriate values for Cost Basis and Apply Budget parameters, to see the updated dashboard.

You can perform the following actions:

- Subscribe to periodic updates on your total monthly spending.
- Setup interval preference to receive emails daily or weekly.
- Toggle between Total Spend and Delta Spend to view their respective details.

---

## Forecast

<!-- sub-header -->
- **breadcrumb:** Plan > Budgets and Forecasts > Forecast
- **source_path:** SSVCLNQ/product/bf-forecast.html
- **original_file:** forecasts-forecast.md
- **images:**
  - 03-media/apptio-cloudability-standard/forecast-homepage.jpg
  - 03-media/apptio-cloudability-standard/forecast-details.jpg

## Forecast

This feature allows you to see historical spending patterns and inspect the underlying changes that are driving your forecasted spend so that you can understand what is expected to change. It also helps you to create additional budgets.

Use Case

You might use the six-month trend to create a reasonable stretch goal budget for your team which is less than the plan from your finance team. With Cloudability, it's easy to share this budget with your team, receive updates on your progress, and see Plan vs. Actual reporting on your progress to date.

Customize Forecast Dashboard

Navigate to Plan > Forecast

Select Details button to see the forecast details.

You can perform the following actions:

- Modify the view by selecting appropriate values for any of the parameters, like cost basis, forecast model, and so on.
- Export tabular data, either via the UI or the API, to a financial management tool of your choice.
- Save the forecast as a budget.

FAQ

Why am I seeing a message about "missing cost data" for this month?

AWS typically sends updated billing files every four hours. Occasionally, particularly in the first and last few days of the month, it can take longer. We'll show you your estimate based on the most recent data, but when we haven't received a billing file from Amazon for a given month, we'll show an incomplete data banner.

---

## Enhanced Forecast

<!-- sub-header -->
- **breadcrumb:** Plan > Enhanced Forecast
- **source_path:** SSVCLNQ/product/efp-forecast.html
- **original_file:** plan-enhanced-forecast.md
- **images:**
  - 03-media/apptio-cloudability-standard/efp-summary.jpg
  - 03-media/apptio-cloudability-standard/efp-minigraph.jpg
  - 03-media/apptio-cloudability-standard/efp-model-settings.jpg
  - 03-media/apptio-cloudability-standard/efp-settings.jpg
  - 03-media/apptio-cloudability-standard/efp-save-budget.jpg

## Enhanced Forecast

Use the Enhanced Forecast page to generate and analyze cloud spend forecasts. It uses Intelligent Forecasting to generate forecasts from historical actuals and provides flexible controls for analyzing results by spend driver. You can compare forecast models, review model accuracy, and adjust model selection for individual forecast line items. This helps improve forecast accuracy, makes the forecast easier to understand, and gives you more control when needed.

To learn more about how Intelligent Forecasting works, see Intelligent Forecasting

The Enhanced Forecast page has the following components:

- Summary – shows KPIs and a summary chart of actual and forecasted spend, with optional budget comparison
- Details – shows forecast line-item detail in a table for analysis by spend driver
- Forecast controls – used to generate forecasts, save results to a budget, and apply a budget for comparison

These component is described in more detail below.

### Summary

Select the Summary tab to review high-level forecast results.

KPIs

The KPI cards show totals for the actuals and estimates displayed in the summary chart, along with a separate total for the current fiscal year. If a budget is applied, a budget variance KPI is also displayed.

Summary chart

The summary chart displays:

- Actuals for historical periods
- Estimates for forecasted periods
- Budget amounts, if a budget is applied

In this view, Actuals are recorded historical spend amounts and Estimates are projected future spend amounts generated from those actuals by the Intelligent Forecast engine. Together, they make up the overall forecast .

The estimates are shown with a Confidence Range that reflects the high and low values for a given period. The Confidence Range is based on a statistical range and can grow wider over time as uncertainty increases farther into the forecast horizon.

The current fiscal year is shown as a highlighted region on the chart so that you can clearly see how actual and forecasted spend contribute to the current fiscal year total.

You can interact with the chart in several ways:

- Hover over a data point to view detailed values.
- Click a legend item to hide or show its associated chart element.
- Click the expand icon, shown as a double arrow, to expand the chart to full-page size.

### Details

Select the Details tab to review and analyze forecast line-item details.

Forecast line-item details are shown in a table, where each row represents the historical spend and estimated future spend for a unique combination of selected spend driver values. For each line item, the table also shows the selected forecast model and its accuracy score. You can sort, filter, and group the table by spend driver and other table values to compare results, focus on specific spend patterns, and analyze the forecast from different perspectives. You can also show or hide table columns by using the Columns Chooser in the table sidebar or from the column header menu.

Estimated values for future periods are generated from historical actual values using the Intelligent Forecast engine, which evaluates multiple statistical forecast models and automatically selects the model that best fits the input data series.

To learn more about supported models and model selection, see Intelligent Forecasting

![](../images/efp-minigraph.jpg)

Forecast line mini-graph

To examine a specific forecast line item more closely, click the expand icon next to the row to open its mini-graph.

You can interact with the mini-graph in similar ways to the summary chart:

- Hover over data points to view details.
- Hide or show chart elements by clicking legend entries, for example, to hide the Confidence Range display.

You can also view details about the forecast model used to generate the forecast values, compare alternate model results, and change the selected model.

Model Settings

Click Model Settings in the mini-graph to open forecast model settings for the selected forecast line.

The Model Settings page displays line graphs for all forecast model results. Models are listed in the selection panel in descending order by accuracy. The currently applied model is highlighted in both the chart display and the model list.

Use the Select Model list to preview and choose a different forecast model. When you select a model from the list, the corresponding line in the chart display is highlighted and the information pane updates to show details about that model.

Select Update to apply the selected model. When you do, the forecast line-item values are updated using that model’s results.

Select the Recommended model to return to the Intelligent Forecast engine’s recommended model.

To close the Model Settings page and return to the forecast line-item details, select Cancel or press Esc .

Export

To export forecast line-item detail, open the table overflow (3-dot) menu and select Export . The export file is generated in CSV format.

### Forecast controls

The page header includes forecast controls shared by both the Summary and Details tabs. Use these controls to generate a forecast, save the results to a budget, and apply an existing budget for comparison.

Forecast Settings

Select Forecast Settings to generate a new forecast. This opens a panel where you can choose the forecast parameters. When you select Apply , the forecast is generated using the selected parameters. A progress bar is displayed while the forecast is being generated. After generation is complete, the results are available on both the Summary and Details tabs.

Forecast settings include the following:

| Setting | Description |
| --- | --- |
| Cost Metric | Cost metric for the forecast. Available options include standard Cloudability cost metrics and any custom cost metrics. |
| Actuals start | Select the first month of historical actuals to include in the forecast input series. This defines the lookback period used by the forecast engine. You may choose any start month, but it must be at least 12 months before the current month. The selected start period can affect seasonality detection. Although not required, using the start of a fiscal year or fiscal quarter can help align repeating spend patterns to your fiscal calendar. In general, more historical data improves forecast accuracy. |
| Duration | Select how far into the future to forecast. Options include forecasting to the end of the current fiscal year, to the end of the next fiscal year, or for fixed durations such as 12, 18, or 24 months. |
| Excluded Spend | Optionally exclude Credits , One-time Charges , or both from the forecast calculation. |
| Spend Drivers | Select the dimensions used to break the forecast into line-item detail. Available choices include Cloudability dimensions such as Business Dimensions, Tags, Account Groups, and Vendor. Each unique combination of selected dimension values becomes a line item in the forecast details table. |

Save forecast as Budget

Use Save to create a budget from the current forecast. This opens the Save Budget panel, prepopulated with forecast values that can be edited before saving.

![Save Budget Panel](../images/efp-save-budget.jpg)

The Save Budget panel shows the View and Cost Metric used for the new budget, along with default values for the required inputs: budget name, budget start period, and duration.

When creating a budget from the current forecast:

- the budget cost metric matches the forecast and cannot be changed
- historical periods are populated with actuals
- future periods are populated with estimates
- periods outside the current forecast range are set to zero

Budgets created from the Enhanced Forecast page are aligned to fiscal year boundaries. The budget start can be the current, prior, or next year, and duration can range from 1 to 3 years.

You can edit the prepopulated amounts before saving. Double-click a cell to enter a new value. Values entered in summary periods, such as quarter or year totals, are automatically spread across the included periods.

After saving, the budget can be managed from the Budgets page. See Budgets to learn more.

Apply a Budget

Use the Budget selector to apply an existing budget to the forecast summary. When a budget is applied, budget amounts are displayed as a bar chart overlay on the summary chart to help visualize how actuals and estimated values compare to budget. A Budget Variance KPI is also added.

---

## Intelligent Forecasting

<!-- sub-header -->
- **breadcrumb:** Plan > Enhanced Forecast > Intelligent Forecasting
- **source_path:** SSVCLNQ/product/intelligent-forecasting.html
- **original_file:** forecast-intelligent-forecasting.md
- **images:** []

## Intelligent Forecasting

### Overview

Features such as the Enhanced Forecast Page and Cloudability Financial Planning use the Intelligent Forecast Engine to generate forecasts from historical time-series data. The Intelligent Forecast Engine evaluates multiple forecast models to identify the model that best matches each historical time series. These models are designed to capture different types of behavior in time-series data, such as stable values, linear growth or decline, repeating seasonal patterns, and changes in variability over time. By supporting multiple model types, the engine can generate forecasts that are more accurate, explainable, and adaptable across different scenarios.

Forecast accuracy generally improves when more historical data is available, because the models can better identify recurring seasonal patterns, longer-term trends, and underlying variability. A richer historical data set gives the engine more context for selecting the best-fitting model and producing a more stable forecast.

The Intelligent Forecast Engine supports several forecast model types, including Baseline, Linear Trend, Moving Average, and selected ETS models. These models are designed to fit different historical patterns in the data and use different settings or parameters depending on how they work.

The Intelligent Forecast Engine runs all supported model types against each forecast item and selects the model that performs best for the historical pattern in that item.

Learn more about how Intelligent Forecasting works

### Forecast model types

| Model Type | Description |
| --- | --- |
| Baseline | The Baseline model, sometimes referred to as Naive , uses the most recent historical value as a simple forecast without explicitly modeling trend or seasonality. It is best suited for relatively stable patterns where recent history is a reasonable indicator of near-term future values. Because it does not model more complex patterns, it may be less accurate when values are steadily rising, steadily falling, or follow recurring seasonal cycles. |
| Linear Trend | The Linear Trend model fits a straight-line trend to historical values and projects that trend forward. It is best suited for data that is steadily increasing or decreasing over time. Because it does not model repeating seasonal patterns, it may be less accurate when values vary according to recurring monthly, quarterly, daily, or other cyclical patterns. |
| Moving Average | The Moving Average model forecasts future values by averaging a defined number of the most recent historical periods. For example, a 3-period rolling average uses the average of the most recent three periods to generate the forecast. This model is useful when data is noisy and short-term fluctuations need to be smoothed. Because it smooths recent history, it tends to react more slowly to change and may understate rising values or overstate falling values. |
| ETS models | ETS stands for Error, Trend, and Seasonality . ETS models are a family of exponential smoothing models in which each model is defined by the form of its error, trend, and seasonal components. In standard notation, an ETS model is written as ETS(Error, Trend, Seasonality) . For example, ETS(A,A,N) represents a model with additive error, additive trend, and no seasonality. In the shorthand used here: A = additive Ad = damped additive trend N = none M = multiplicative |

Supported ETS-based models include the following:

| ETS acronym | Descriptive name | Technical description |
| --- | --- | --- |
| ANN | Simple Exponential Smoothing | Models additive error with no trend and no seasonality |
| AAN | Holt’s Linear Trend | Models additive error with additive trend and no seasonality |
| ANA | Exponential Smoothing with Additive Seasonality | Models additive error with no trend and additive seasonality |
| ANM | Exponential Smoothing with Multiplicative Seasonality | Models additive error with no trend and multiplicative seasonality |
| AAdN | Holt’s Damped Trend | Models additive error with damped additive trend and no seasonality |
| AAA | Holt-Winters Additive | Models additive error with additive trend and additive seasonality |
| AAM | Holt-Winters Multiplicative | Models additive error with additive trend and multiplicative seasonality |
| AAdA | Holt-Winters Additive with Damped Trend | Models additive error with damped additive trend and additive seasonality |
| AAdM | Holt-Winters Multiplicative with Damped Trend | Models additive error with damped additive trend and multiplicative seasonality |

ETS models are useful when patterns in the data are more complex and may include sustained directional change, repeating seasonal behavior, or both. Because ETS models include additional parameters, they can often fit complex time-series patterns more accurately than simpler models, provided there is enough historical data to estimate those parameters reliably. Each ETS variant represents a different structural assumption about the behavior of the time series, and the Intelligent Forecast Engine evaluates these variants to determine which structure best fits the observed historical pattern.

### Forecast model comparison

| Model family | Model name | Model parameters | Best for | Main limitation |
| --- | --- | --- | --- | --- |
| Baseline models | Naive | None | Stable data where recent history is a reasonable indicator of near-term future values | Less accurate when values have sustained trend or recurring seasonal patterns |
| Trend models | Linear Trend | Slope and intercept | Data that is steadily increasing or decreasing over time | Less accurate when values have recurring seasonal patterns |
| Averaging models | Moving Average | Window length | Noisy data where short-term smoothing is helpful | Tends to lag when values are rising or falling quickly |
| ETS models | Simple Exponential Smoothing (ANN) | α | Stable data with limited trend or seasonal variation | Less accurate when values have sustained trend or recurring seasonal patterns |
| ETS models | Holt’s Linear Trend (AAN) | α, β | Data with a steady upward or downward trend but no repeating seasonal pattern | Less accurate when values have recurring seasonal patterns |
| ETS models | Exponential Smoothing with Additive Seasonality (ANA) | α, γ | Data with recurring seasonal patterns but a relatively stable overall level | Less accurate when values have sustained upward or downward trend |
| ETS models | Exponential Smoothing with Multiplicative Seasonality (ANM) | α, γ | Data with recurring seasonal patterns whose size increases or decreases with the overall level | Less accurate when values have sustained upward or downward trend |
| ETS models | Holt’s Damped Trend (AAdN) | α, β, φ | Data with a trend that is expected to moderate over time | Less accurate when values have recurring seasonal patterns |
| ETS models | Holt-Winters Additive (AAA) | α, β, γ | Data with trend and seasonal patterns whose size remains relatively constant over time | Less suitable when seasonal effects increase or decrease with the overall level |
| ETS models | Holt-Winters Multiplicative (AAM) | α, β, γ | Data with trend and seasonal patterns whose size increases or decreases with the overall level | Less accurate when values are low or fluctuate significantly from one period to the next |
| ETS models | Holt-Winters Additive with Damped Trend (AAdA) | α, β, γ, φ | Data with seasonal patterns and a trend that is expected to moderate over time | Requires enough history to estimate those parameters reliably |
| ETS models | Holt-Winters Multiplicative with Damped Trend (AAdM) | α, β, γ, φ | Data with seasonal patterns whose size increases or decreases with the overall level and a trend that is expected to moderate over time | Less accurate when values are low or fluctuate significantly from one period to the next |

### Forecast model parameters

Different forecast model types use different settings or parameters.

| Parameter | Used in | Meaning |
| --- | --- | --- |
| None | Baseline | The Baseline model does not use configurable forecast parameters |
| Slope | Linear Trend | Defines the rate of increase or decrease in the fitted trend line |
| Intercept | Linear Trend | Defines the starting point of the fitted trend line |
| Window length | Moving Average | Defines how many historical periods are included in the rolling average |
| α (alpha) | All ETS models | Level smoothing – controls how quickly the model updates the estimated level, or baseline value, based on new actuals |
| β (beta) | ETS models with trend | Trend smoothing – controls how quickly the model updates the estimated trend based on new actuals |
| γ (gamma) | ETS models with seasonality | Seasonal smoothing – controls how quickly the model updates the estimated seasonal pattern based on new actuals |
| φ (phi) | Damped-trend ETS models | Trend damping – controls how strongly the projected trend is damped over time |

In ETS models, the ETS notation describes the model’s structural form, while the smoothing parameters control how the model updates its internal state components over time. These state components include level , trend , and seasonality . These state components are different from the ETS error component, which describes the form of the residuals – the differences between observed values and the values produced by the model during the fitting process.

These parameters influence how responsive the forecast is to new observed values and how well the model can represent level, trend, and seasonality in the historical data.

Alpha (level smoothing) controls how much weight is given to the most recent value when estimating the overall level of the data.

- Lower alpha – heavier smoothing; the model relies more on longer-term history
- Higher alpha – lighter smoothing; the model reacts more strongly to recent changes
- Alpha = 1 – only the latest data point is used to update the level

Beta (trend smoothing) controls how quickly the model updates its estimate of the trend over time.

- It behaves similarly to alpha, but applies specifically to the trend component
- Higher beta makes the model more responsive to recent changes in trend
- Lower beta makes the trend estimate more stable

Gamma (seasonal smoothing) controls how the model updates seasonal patterns, such as monthly or quarterly seasonality.

- It behaves similarly to alpha, but applies to the seasonal component
- Higher gamma updates seasonality more strongly based on recent periods
- Lower gamma smooths seasonal effects over a longer history

Phi (trend damping) controls how strongly the model reduces the effect of the trend over time.

- Higher phi keeps the trend effect stronger for longer
- Lower phi reduces the trend effect more quickly
- Phi is used only in damped-trend models.

### Trend and seasonality indicators

ETS model results may also include Trend Strength , Seasonality Strength , and Seasonal Period indicators. These values help show how much the trend and seasonal components contribute to model accuracy and how frequently seasonal patterns repeat.

| Indicator | Range | Description | Typical interpretation |
| --- | --- | --- | --- |
| Trend Strength | 0.0 to 1.0 | Indicates how much the trend component improves model accuracy. It is calculated by comparing the original model to the same model with the trend removed. | 0.0 = no meaningful trend 0.0-0.3 = weak trend 0.0-0.3 = weak trend 0.7-1.0 = strong trend |
| Seasonality Strength | 0.0 to 1.0 | Indicates how much the seasonal component improves model accuracy. It is calculated by comparing the original model to the same model with the seasonal component removed. | 0.0 = no seasonal pattern 0.0 = no seasonal pattern 0.3-0.7 = moderate seasonality 0.7-1.0 = strong, consistent seasonal patterns |
| Seasonal Period | Positive integer | Indicates the number of time periods in one full seasonal cycle used by the model. For example, a value of 12 represents a yearly cycle in monthly data, while a value of 7 represents a weekly cycle in daily data. | Higher values indicate a longer repeating cycle. |

These indicators can help explain why a model that includes trend or seasonality was selected. Higher Trend Strength and Seasonality Strength values suggest that the corresponding component contributes more meaningfully to forecast accuracy, while Seasonal Period indicates the length of the repeating cycle identified in the data.

### How Intelligent Forecasting works

When the Intelligent Forecast Engine generates a forecast, it does not rely on a single model or fixed parameter values. Instead, it fits each supported model to the historical pattern for the forecast item, determining the model values, settings, or parameters needed to best match that pattern. This fitting process takes place before the engine evaluates model results and selects the best-performing model.

Some models use relatively simple structures. For example, a Moving Average model uses a window length, and a Linear Trend model uses the fitted slope and intercept of the historical trend line. ETS models are more adaptive and use one or more smoothing parameters, such as alpha (α), beta (β), gamma (γ), and phi (φ), depending on whether the model includes level, trend, seasonality, or damped trend.

For those ETS models, the Intelligent Forecast Engine uses an iterative process to calculate the parameter values that best fit the observed pattern in the historical data for the forecast item.

Higher or lower parameter values change how responsive the model is to new observed values. For example, a higher alpha makes the estimated level react more quickly to recent changes in the data, while a lower alpha makes the level change more gradually.

Once optimal parameter values have been chosen for each model, the Intelligent Forecast Engine evaluates the models to determine which one performs best against the historical data. Using a machine learning approach, it applies each model to an earlier portion of the historical data, compares the resulting forecasted values for a later portion of the same series to the known observed values, and computes the symmetric mean absolute percentage error (SMAPE). It then converts that result into an accuracy score and selects the model with the highest accuracy score.

A simpler model such as Baseline or Moving Average may perform best for a stable pattern, while a more advanced ETS model may perform better for data that includes trend, seasonality, or both. By testing candidate models against a known portion of the input series and scoring them consistently, the engine can select the model that is most likely to produce the most accurate future forecast for that item.

The Intelligent Forecast Engine generates forecasts that adapt to different types of time-series behavior. A stable pattern may be best represented by a simpler model, while a more dynamic or seasonal pattern may require a model with trend and seasonal parameters tuned to that specific history. A pattern may also start as stable and evolve over time into one that requires a more complex model.

Because the Intelligent Forecast Engine selects both the best-performing model and the parameter values that best match the historical pattern, it can generate forecasts that are tailored to each forecast item rather than relying on one fixed approach for all data.

---
