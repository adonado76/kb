---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Unused Resource Recommendations"
breadcrumb:
  - "TBM Studio"
  - "Troubleshooting and Support"
  - "Error Messages Explained"
source_path: "studio/new-uc/ts-support/em-unused.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Unused Resource Recommendations

TBM Studio identifies unused resources that can be cleaned up to improve performance.
Access these via the Recommendations tab and use the guided troubleshooting
workflow.

## Unused Metrics

Calculated metrics that aren't used in other metrics or reports. Navigate to TBM Studio >
Recommendations > Unused Metrics. Select Troubleshoot All Identified Problems and follow the
guided workflow to delete unused metrics.

## Unused Allocations (Zero Unit Allocations)

Allocations that produce zero cost flow. These may indicate configuration errors or
obsolete allocation logic. Follow the Recommendations workflow to review and delete unused
allocations by model object.

## Unused Reports (BETA)

Reports that haven't been accessed recently. Turn off Auto Calculate before using this
workflow for bulk changes. Deactivating unused reports reduces calculation overhead.
