---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Interpretation guidelines and caveats"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Data and Methodology Reference"
source_path: "it-benchmarking/data-and-methodology/interpretation-guidelines.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Interpretation guidelines and caveats

This is the part that prevents bad decisions.

## Valid comparisons vs invalid comparisons

Generally valid:

- Comparing your organization to peers that share industry, size band, and region
- Comparing towers that are in scope and mapped consistently
- Comparing unit costs where both cost and volume definitions match

Risky or invalid:

- Cross industry comparisons with wildly different business models
- Comparing a partial scope of IT to full scope benchmarks
- Mixing different accounting treatments without adjustment

If the underlying concept of “peer” does not hold, the metric is at best directional.

## Scope mismatches

Common scope differences:

- Some organizations include telecom and operational technology in IT, others do not
- Shared services may be fully allocated into IT in some cases and left in corporate overhead in
  others
- Cloud and SaaS costs may be centralized in IT in some organizations and distributed in
  others

When you see a large gap:

- First verify scope and mapping
- Only then label it as performance difference

## Structural differences

Benchmark gaps can reflect:

- Real inefficiency
- Strategic choices (higher service levels, more resilience)
- Different sourcing decisions (insource vs outsource, cloud vs on premise)
- Legacy footprint and technical debt

Being above benchmark is not automatically “bad.” Being below is not automatically “good.” The
question is whether the difference is justified and understood.

## Data quality limitations

There are two sides to data quality:

- Peer data quality – governed by provider rules and sample thresholds
- Your data quality – governed by your TBM model, mapping, and volume sources

Watch for:

- Entire towers or metrics missing for you
- Year over year swings that clearly come from remapping, not operations
- Volumes that have not been updated in years

Use benchmarks to highlight where detailed data review is needed, not just where to cut.
