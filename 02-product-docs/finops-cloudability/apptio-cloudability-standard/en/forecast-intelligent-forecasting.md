---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Intelligent Forecasting"
breadcrumb:
  - "Plan"
  - "Enhanced Forecast"
  - "Intelligent Forecasting"
source_path: "SSVCLNQ/product/intelligent-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Intelligent Forecasting

## Overview

Features such as the Enhanced Forecast Page and Cloudability Financial Planning use the Intelligent Forecast Engine to generate forecasts from historical time-series data. The Intelligent Forecast Engine evaluates multiple forecast models to identify the model that best matches each historical time series. These models are designed to capture different types of behavior in time-series data, such as stable values, linear growth or decline, repeating seasonal patterns, and changes in variability over time. By supporting multiple model types, the engine can generate forecasts that are more accurate, explainable, and adaptable across different scenarios.

Forecast accuracy generally improves when more historical data is available, because the models can better identify recurring seasonal patterns, longer-term trends, and underlying variability. A richer historical data set gives the engine more context for selecting the best-fitting model and producing a more stable forecast.

The Intelligent Forecast Engine supports several forecast model types, including Baseline, Linear Trend, Moving Average, and selected ETS models. These models are designed to fit different historical patterns in the data and use different settings or parameters depending on how they work.

The Intelligent Forecast Engine runs all supported model types against each forecast item and selects the model that performs best for the historical pattern in that item.

Learn more about how Intelligent Forecasting works

## Forecast model types

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

## Forecast model comparison

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

## Forecast model parameters

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

## Trend and seasonality indicators

ETS model results may also include Trend Strength , Seasonality Strength , and Seasonal Period indicators. These values help show how much the trend and seasonal components contribute to model accuracy and how frequently seasonal patterns repeat.

| Indicator | Range | Description | Typical interpretation |
| --- | --- | --- | --- |
| Trend Strength | 0.0 to 1.0 | Indicates how much the trend component improves model accuracy. It is calculated by comparing the original model to the same model with the trend removed. | 0.0 = no meaningful trend 0.0-0.3 = weak trend 0.0-0.3 = weak trend 0.7-1.0 = strong trend |
| Seasonality Strength | 0.0 to 1.0 | Indicates how much the seasonal component improves model accuracy. It is calculated by comparing the original model to the same model with the seasonal component removed. | 0.0 = no seasonal pattern 0.0 = no seasonal pattern 0.3-0.7 = moderate seasonality 0.7-1.0 = strong, consistent seasonal patterns |
| Seasonal Period | Positive integer | Indicates the number of time periods in one full seasonal cycle used by the model. For example, a value of 12 represents a yearly cycle in monthly data, while a value of 7 represents a weekly cycle in daily data. | Higher values indicate a longer repeating cycle. |

These indicators can help explain why a model that includes trend or seasonality was selected. Higher Trend Strength and Seasonality Strength values suggest that the corresponding component contributes more meaningfully to forecast accuracy, while Seasonal Period indicates the length of the repeating cycle identified in the data.

## How Intelligent Forecasting works

When the Intelligent Forecast Engine generates a forecast, it does not rely on a single model or fixed parameter values. Instead, it fits each supported model to the historical pattern for the forecast item, determining the model values, settings, or parameters needed to best match that pattern. This fitting process takes place before the engine evaluates model results and selects the best-performing model.

Some models use relatively simple structures. For example, a Moving Average model uses a window length, and a Linear Trend model uses the fitted slope and intercept of the historical trend line. ETS models are more adaptive and use one or more smoothing parameters, such as alpha (α), beta (β), gamma (γ), and phi (φ), depending on whether the model includes level, trend, seasonality, or damped trend.

For those ETS models, the Intelligent Forecast Engine uses an iterative process to calculate the parameter values that best fit the observed pattern in the historical data for the forecast item.

Higher or lower parameter values change how responsive the model is to new observed values. For example, a higher alpha makes the estimated level react more quickly to recent changes in the data, while a lower alpha makes the level change more gradually.

Once optimal parameter values have been chosen for each model, the Intelligent Forecast Engine evaluates the models to determine which one performs best against the historical data. Using a machine learning approach, it applies each model to an earlier portion of the historical data, compares the resulting forecasted values for a later portion of the same series to the known observed values, and computes the symmetric mean absolute percentage error (SMAPE). It then converts that result into an accuracy score and selects the model with the highest accuracy score.

A simpler model such as Baseline or Moving Average may perform best for a stable pattern, while a more advanced ETS model may perform better for data that includes trend, seasonality, or both. By testing candidate models against a known portion of the input series and scoring them consistently, the engine can select the model that is most likely to produce the most accurate future forecast for that item.

The Intelligent Forecast Engine generates forecasts that adapt to different types of time-series behavior. A stable pattern may be best represented by a simpler model, while a more dynamic or seasonal pattern may require a model with trend and seasonal parameters tuned to that specific history. A pattern may also start as stable and evolve over time into one that requires a more complex model.

Because the Intelligent Forecast Engine selects both the best-performing model and the parameter values that best match the historical pattern, it can generate forecasts that are tailored to each forecast item rather than relying on one fixed approach for all data.
