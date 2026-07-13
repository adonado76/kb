---
concept: "Intelligent Forecasting — automated time-series forecasting"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-planning
status: draft
generated_from:
  - 02-product-docs/apptio-planning/en/it-planning/planning/intelligent-forecasting.md
last_updated: "2026-07-02"
---
# Intelligent Forecasting — How IBM Apptio Planning Reduces Manual Forecasting Effort

## The capability

Traditional IT forecasting is manual and inconsistent between planners: each budget owner applies
their own judgment (or a flat percentage bump) to project future spend, with no shared methodology
and no way to distinguish a genuine trend from a one-time anomaly in the historical data.
Intelligent Forecasting introduces "advanced time-series forecasting techniques into Apptio
Planning, empowering teams to produce more accurate, consistent forecasts with less manual
effort."

## How IBM Apptio Planning covers it

The feature analyzes each line item's historical spend pattern and automatically selects the most
suitable statistical model for it — evaluating "a diverse set of statistical models... ranging
from adaptive smoothing methods to baseline and regression-based approaches" to capture different
data behaviors (growth trends, seasonality, volatility, linear relationships).

Three things distinguish this from a black-box forecast:

- **Outlier detection** — historical anomalies (one-time spikes, drops, or data entry errors) are
  surfaced explicitly, with a defined mechanism: an outlier is "any data point within the last 20%
  of your historical values that falls outside the model's confidence range." Planners can adjust
  these before the model trains on them, rather than having a single bad month permanently skew
  every forecast that follows.
- **Full transparency and editability** — planners can inspect model settings and smoothing
  parameters, review a Prediction Accuracy score, and compare multiple candidate models side by
  side before applying one. Forecasts remain fully editable after generation — the system proposes,
  it doesn't dictate.
- **Broad expense-type coverage** — supported for Other/Summary expenses, Labor and Labor Activity
  (forecasting headcount or hours directly), and contracts/assets under manual amortization or
  depreciation — covering most of the expense types a typical IT budget actually contains.

A minimum of three months of historical data is required to run a forecast, and — worth setting
expectations on — the feature currently does **not** apply to external lines, generated
financials, submitted expenses, or actuals; support for using actuals as forecast input and for
forecasting on grouped expenses is documented as planned for a future release, not available today.

## Why this matters in a client conversation

This capability directly attacks forecast inconsistency — a common source of friction when
multiple budget owners each apply their own informal method and Finance has to reconcile wildly
different assumptions during consolidation. Automated model selection with a visible accuracy
score gives every planner the same disciplined starting point, while the outlier adjustment
workflow keeps a single bad month (a one-time vendor overcharge, a data entry error) from
permanently distorting a multi-year forecast trend.

An honest scoping note for any proposal: this is presently an **enhancement to manual forecast
input**, not a fully automated actuals-to-forecast pipeline — a planner still reviews, adjusts, and
explicitly applies each model. That's a feature, not a limitation, for organizations that want
forecast accountability to remain with a named owner, but it should be positioned accurately rather
than as "hands-off AI forecasting."

## Source documents

- Intelligent Forecasting Overview — `02-product-docs/apptio-planning/en/it-planning/planning/intelligent-forecasting.md`