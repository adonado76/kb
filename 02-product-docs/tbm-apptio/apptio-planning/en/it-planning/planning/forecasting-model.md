---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Forecasting Models"
breadcrumb:
  - "Planning"
  - "Intelligent Forecasting"
source_path: "it-planning/planning/forecasting-model.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Forecasting Models

Intelligent Forecasting automatically evaluates a diverse set of statistical models to
identify the best fit for your data. These models range from **adaptive smoothing methods**
to **baseline** and **regression‑based** approaches. The goal is to capture different data
behaviors—such as growth trends, repeating seasonal patterns, volatility, and linear
relationships—so the system can consistently generate accurate and explainable forecasts across
various business scenarios.

Forecast accuracy generally improves when more historical data is available, as the models
can better identify recurring seasonal patterns, long‑term trends, and underlying
variability. Providing a richer historical context enables the forecasting engine to make
more stable and reliable predictions.

Supported Forecasting Models:

- **Holt–Winters models** are highly flexible and adapt to changing trends and seasonal
  patterns.
- **Naive models** act as simple but robust baselines, ideal for volatile or
  pattern‑less series.
- **Linear Regression models** provide structure by learning linear relationships
  between time (or drivers) and the target metric.

## Holt-Winters Models

These models describe time‑series using three adaptive components:

- **Error (E)** – How new observations adjust the model (usually Additive)
- **Trend (T)** – Direction of movement: None (N), Additive (A), or Additive Damped
  (Ad)
- **Seasonality (S)** – Repeating cycles: None (N), Additive (A), or Multiplicative
  (M)

These models are effective for financial planning and operational forecasting because they
automatically update as new data arrives and can flexibly represent a variety of real‑world
patterns

## Holt–Winters Model Variants

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Model Name** | **ETS Notation** | **Trend Type** | **Seasonality Type** | **When to Use** |
| Simple Exponential Smoothing Model | ANN | None | None | For stable data with no trend or seasonality. |
| Additive Seasonality Model | ANA | None | Additive | When seasonal effects are constant in size. |
| Multiplicative Seasonality Model | ANM | None | Multiplicative | When seasonal effects scale with the data level. |
| Holt’s Linear Trend Model | AAN | Additive | None | When data has a steady upward or downward linear trend. |
| Holt’s Damped Trend Model | AAdN | Additive Damped | None | When the trend exists but is expected to flatten over time. |
| Additive Holt–Winters Model | AAA | Additive | Additive | For trend + constant magnitude seasonality. |
| Multiplicative Holt–Winters Model | AAM | Additive | Multiplicative | For trend + proportional seasonal variations. |
| Damped Additive Holt–Winters Model | AAdA | Additive Damped | Additive | When trends are flattening and seasonality is constant. |
| Damped Multiplicative Holt–Winters Model | AAdM | Additive Damped | Multiplicative | When trend levels off and seasonality scales with data. |

## Naive Forecasting Model

The Naive model is the most straightforward forecasting approach: it simply carries the
latest historical value forward into future periods.

For financial planners, this method is especially helpful when:

- The data is volatile, erratic, or difficult to predict
- Recent results are the best indicator of short‑term future performance
- You need a clear baseline forecast to compare against more advanced models.

It requires no configuration and reacts immediately to sudden shifts, making it a
dependable “quick estimate” model.

## Linear Regression Model

The Linear Regression model identifies a **straight‑line trend** in your historical data
and extrapolates it into the future.

For financial planning scenarios, this model is valuable when:

- Your data shows a consistent upward or downward trend over time,
- You want forecasts that reflect planned drivers (e.g., growth factors, business events,
  budget assumptions),
- You need explainable forecasts, since regression clearly shows how time or drivers
  impact the results.

It’s a practical model for budgeting and planning cycles where growth, decline, or
operational factors influence future values.

## Statistical Details

Statistical Details provide technical insight into how the forecast was generated and how
reliable it is. These details are intended for users who want to understand the model
behavior behind the predicted values.

## Accuracy Details

These metrics measure how far off the predictions were from the test portion of your
historical data. Lower numbers are better for all error metrics.

