---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Understand Model Metrics (Cost, Budget, Forecast)"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Model Basics"
source_path: "studio/new-uc/howtoguides/build-cost-model/understand-model-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Understand Model Metrics (Cost, Budget, Forecast)

|  |  |
| --- | --- |
| **Content Type** | How-To Guide / Conceptual |
| **Target Audience** | Business Analysts, IT Finance Teams |
| **Time Estimate** | 10-15 minutes |
| **Prerequisites** | Basic understanding of TBM Studio; familiarity with financial concepts |

## Objective

Understand what model metrics are, how the core metrics (Cost, Budget, Forecast) work, and
how they flow through allocations in your cost model.

## When to Use This Information

This conceptual guide helps you when:

- Setting up a new model and deciding which metrics to track
- Configuring allocations that apply to specific metrics
- Interpreting model reports that display multiple metrics
- Creating variance reports that compare Cost vs. Budget
- Troubleshooting why certain values are not flowing as expected

## What Are Model Metrics?

A **model metric** is a numeric value that flows through your cost model via
allocations. While TBM Studio supports many types of metrics, three are foundational to most
IT financial management:

|  |  |
| --- | --- |
| **Metric** | **Description** |
| **Cost** | Actual incurred expenses. This is typically the primary metric in a TBM model, sourced from your general ledger, invoices, or other financial systems. Cost represents what you have actually spent. |
| **Budget** | Planned or allocated spending amounts. Budget represents what you intended to spend, typically set during annual planning. Comparing Budget to Cost reveals variances. |
| **Forecast** | Projected future spending based on current trends. Forecast is typically updated throughout the year as actual spending patterns emerge, providing a more accurate view of where costs are heading. |

Your organization may also use additional metrics such as CapEx (capital expenditures),
utilization, or custom metrics specific to your business needs.

## Model Metrics vs. Calculated Metrics

TBM Studio supports two types of metrics:

**Model metrics** (also called modeled metrics) originate in your source data and flow
through allocations. Cost, Budget, and Forecast are typically model metrics. They are the
raw values that enter your model at the lowest tier (like Cost Source) and propagate upward
through each allocation step.

**Calculated metrics** are derived from model metrics using formulas. For example, you
might create a "Budget Variance" calculated metric defined as Budget minus Cost. Calculated
metrics do not flow through allocations — they are computed at the reporting layer.

**Note:** Model metrics sum when grouping data. Calculated metrics recalculate using
their formulas. This distinction matters when aggregating data across time periods or
hierarchies.

## How Metrics Flow Through Allocations

When you create an allocation, you specify which metrics it applies to. Here is how the
flow works:

1. **Unit drivers bring value in.** At your cost source table (the bottom tier of your
   model), unit drivers pull values from columns in your data. For example, a unit driver
   might reference the "Amount" column to bring Cost into the model.
2. **Allocations distribute value.** Each allocation takes value from one table and
   distributes it to another based on weighting rules. For instance, you might allocate Cost
   from Cost Source to Vendors based on vendor invoice amounts.
3. **Metrics propagate independently.** If you configure an allocation to apply to both
   Cost and Budget, each metric flows separately. Cost values go from source to target using
   the allocation weights, and Budget values do the same — maintaining their separate totals
   throughout the model.
4. **Values cascade through tiers.** As you build a multi-tier model (Cost Source →
   Vendors → Technology Services → Business Units), metrics flow through each layer,
   accumulating and distributing based on your allocation rules.

## Viewing Metrics in the Model

You can switch between metrics when viewing the model:

1. Open a model object by clicking its Model step in the transform pipeline.
2. Look for the metric selector at the top of the model pane. This dropdown shows all
   available metrics (Cost, Budget, Forecast, etc.).
3. Select a different metric to see how that value flows through the model. The Sankey
   diagram widths update to reflect the selected metric's values.

Tip: When building model reports, you can select which metrics to include using
the Edit Metrics button in the Tier Editor. Including fewer metrics improves calculation
performance.

## Creating and Managing Metrics

Metrics are defined at the project level and appear in the Metrics section of Project
Explorer. To create a new metric:

1. On the Home tab, click **New**, then click **Metric**.
2. Enter a name and click **OK**.
3. Configure the metric properties, including the model type (Model or Calculated),
   formatting, and metric type (Costing, Pricing, or Numeric).
4. Save and check in the metric.

## Key Metric Properties

**Model Type:** Choose "Model" for metrics that flow through allocations, or
"Calculated" for formula-based metrics.

**Metric Type:** Choose "Costing" for monetary values from fully costed sources (like a
general ledger), "Pricing" for price × quantity models, or "Numeric" for non-monetary
values.

**Table Format:** Controls how the metric appears in reports. Use =Currency($\_) for
monetary values to display as dollars.

**Time Behavior:** Determines how the metric aggregates across time periods — Sum,
Average, or Recalculate.

## What's Next

- [Set up allocations](setup-sa.html) to flow metrics between tables
- Create calculated metrics for variance analysis — see [Model Studio Reference](../../reference/model-studio-ref.html)
- Learn more about metric properties and formulas — see [Model
  Architecture](../../concepts-architecture/model-architecture/model-concepts-overview.html).

## Related Concepts

- [Model Architecture](../../concepts-architecture/model-architecture/model-concepts-overview.html) — Detailed explanation of how the allocation engine processes
  metrics
- [Formulas and Functions](../../reference/formula-function.html) — Creating
  calculated metrics with formulas

**Parent topic:** [Model Basics](../../../../studio/new-uc/howtoguides/build-cost-model/model-basics.html)
