---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Model Validation and Tracing"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Model Architecture"
source_path: "studio/new-uc/concepts-architecture/model-architecture/model-validation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Model Validation and Tracing

Once your model is configured and has been calculated, the next critical step is validating that
costs flow correctly and that your allocation results are reasonable and auditable.

## Model Validation

Validation is the process of checking that your model produces accurate, complete, and balanced
results. There are three types of validation checks to perform.

**Balance Checks**

The most fundamental check: do your source totals equal your target totals? If you started with
$5 million in Cost Source, the sum of all final target objects should also be $5 million (minus any
intentional unallocated amounts).

- **What to check:** Sum of source object values should equal the sum of final target object
  values plus any unallocated amounts
- **If they don’t balance:** Look for over-allocations (Standard Value type can over-allocate),
  misconfigured formulas, or data quality issues

**Completeness Checks**

Verify that all expected data has flowed through the model. This means checking that every source
row was processed, every model object received input, and no allocations were silently skipped due
to configuration issues.

- Review unallocated cost amounts at each tier (not just the first)
- Verify that intermediate objects have non-zero values
- Check that all expected time periods are present in the results

**Reasonableness Checks**

Even when a model balances and is complete, the results may not be reasonable. Compare current
results against prior periods, budgets, or external benchmarks to identify anomalies.

- Did any business unit’s costs change by more than 20% month-over-month without a known cause?
- Are per-unit costs (cost per server, cost per application) within expected ranges?
- Do the relative proportions across business units match expectations?

## Cost Tracing

Cost tracing is the ability to follow a specific cost from its source to its final destination
(forward tracing) or from a final number back to its origins (backward tracing). This is essential
for auditing, stakeholder questions, and troubleshooting.

**Forward Tracing: Where Did This Cost Go?**

Starting from a known source (e.g., a specific vendor invoice), trace its path through the model
to see which business units ultimately received portions of that cost. TBM Studio’s diagram view and
the Single Object Modeler both support forward navigation through the allocation chain.

**Backward Tracing: Where Did This Cost Come From?**

Starting from a final number in a report (e.g., Engineering’s $1.8M allocation), trace back
through the model to understand which source costs contributed. This is the question stakeholders
most frequently ask: “Why does my department’s IT cost look this way?”

Note:

**Tracing Best Practice**

Document your model’s allocation logic in plain language alongside the technical configuration.
When a finance director asks “Why did my costs go up?”, having a narrative explanation ready (“Your
department added 15 servers in March, increasing your share of datacenter costs”) is far more
effective than walking them through the technical model.

## Model Reports (Sankey Diagrams)

TBM Studio provides Model Reports, which use Sankey-style visualizations to show cost flows in an
intuitive, visual format. These are distinct from standard Report Studio reports and are
specifically designed for model validation and stakeholder communication.

**Sankey diagram features:**

- Displays costs flowing through defined layers (e.g., Financials → Cost Pools → Infrastructure →
  Services)
- Line width is proportional to cost value, making large flows immediately visible
- Click any flow line to drill through to the underlying transaction-level detail
- Toggle between Sankey visualization and tabular data view
- Supports multiple columns per layer for granular analysis

**When to use Model Reports:**

- **Validation:** Verify that costs flow as expected through each tier
- **Communication:** Show stakeholders how their costs are derived in an intuitive visual
  format
- **Auditing:** Drill into specific flow lines to trace individual cost items
- **Onboarding:** Help new team members understand the model structure quickly