|  |  |  |  |
| --- | --- | --- | --- |
| **Metric** | **Range** | **Description** | **How to use/Interpret** |
| **MAE** (Mean Absolute Error) | 0 to any positive number | The average difference between the model’s predicted values and the historical actuals. | Lower MAE indicates that the model stays closer to historical patterns. Useful for understanding the overall consistency of predictions. |
| **MAPE** (Mean Absolute Percentage Error) | 0.0 to any positive number (expressed as a percentage) | The average forecasting error expressed as a percentage of historical values. | Helps compare accuracy across items with different scales. Typical interpretation ranges:  • **0–10%:** Very accurate  • **10–20%:** Good  • **20–50%:** Acceptable  • **50%+:** Low accuracy  Note: Not reliable when historical values are very small or zero. |
| **MASE**  (Mean Absolute Scaled Error) | 0.0 to any positive number, or **“Infinity”** | Compares your model's error to a simple baseline forecast that repeats the last historical value. | Typical interpretation ranges:  - **Less than 1.0****:** Model performs better than the baseline - **Equal to 1.0**: Performs the same as the baseline - **Greater than 1.0****:** Baseline performs better - **Infinity:** All historical values are constant; baseline is most   appropriate |
| **RMSE** (Root Mean Square Error) | 0 to any positive number | Similar to MAE but gives more weight to larger errors (big misses). | - RMSE close to MAE → forecast errors are steady and consistent - RMSE much higher than MAE → data has spikes or occasional large errors |
| **Accuracy Score** | 0 to 100 (percentage scale) | A combined score that reflects the overall accuracy of the model based on multiple error metrics. Higher scores indicate better model performance relative to alternatives. | Typical interpretation ranges:  - **90-100%:** Excellent - Highly reliable forecast - **75-89%:** Good - Reliable forecast - **60-74%:** Fair - Use with caution - **Below 60%:** Poor - Forecast may not be reliable |

Use the guidelines below to quickly identify which model provides the most reliable
results.

- **Accuracy Score:** Higher values indicate better overall accuracy.
- **MAPE:** Lower values are better.
- **MASE:** Lower values are better (ideally **less than 1.0**).
- **MAE / RMSE:** Lower values indicate the model is closer to your historical
  data.

## Parameters

Parameters determine how much the model relies on recent values versus longer‑term trends
and seasonal patterns.

**Alpha (Level Smoothing)**

Controls how much weight is given to the most recent value when estimating the overall
level of the data.

- **Lower Alpha** → heavier smoothing; the model relies more on long‑term history.
- **Higher Alpha** → lighter smoothing; the model reacts more strongly to recent
  changes.
- **Alpha = 1** → only the latest data point is used for the level.

**Beta (Trend Smoothing)**

Controls how quickly the model updates its estimate of the trend over time.

- Behaves similarly to Alpha but specifically affects the trend component.
- Higher Beta makes the model more responsive to recent changes in trend; lower Beta
  stabilizes it.

**Gamma (Seasonal Smoothing)**

Controls how the model updates seasonal patterns (for example, quarterly or monthly
seasonality).

- Similar in behavior to Alpha but applied to the seasonal component.
- Higher Gamma updates seasonality based on recent periods; lower Gamma smooths seasonal
  effects over longer history.

## Trend and Seasonality

These indicators show how much trend and seasonality influence the model’s accuracy. They
help you identify whether the data contains meaningful upward or downward movements, or
repeating patterns over time.

|  |  |  |  |
| --- | --- | --- | --- |
| **Metric** | **Range** | **Description** | **How to use/Interpret** |
| Trend Strength | 0.0 to 1.0 | Indicates how much the trend component improves the model’s accuracy. Calculated by comparing the original model to the same model with the trend removed. | Typical interpretation ranges: • **0.0:** No meaningful trend  • **0.0–0.3:** Weak trend  • **0.3–0.7:** Moderate trend  • **0.7–1.0:** Strong trend; |
| Seasonality Strength | 0.0 to 1.0 | Indicates how much the seasonal component improves the model’s accuracy. Calculated by comparing the original model to the same model with the seasonal component removed. | Typical interpretation ranges: • **0.0:** No seasonal pattern  • **0.0–0.3:** Weak seasonality  • **0.3–0.7:** Moderate seasonality  • **0.7–1.0:** Strong, consistent seasonal patterns |
