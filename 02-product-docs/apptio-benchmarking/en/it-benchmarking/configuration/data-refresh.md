---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Data refresh and maintenance"
breadcrumb:
  - "Benchmarking"
  - "Configuration Guide"
source_path: "it-benchmarking/configuration/data-refresh.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Data refresh and maintenance

Configuration is not one and done. You need a refresh pattern.

**Refresh cadence for your data**  
Common pattern:

- **Annually (after benchmark data is refreshed – end of second calendar quarter)**
  - Validate core Benchmarking configuration for the latest full fiscal year.
  - Validate full set of Industry, IT OpEx, and Infra comparisons.
  - Align with planning or financial close.
- **Quarterly**
  - Spot-check key metrics for odd jumps.
  - If integrated, validate your Costing project’s model has no broken mappings and matches TBM
    version in Interactive Benchmarking.

**Handling TBM model changes**  
When you

- Add or rename Resource Towers.
- Introduce new Cost Pools.
- Change allocation logic significantly.

  
then

- Review Benchmarking mappings and update where needed.
- Re-run a small set of standard benchmark views to confirm results are still plausible.
- Document that a structural change occurred so anyone looking at trends knows where the break
  is.

If you skip this, you will see unexplained jumps and spend weeks trying to remember what
changed.
