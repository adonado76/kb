---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "apptio-benchmarking"
title: "Values look wrong or suspicious"
breadcrumb:
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
  - "Values look wrong or suspicious"
source_path: "SSIU957/it-benchmarking/troubleshooting/values-wrong.html"
images: []
capability_ids: []
last_updated: "2026-07-12"
summary: ""
---
# Values look wrong or suspicious

Our value is orders of magnitude higher or lower than peers

- Unit mismatch (thousands vs whole currency units, GB vs TB, etc.)
- Volume error (wrong counts, wrong scope)
- Scope mismatch (you’re including costs others exclude, or vice versa)
- Wrong year or partial-year data

1. Look up the metric definition ( Data & Methodology Reference ): numerator and denominator.
1. Confirm the cost total in Costing matches Finance for that year.
1. Confirm volume comes from the right system and matches reality.
1. Check for unit errors (for example TB entered as GB).
1. Verify the selected year is a full year, not a half-year.

Our IT spend ratio is very different from internal Finance numbers

- Different IT scope (for example IT + telecom vs IT only)
- Different revenue scope (group vs segment, gross vs net)
- Currency or period differences
- Benchmarking uses TBM-aligned IT definitions; Finance uses internal categories

1. Compare IT scope: what Cost Pools and functions are included on both sides.
1. Confirm revenue scope and period match the IT cost scope.
1. Check currency and any rate assumptions.

Short answer you can send The ratio differs because Benchmarking is using a standard TBM-aligned definition of IT cost and revenue that doesn’t exactly match Finance’s internal view. We’ll reconcile scope and definitions and then agree on a single view for external comparisons.

Year over year benchmark trend jumps unexpectedly

- TBM model changes (remapping, new towers, project scope changes)
- Benchmarking pointing to a different Costing project or scope for that year
- Change in organizational profile that alters the peer group
- Benchmark dataset refresh that changed peer composition

1. Review TBM / Costing change logs around the jump year.
1. Confirm Benchmarking is using the same Costing project and scope across years.
1. Check whether your profile changed industry, size band, or region in that year.
1. If necessary, compare to prior benchmark change logs to see if coverage changed.

Short answer you can send The jump is driven mostly by structural or configuration changes, not a single operational event. We changed how costs are mapped or which peers we compare against, so we’ll mark that year as a structural break rather than a smooth trend.
