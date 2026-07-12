---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Model Studio Issues"
breadcrumb:
  - "Troubleshooting and Support"
  - "Common Issues and Solutions"
  - "Model Studio Issues"
source_path: "SSWRJM/studio/new-uc/ts-support/ms-issues.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Model Studio Issues

## Allocation Not Working as Expected

Symptoms:

- Costs not flowing to expected targets
- Unallocated costs remaining after allocation
- Zero values in target objects

Solutions:

1. Check driver data coverage - Open the driver table and verify it contains values for all target entities. Consider adding a residual pool for handling gaps.
1. Verify data relationships - Open the allocation step and confirm Source Column and Destination Column are correctly mapped.
1. Address legacy allocation issues - If you see "Automatic relationship" checkbox enabled, clear it and manually set source/destination columns.

## Model Calculation Taking Too Long

Symptoms:

- Builds take hours to complete
- Staging environment frequently out of date
- Users experience slow report performance

Solutions:

1. Analyze model complexity - Use the Performance Review component to identify problematic areas. Focus on reducing allocations at lower levels of the model.
1. Add identifiers to large objects - Navigate to the flagged model object. In Rows dropdown, select Use object identifier.
1. Reduce assignment ratio table size - Add data relationships to constrain allocation scope. Add From or To filters.
1. Clean up unused elements - Delete unused metrics via the Recommendations panel. Remove unused allocations and deactivate unused reports.
