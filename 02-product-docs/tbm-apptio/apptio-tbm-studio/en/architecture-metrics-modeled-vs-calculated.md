---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Metrics: Modeled vs. Calculated"
breadcrumb:
  - "Concepts and Architecture"
  - "Model Architecture"
  - "Metrics: Modeled vs. Calculated"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/model-architecture/metrics-modeled-calculated.html"
images:
  - "03-media/apptio-tbm-studio/model-metric-flow.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Metrics: Modeled vs. Calculated

Metrics are the numeric measurements that flow through your model and appear in your reports. TBM Studio supports two fundamentally different types of metrics, and understanding the distinction is critical for building effective cost models.

## Modeled Metrics

A modeled metric is a core numeric value that participates directly in the allocation engine. When costs are allocated from one object to another, modeled metrics are the values being distributed.

- Cost: Actual expenditure — the most common metric and the default in every project
- Budget: Planned expenditure for comparison against actuals
- Forecast: Projected future expenditure
- Custom metrics: Any additional allocatable value you define, such as CapEx, headcount, or utilization

How Modeled Metrics Flow

![Model Metric Flow](../../../../resources/images/studio_images/model-metric-flow.png)

- Each model object stores its own set of modeled metric values per time period
- Metrics originate from transform tables (Data Studio) and propagate through allocations
- When grouping data in reports, modeled metrics sum their values
- Modeled metrics cannot calculate across time periods — they represent single-period values
- There is one model per project, but that model can carry multiple modeled metrics

## Calculated Metrics

A calculated metric is derived from a formula that references modeled metrics, table columns, or other calculated metrics. Calculated metrics do not participate in the allocation engine — they are computed at reporting time.

| Pattern | Formula Example | Purpose |
| --- | --- | --- |
| Pattern | Formula Example | Purpose |
| Variance | = Budget - Cost | Show the gap between planned and actual spending |
| Variance % | = (Budget - Cost) / Budget | Show over/under-spend as a percentage |
| Per-unit cost | = Cost / ServerCount | Normalize costs for comparison across different-sized entities |
| Year-to-date | = YearToDate(CapEx) | Aggregate a modeled metric from the start of the fiscal year to the current period |
| Cost share | = Cost / SUM(Cost) | Show what percentage of total cost each entity represents |

- Defined under Metrics in Project Explorer and available to all reports in the project
- Formulas are evaluated during reporting calculations, not during model calculations
- When grouping data, calculated metrics recalculate (they do not sum) unless explicitly marked as summable
- Can calculate across time periods using time-intelligent functions like YearToDate, MonthToDate
- Changing a formula requires checking out the metric and checking it back in
- Cannot be converted to modeled metrics or vice versa

## Metric Decision Guide

| You Need... | Metric Type | Why |
| --- | --- | --- |
| You Need... | Metric Type | Why |
| Raw cost data that flows through allocations | Modeled Metric | Only modeled metrics participate in the allocation engine |
| A mathematical combination of other metrics | Calculated Metric | Formulas reference modeled metrics and compute derived values |
| Data that aggregates across time (YTD, TTM) | Calculated Metric | Time-intelligent functions only work in calculated metrics |
| A value used across many areas at different levels | Modeled Metric | Modeled metrics apply across the full model hierarchy |
| A single-purpose reporting calculation | Calculated Metric | Keep reporting logic separate from model logic |
| Categorical data (labels, names, codes) | Dimension/Column | Non-numeric attributes belong as table columns, not metrics |

Common Misconception

Calculated metrics do not modify model flows. If you create a calculated metric that divides Cost by Budget, that calculation only appears in reports. It has no effect on how costs are allocated. If you need a value to participate in allocations, it must be a modeled metric.
