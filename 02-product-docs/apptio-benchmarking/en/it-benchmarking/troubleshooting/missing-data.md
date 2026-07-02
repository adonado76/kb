---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Missing or incomplete data"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
source_path: "it-benchmarking/troubleshooting/missing-data.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Missing or incomplete data

**Entire charts or tables are blank**

Symptom  
A view loads, but all values for your organization are blank.
  
Likely causes

- No IT cost or profile data for the selected year
- Benchmarking is pointing at the wrong year or Costing project
- Peer group settings exclude your org or hide the metric
- Domain (Industry / OpEx / Infra) not fully enabled

What to check

1. Confirm your organizational profile and cost data exist for that year.
2. Check Benchmarking configuration for the active year and Costing project.
3. Relax filters (industry, size, region) to see if the metric reappears.
4. Confirm the relevant domain is enabled and not in an error state.

Short answer you can send  
This chart is blank because there’s no benchmarkable data
for us in the selected year and peer group. Once we update the underlying data or adjust the peer
group, the values will appear.

**Some Resource Towers or Cost Pools are missing spend**

Symptom  
You know there is spend in certain Resource Towers or Cost Pools in Costing,
but they do not show up in Benchmarking.  
Likely causes

- Those costs are mapped to custom Resource Towers or Cost Pools that aren’t aligned to standard
  TBM categories
- Spend sits in a Costing project that Benchmarking is not using
- Benchmark dataset doesn’t support that Resource Tower for the chosen peer group

What to check

1. In Costing, confirm those Resource Towers / Cost Pools have non-zero cost for the selected
   year.
2. Verify mapping from local structures to standard Cost Pools / Resource Towers used by
   Benchmarking.
3. Check which Costing project Benchmarking is configured to use and whether the spend is in that
   project.

Short answer you can send  
The Resource Tower or Cost Pool isn’t showing because it’s
either mapped to a non-standard category that doesn’t line up with the benchmark taxonomy, or it
sits in a Costing project that Benchmarking isn’t using. Once we align the mapping and source, it
will show in the benchmark views.

**Infrastructure metrics do not appear, but OpEx does**

Symptom  
Industry and IT OpEx views show data, but Infrastructure views are
empty.  
Likely causes

- Volume or capacity data missing for infra-related Resource Sub-Towers
- Resource Sub-Towers not mapped cleanly to benchmark definitions

What to check

1. Verify cost **and** volume data for infra Resource Sub-Towers (servers, storage, network,
   etc.).
2. Check units (for example TB vs GB, physical vs virtual servers).

Short answer you can send  
Infra benchmarks are not available yet because we haven’t
completed the cost and volume mapping for the infrastructure Resource Towers. Once that’s in place,
the infra unit cost metrics will populate.
