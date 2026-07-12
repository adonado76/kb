---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Report Studio Issues"
breadcrumb:
  - "TBM Studio"
  - "Troubleshooting and Support"
  - "Common Issues and Solutions"
source_path: "studio/new-uc/ts-support/rs-issues.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Report Studio Issues

## Report Not Loading or Loading Slowly

**Symptoms:**

- Report displays blank or never finishes loading
- Browser times out when opening report
- Report loads but takes several minutes

**Solutions:**

1. **Check calculation status** - Go to Build > Calculation Queue. Verify the
   environment has finished calculating.
2. **Refresh browser and clear cache** - Refresh the browser page. If issue persists,
   try clearing browser cache.
3. **Verify underlying data** - Check that source tables and transforms have valid data
   for the selected time period.
4. **Test in Development environment** - Switch to Development workspace and check if
   the same report loads correctly there.
