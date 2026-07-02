---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Intelligent Forecasting Overview"
breadcrumb:
  - "Planning"
  - "Intelligent Forecasting"
source_path: "it-planning/planning/intelligent-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Intelligent Forecasting Overview

Intelligent Forecasting introduces advanced time-series forecasting techniques into
Apptio Planning, empowering teams to produce more accurate, consistent forecasts with less
manual effort. The feature analyzes historical spend patterns and automatically applies the most
suitable model for each line item.

**Key Features:**

- **Automated model selection based on historical trends**

  Intelligent Forecasting
  analyzes each line item’s time‑series pattern and automatically selects the most
  appropriate forecasting model.
- **Outlier detection to improve forecast accuracy**

  Historical anomalies are
  detected allowing users to adjust them, so the model is trained on cleaner, more stable
  data—leading to more reliable forecast results.
- **More accurate and consistent forecasts**

  Automated pattern detection (trend,
  level, seasonality), parameter tuning, and optimized smoothing produce stronger accuracy
  and reduce forecast variation between planners.
- **Increased transparency and control, with the ability to review and refine
  results**

  Planners can inspect model settings, smoothing parameters, and standard
  accuracy measures. Forecasts are fully editable: users can accept, adjust, or override
  values as needed.

## Enable Intelligent Forecasting

Note: Admin or Budget Process Owner roles
are required to perform these tasks.

**Steps to Enable Intelligent Forecasting**

1. Navigate to **Settings**
   **(Gear icon)** → **Company Profile**.
2. Ensure **New Expenses Page Experience (Beta)** is enabled first—Intelligent
   Forecasting cannot be used without it. To enable the feature, follow these steps:
   - **General Configuration** → **Access & Permissions** → Select **Enable
     New Expenses Page Experience (Beta)**
3. Select **Forecasting** → **Enable Intelligent Forecasting**
4. Click **Save and Exit** button

## Apply Intelligent Forecasting

Note: *ITPPredictiveForecastingFeatureFullAccess* permission is required to use the
Intelligent Forecasting feature. Admin, Budget Process Owner and Cost Center Owner roles
already have this permission.

Users can create or modify forecasts by defining the forecast periods and historical data
in the **Forecast** dialog box.

1. Navigate to the **Expenses** page and enable the **New View** toggle.
2. Select the Expenses (Summary, Other, Assets, Contracts, Labor or Labor Activity) tab.
3. Go to the **Other** tab.
4. Select one or more line items by checking the box next to each item.
5. Then choose **Forecast** either from the right‑click menu or by clicking the
   **Forecast** button.
6. In the **Forecast** dialog, select the **Historical Date Range** by selecting the
   **Start Period** and **End Period**. This data will be used to generate the
   forecast.
7. *A minimum of 3 months of data is required to run Intelligent Forecasting.*
8. In the same dialog, configure the **Forecast Period** by selecting the **Start
   Period** and **End Period**.
   - The **Forecast Start Period** automatically defaults to the month immediately
     after the Historical End Period but can be overridden.
   - The **Forecast End Period** can be any month between the Forecast Start Period
     and the Plan End Period.
9. To review the generated forecast, click **Preview**.
10. You may switch between forecast models to compare outputs and statistical details.
11. When satisfied with the forecast, select the model to apply and click **Apply Selected
    Model** to update the chosen line items.

## Supported Expense Types for Intelligent Forecasting

**Other & Summary**

- Other expenses can be forecasted from either the **Other** tab or the **Summary**
  tab.
- Applying a forecast updates the corresponding financial values automatically.

**Labor & Labor Activity**

- Supported for **Labor** and **Labor Activity (Hours)**.
- The forecast preview displays:
- **Headcount** for Labor
- **Hours** for Labor Activity
- Applying a forecast automatically updates both labor and labor activity financials.

**Contracts & Assets**

- Supported for **Manual Amortization Contracts** and **Manual Depreciation
  Assets**.
- Forecasting is **disabled** for unsupported contract and asset rows.
- Applying a forecast generates updated financials for both contracts and assets.

**Important Notes**

- Intelligent Forecasting is **not available** for:
- External lines
- Generated financials
- Submitted expenses
- Actuals
- Support for using **Actuals as historical data** for forecasting is planned for a
  future release.
- Support for **Intelligent Forecasting on grouped expenses** is also planned for a
  future release.

## Reviewing and Interpreting the Forecast Preview

Note: *ITPPredictiveForecastingFeatureFullAccess* permission is required to use the
Intelligent Forecasting feature. Admin, Budget Process Owner and Cost Center Owner roles
already have this permission.

The forecasting preview shows what the results for the forecast look like, based on your
input. This gives you the opportunity to analyze and work with projected forecast data
before applying it, helping you make more informed decisions.

1. The Forecast Preview is available after clicking the **Preview** button on the
   **Forecast** dialog.
2. The **Preview Chart** displays the visualization of the historical data followed by
   the forecasted data, which is represented as a dotted line.
3. The **Preview Chart** shows predicted values, as well as a confidence interval that
   indicates high and low bounds within a shaded area.
4. **Prediction Accuracy** score shows the overall forecast accuracy, indicating how
   closely the model’s predictions match historical data.
5. Click on the **Statistical details** tab to review the details for the forecast.

To learn more about the models and statistical details, please see [Forecasting Models](forecasting-model.html "Intelligent Forecasting automatically evaluates a diverse set of statistical models to identify the best fit for your data. These models range from adaptive smoothing methods to baseline and regression‑based approaches. The goal is to capture different data behaviors—such as growth trends, repeating seasonal patterns, volatility, and linear relationships—so the system can consistently generate accurate and explainable forecasts across various business scenarios.")

## Identifying and Adjusting Forecast Outliers

Note: *ITPPredictiveForecastingFeatureFullAccess* permission is required to use the
Intelligent Forecasting feature. Admin, Budget Process Owner and Cost Center Owner roles
already have this permission.

**Outliers**

An outlier is any data point within the **last 20% of your historical values** that
falls **outside the model’s confidence range** for that point in time. These points
indicate moments where the actual value deviated more than expected from typical patterns
in the data.

During forecasting, multiple models are evaluated and compared.
Although the model‑fitting confidence intervals for historical points are not displayed,
each fitted value has an estimated confidence range—similar to the intervals shown for the
forecast.

Most historical points usually align closely with their model‑estimated
values. However, when a point falls noticeably outside the expected confidence range, it
is identified as an outlier. This signals that the historical value was unusually high or
low compared to what the model anticipated.

Outliers can occur due to one‑time
events, unusual spend spikes or drops, or data entry anomalies. Highlighting them helps
you understand which historical values may be contributing to unexpected model behavior or
reduced forecast accuracy.

**Adjusting Outliers**

1. When Intelligent Forecasting identifies outliers in your historical data, you can view
   the outliers in Forecast Preview and Outliers Detected button is activated.
2. Click the **Outliers detected** button on the preview. The **Outliers detected**
   pane opens.
3. Click **Adjust outliers** to update the forecast and see the impact of the
   adjustment.
4. When multiple outliers are detected, they are adjusted sequentially from the beginning
   of the data set. This means that each adjusted outlier value is applied to the
   calculation of the adjustment for the subsequent outlier, resulting in a more accurate
   forecast.
5. When satisfied with the forecast, click **Apply Selected Model** to update the
   chosen line items.
