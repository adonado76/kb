---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Values look wrong or suspicious"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
source_path: "it-benchmarking/troubleshooting/values-wrong.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Values look wrong or suspicious

**Our value is orders of magnitude higher or lower than peers**

Symptom  
A metric shows you far above or below the peer band by a large factor, not
just 10–20 percent.  
Likely causes

- Unit mismatch (thousands vs whole currency units, GB vs TB, etc.)
- Volume error (wrong counts, wrong scope)
- Scope mismatch (you’re including costs others exclude, or vice versa)
- Wrong year or partial-year data

What to check

1. Look up the metric definition (**[Data
   & Methodology Reference](../home.html#benchmarking__data-methodology)**): numerator and denominator.
2. Confirm the cost total in Costing matches Finance for that year.
3. Confirm volume comes from the right system and matches reality.
4. Check for unit errors (for example TB entered as GB).
5. Verify the selected year is a full year, not a half-year.

Short answer you can send  
This value is out of range because the underlying cost or
volume data isn’t aligned with the benchmark definition. We’re validating the scope and units and
will update the mapping so the comparison is meaningful.

**Our IT spend ratio is very different from internal Finance numbers**

Symptom  
Benchmarking’s IT spend as percentage of revenue is different from Finance’s
view.  
Likely causes

- Different IT scope (for example IT + telecom vs IT only)
- Different revenue scope (group vs segment, gross vs net)
- Currency or period differences
- Benchmarking uses TBM-aligned IT definitions; Finance uses internal categories

What to check

1. Compare IT scope: what Cost Pools and functions are included on both sides.
2. Confirm revenue scope and period match the IT cost scope.
3. Check currency and any rate assumptions.

Short answer you can send  
The ratio differs because Benchmarking is using a standard
TBM-aligned definition of IT cost and revenue that doesn’t exactly match Finance’s internal view.
We’ll reconcile scope and definitions and then agree on a single view for external comparisons.

**Year over year benchmark trend jumps unexpectedly**

Symptom  
A metric is stable for years, then suddenly jumps up or down with no obvious
operational event.  
Likely causes

- TBM model changes (remapping, new towers, project scope changes)
- Benchmarking pointing to a different Costing project or scope for that year
- Change in organizational profile that alters the peer group
- Benchmark dataset refresh that changed peer composition

What to check

1. Review TBM / Costing change logs around the jump year.
2. Confirm Benchmarking is using the same Costing project and scope across years.
3. Check whether your profile changed industry, size band, or region in that year.
4. If necessary, compare to prior benchmark change logs to see if coverage changed.

Short answer you can send  
The jump is driven mostly by structural or configuration
changes, not a single operational event. We changed how costs are mapped or which peers we compare
against, so we’ll mark that year as a structural break rather than a smooth trend.
