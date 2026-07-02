---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Benchmark-enabled reports in Costing"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
source_path: "it-benchmarking/benchmarking-reports/benchmark-enabled-report.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Benchmark-enabled reports in Costing

These are reports enabled in your Costing project, if the relevant component is installed and
integration with Interactive Benchmarking is established, that include benchmark values in context
of your model.

**What they add**  
Compared to standalone Benchmarking views, they let you:

- See actual vs benchmark in one place
- Drill from the benchmark down to accounts, services, vendors, or applications
- Reconcile with Finance and tower owners using the same cost base

They are especially useful when:

- You want to move from “our unit cost is high” to “here is where, who, and what to change.”
- You need to show that a proposed initiative targets the drivers of the gap.

**Typical report patterns**  
Common patterns:

- **Resource Tower scorecards**
  - Each row is a Resource Tower or Sub-Tower.
  - Columns include your unit cost, benchmark, variance, and possibly RAG status.
- **Variance breakdowns**
  - A single Resource Tower, broken down by Cost Pool, vendor, region, or service.
  - Shows which pieces drive the difference to the benchmark.
- **Application level views**
  - Where applications map cleanly to infra drivers, cost per app can be compared to a relevant
    benchmark band.

![Costing’s Industry & OpEx Benchmarks report’s Application Distribution tab](../../resources/images/it%20benchmarking_images/benchmark-report-distribution-tab.png)

Use these when you want a clear line from…  
“We are above benchmark for cost per TB.”
to “These storage arrays, contracts, or regions are the main levers.”
