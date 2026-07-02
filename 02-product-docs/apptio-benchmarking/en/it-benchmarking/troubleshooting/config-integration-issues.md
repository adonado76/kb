---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Configuration and integration issues"
breadcrumb:
  - "Benchmarking"
  - "Benchmarking Reports"
  - "Troubleshooting and FAQ"
source_path: "it-benchmarking/troubleshooting/config-integration-issues.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Configuration and integration issues

**Benchmarking does not reflect recent changes in Costing**

Symptom  
You updated mappings or allocations in Costing, but Benchmarking still shows
the old structure.  
Likely causes

- Benchmarking is pointed at a different Costing project than the one you updated
- Benchmark data hasn’t been refreshed since the change
- You changed a model or module that isn’t in the Benchmarking feed

What to check

1. Check Benchmarking configuration for which Costing project is in use.
2. Confirm when the last data refresh was run.
3. Verify that the Costing model you changed is actually feeding the Benchmarking data set.

Short answer you can send  
Benchmarking is still using the prior Costing view
because it hasn’t been refreshed from the updated project. Once we refresh from the correct project,
the benchmark views will reflect the new mappings.

**After changing TBM version, metrics look inconsistent**

Symptom  
You change the taxonomy version in Benchmarking and suddenly reports don’t
line up with previous years.  
Likely causes

- Resource Towers and Resource Sub-Towers differ between old and new versions
- Not all costs are mapped to new structures yet
- Some metrics use new groupings that don’t match historical grouping
- Benchmarking and Costing each are using different TBM versions.

What to check

1. Compare old vs new Resource Tower / Sub-Tower definitions.
2. Check for unmapped or partially mapped cost in the new version.
3. Treat the version-change year as a new baseline, not a continuation.
4. In Interactive Benchmarking, check that its Settings reflect the same TBM version as your
   Costing project.

Short answer you can send  
We moved to a newer taxonomy, which changes how towers and
sub-towers are grouped. That makes new results not directly comparable to prior years. We’ll treat
the change year as a baseline reset and, where needed, restate prior periods in the new
structure.
