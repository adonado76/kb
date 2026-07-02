---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Data quality and validation routines"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Operations and Governance"
source_path: "it-benchmarking/operations-governance/data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Data quality and validation routines

Benchmarks are a good way to flush out modeling issues. Use that instead of hiding them.

## Annual validation

At each annual refresh:

- Compare **IT OpEx structure** vs prior year:
  - Large shifts should correspond to real events (migrations, restructuring) or explicit modeling
    changes.
- Compare **key infra unit costs** vs prior year:
  - Big jumps warrant a check on both cost and volume data.
- Reconcile **IT spend vs revenue ratios** with Finance to ensure level-set.

If a jump is due to a TBM model change, clearly label that year as a “structure change” in your
documentation or commentary.

## Sanity checks before executive use

Before any major meeting:

- Confirm peer filters reflect the story: industry, size band, region, year.
- Make sure you can answer:
  - What is included in this metric?
  - Who are we compared to?
  - Is this gap likely real, or data-driven?

If you cannot answer those in plain language, do not use that view yet. Fix config or revisit
the metric in [Data & Methodology
Reference](../home.html#benchmarking__data-methodology).
