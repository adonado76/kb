---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Infrastructure benchmark reports in Interactive Benchmarking"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
source_path: "it-benchmarking/benchmarking-reports/infrastructure-benchmarking-reports.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Infrastructure benchmark reports in Interactive Benchmarking

These answer “How efficient are our core infrastructure towers compared to peers?”

## Unit Costs

![#: Interactive Benchmarking’s Infrastructure Benchmarks report’s Unit Costs tab](../../resources/images/it%20benchmarking_images/unit-cost.png)

Practical benefits:

- Translate infrastructure spend into a real, comparable unit metric.
- Compare your actuals to an expected peer benchmark at your scale.
- Get scale-adjusted benchmarking, not lazy averages.

## FTE Efficiency

![Interactive Benchmarking’s Infrastructure Benchmarks report’s FTE Efficiency tab](../../resources/images/it%20benchmarking_images/fte-efficiency.png)

Practical benefits:

- Benchmark productivity, not just cost.
- Separate “high cost” from “low productivity”.
- Get an implied “right-sized” FTE estimate.
- Drive targeted operational improvements.

## How to read them

Pay attention to:

- **Unit definitions**: Is it per physical server, per VM, per vCPU, per TB of usable capacity,
  and so on?
- **Scope**: What costs are included in the tower, and what is explicitly excluded?
- Where your value sits relative to the median and quartiles?

If you are significantly above benchmark:

- Check cost and volume alignment:
  - Same period
  - Same scope
  - Correct units
- If that holds, talk with Resource Tower Owners about:
  - Design choices and resilience targets
  - Legacy footprint,
  - Sourcing and tooling.

If you are significantly below benchmark:

- Confirm you are not undercounting costs or overcounting volumes.
- If valid, this is a strength, but check you are not achieving it by underinvesting in
  reliability or security.

Infra benchmarks are the right place to ground detailed tower improvement plans.
