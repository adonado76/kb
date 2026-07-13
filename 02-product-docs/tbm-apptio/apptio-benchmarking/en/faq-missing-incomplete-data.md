---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Missing or incomplete data"
breadcrumb:
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
  - "Missing or incomplete data"
source_path: "SSIU957/it-benchmarking/troubleshooting/missing-data.html"
images: []
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Missing or incomplete data

Entire charts or tables are blank

- No IT cost or profile data for the selected year
- Benchmarking is pointing at the wrong year or Costing project
- Peer group settings exclude your org or hide the metric
- Domain (Industry / OpEx / Infra) not fully enabled

1. Confirm your organizational profile and cost data exist for that year.
1. Check Benchmarking configuration for the active year and Costing project.
1. Relax filters (industry, size, region) to see if the metric reappears.
1. Confirm the relevant domain is enabled and not in an error state.

Some Resource Towers or Cost Pools are missing spend

- Those costs are mapped to custom Resource Towers or Cost Pools that aren’t aligned to standard TBM categories
- Spend sits in a Costing project that Benchmarking is not using
- Benchmark dataset doesn’t support that Resource Tower for the chosen peer group

1. In Costing, confirm those Resource Towers / Cost Pools have non-zero cost for the selected year.
1. Verify mapping from local structures to standard Cost Pools / Resource Towers used by Benchmarking.
1. Check which Costing project Benchmarking is configured to use and whether the spend is in that project.

Short answer you can send The Resource Tower or Cost Pool isn’t showing because it’s either mapped to a non-standard category that doesn’t line up with the benchmark taxonomy, or it sits in a Costing project that Benchmarking isn’t using. Once we align the mapping and source, it will show in the benchmark views.

Infrastructure metrics do not appear, but OpEx does

- Volume or capacity data missing for infra-related Resource Sub-Towers
- Resource Sub-Towers not mapped cleanly to benchmark definitions

1. Verify cost and volume data for infra Resource Sub-Towers (servers, storage, network, etc.).
1. Check units (for example TB vs GB, physical vs virtual servers).

Short answer you can send Infra benchmarks are not available yet because we haven’t completed the cost and volume mapping for the infrastructure Resource Towers. Once that’s in place, the infra unit cost metrics will populate.
