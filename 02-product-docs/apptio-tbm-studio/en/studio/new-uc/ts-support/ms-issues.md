---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Model Studio Issues"
breadcrumb:
  - "TBM Studio"
  - "Troubleshooting and Support"
  - "Common Issues and Solutions"
source_path: "studio/new-uc/ts-support/ms-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Model Studio Issues

## Allocation Not Working as Expected

**Symptoms:**

- Costs not flowing to expected targets
- Unallocated costs remaining after allocation
- Zero values in target objects

**Solutions:**

1. **Check driver data coverage** - Open the driver table and verify it contains values
   for all target entities. Consider adding a residual pool for handling gaps.
2. **Verify data relationships** - Open the allocation step and confirm Source Column
   and Destination Column are correctly mapped.
3. **Address legacy allocation issues** - If you see "Automatic relationship" checkbox
   enabled, clear it and manually set source/destination columns.

Warning: Once you check in changes to replace a legacy allocation, you cannot
re-enable the legacy configuration. Test thoroughly in Development before checking
in.

## Model Calculation Taking Too Long

**Symptoms:**

- Builds take hours to complete
- Staging environment frequently out of date
- Users experience slow report performance

**Solutions:**

1. **Analyze model complexity** - Use the Performance Review component to identify
   problematic areas. Focus on reducing allocations at lower levels of the model.
2. **Add identifiers to large objects** - Navigate to the flagged model object. In Rows
   dropdown, select Use object identifier.
3. **Reduce assignment ratio table size** - Add data relationships to constrain
   allocation scope. Add From or To filters.
4. **Clean up unused elements** - Delete unused metrics via the Recommendations panel.
   Remove unused allocations and deactivate unused reports.
