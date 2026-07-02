---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Forecast"
breadcrumb:
  - "Cloudability Premium"
  - "Plan"
  - "Budgets and Forecasts"
source_path: "product/bf-forecast.html"
images:
  - "images/forecast-details.jpg"
  - "images/forecast-homepage.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Forecast

This feature allows you to see historical spending patterns and inspect the underlying changes
that are driving your forecasted spend so that you can understand what is expected to change. It
also helps you to create additional budgets.

Use Case

You might use the six-month trend to create a reasonable stretch goal budget for your team which
is less than the plan from your finance team. With Cloudability, it's easy to share this budget with
your team, receive updates on your progress, and see Plan vs. Actual reporting on your progress to
date.

Customize Forecast Dashboard

Navigate to  Plan  >  Forecast

![budgets and forecasting screenshot](../../../../03-media/cloudability-premium/images/forecast-homepage.jpg)

Select Details button to see the forecast details.

![forecast details screenshot](../../../../03-media/cloudability-premium/images/forecast-details.jpg)

You can perform the following actions:

- Modify the view by selecting appropriate values for any of the parameters, like cost basis,
  forecast model, and so on.
- Export tabular data, either via the UI or the API, to a financial management tool of your
  choice.
- Save the forecast as a  [budget.](bf-budgets.html)

FAQ

Why am I seeing a message about "missing cost data" for this month?

AWS typically sends updated billing files every four hours. Occasionally, particularly in the
first and last few days of the month, it can take longer. We'll show you your estimate based on the
most recent data, but when we haven't received a billing file from Amazon for a given month, we'll
show an incomplete data banner.

**Parent topic:** [Budgets and Forecasts](../product/plan-and-manage-your-budgets-and-forecasts.html)
