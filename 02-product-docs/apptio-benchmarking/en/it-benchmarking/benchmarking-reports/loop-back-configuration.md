---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "When to loop back to configuration or methodology"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
source_path: "it-benchmarking/benchmarking-reports/loop-back-configuration.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# When to loop back to configuration or methodology

If a report looks off, it might be:

- Configuration
- Data quality
- Real performance

You need to know when to pull in [Configuration Guide](../home.html#benchmarking__config_guide) or [Data &
Methodology Reference](../home.html#benchmarking__data-methodology) sections.

Escalate back to [Configuration Guide](../home.html#benchmarking__config_guide) when:

- Whole Resource Towers or Cost Pools are blank when they should have cost.
- You see obvious unit mix-ups (for example costs that imply 10x too many or too few
  servers).
- Benchmark values change drastically after model changes in Costing.

Escalate back to [Data & Methodology
Reference](../home.html#benchmarking__data-methodology) when:

- People question what exactly is included in a metric.
- There is confusion about peer group or percentiles.
- Someone asks if a comparison is valid given scope or accounting differences.

If you cannot explain a metric in plain language, treat that metric as advisory until you either
fix configuration, refine scope, or get comfortable with the methodology.
