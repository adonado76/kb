---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Normalization and mapping"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Data and Methodology Reference"
source_path: "it-benchmarking/data-and-methodology/normalization-mapping.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Normalization and mapping

This is where your model either earns trust or loses it.

**TBM taxonomy alignment**   
Benchmarks are aligned to standard TBM:

- Cost Pools
- Resource Towers and Resource Sub-Towers

Your Costing project’s model must:

- Map GL accounts, vendor data, and other sources into the same Cost Pools
- Map costs into Resource Towers and Resource Sub-Towers that correspond to benchmark
  definitions

If you have:

- Custom Resource Towers
- Custom Cost Pools
- Mixed categories that blend multiple standard pools

then you need explicit mapping rules. Misalignment here is the top cause of “these benchmarks
look wrong.”

**Scope and inclusions**  
You must decide and document what is in
scope.  
Typical inclusions for IT cost:

- Labor and contractors for IT functions
- Hardware, software, and cloud services
- Vendor services that support IT services
- Depreciation or amortization of technology assets

Typical exclusions:

- Business process outsourcing where IT is not the primary driver
- Non IT corporate overhead that is not allocated into IT
- Extraordinary one time charges, if the provider excludes them

Your scope choices should mirror how benchmark contributors are guided to report, as closely as
possible.

**Currency normalization**  
External benchmarks are reported in a reference
currency.  
Your environment:

- Should use a single working currency for the data you feed to Benchmarking
- Must ensure that both IT cost and revenue use that same currency for the period

If you operate in multiple currencies:

- Conversion should happen upstream in Costing or prior to manual entry
- Document which rates and timing you use for conversion

Mixing currencies silently is a reliable way to produce nonsense.

**Time alignment**  
Do not compare: Your current year forecast to A benchmark that
reflects last year’s actuals. Unless you are doing it deliberately and stating that clearly.

The clean pattern is, your fiscal year N actuals vs benchmark fiscal year N. Where fiscal years
differ across organizations, the benchmark provider applies their own alignment rules; you just need
to be consistent.

**Capital vs expense treatment**  
Benchmarks typically consider periodic IT cost,
which includes:

- Operating expenses
- Depreciation or amortization of capitalized technology investments
- Lease costs, depending on accounting approach

If your IT cost model excludes depreciation while benchmarks include it, your ratios will not
match.  
You should:

- Align treatment of CapEx and depreciation with benchmark guidelines
- Or at least understand the gap and avoid calling those metrics “actual IT spend” in an internal
  accounting sense
