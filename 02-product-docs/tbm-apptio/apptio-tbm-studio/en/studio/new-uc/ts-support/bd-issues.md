---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Build and Deployment Issues"
breadcrumb:
  - "TBM Studio"
  - "Troubleshooting and Support"
  - "Common Issues and Solutions"
source_path: "studio/new-uc/ts-support/bd-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Build and Deployment Issues

## Build Stuck in Pending or Calculating State

When builds appear stuck, first check the Calculation Queue to understand the current
state. Multiple check-ins can queue up builds, and large configuration changes may require
extensive calculation time.

**Solutions:**

- Check Calculation Queue (Build > Calculation Queue) to review status of all
  environments
- Wait for completion or coordinate check-ins with team members to batch changes
  together
- Cancel build if necessary (v12.3.1+) - pending changes will be included in the next
  build

## Cannot Promote to Production

**Solutions:**

- Verify Stage calculation is complete - promotion is only possible after all Stage
  calculations complete
- Check environment lock status - coordinate with other users if Stage is locked
- Review for blocking errors in the Errors panel
