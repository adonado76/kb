---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Allocation Troubleshooting Reference"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Build Cost Models"
  - "Create Allocations"
  - "Allocation Troubleshooting Reference"
source_path: "SSWRJM/studio/new-uc/howtoguides/build-cost-model/troubleshoot-alloc.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Allocation Troubleshooting Reference

## Common Error Messages and Solutions

| Error Message | Cause | Solution |
| --- | --- | --- |
| Error Message | Cause | Solution |
| Unable to Find Linked Keys | Matching columns don't exist or contain no common values | Verify column names and check for data in both tables |
| Column Linkages not found | Legacy automatic allocation can't find matching columns | Switch to explicit key matching; turn off Automatic relationship |
| Assignment Ratio table is too large | Too many source-to-target combinations | Add data relationships to constrain scope; reduce identifier granularity |

## Allocation Not Working Checklist

When allocations produce unexpected results, verify:

- Both source and target tables are checked out
- Model step exists on both tables
- Allocation is saved (not just previewed)
- Matching columns exist in both tables with common values
- Weighting column is numeric with no nulls or negatives
- Filters don't exclude all source rows
- No conflicting allocations to the same target
- Model calculation has been run after changes

## Performance Optimization Tips

- Use data relationships: Constrains allocation scope and improves performance.
- Reduce identifier granularity: Fewer unique identifiers mean smaller allocation tables.
- Limit allocation paths: Each allocation adds calculation overhead.
- Review large tables: Model objects with >50,000 rows may need optimization.

## What's Next

After creating your allocations:

- Trace Cost Flows Through the Model : Learn to track individual costs through multiple tiers.
- Create Model Reports (Sankey Diagrams) : Build Sankey visualizations of your cost model.
- Understand Model Architecture : Deepen your knowledge of how allocations work.
