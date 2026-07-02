---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Rollback and Recovery"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
source_path: "studio/new-uc/concepts-architecture/rollback-recovery.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Rollback and Recovery

Sometimes changes need to be reversed—perhaps a configuration causes performance problems or
content was deployed prematurely. TBM Studio provides rollback capabilities for these situations.

**When to Use Rollback**

Consider using the rollback feature when:

- A checked-in configuration is causing performance problems
- Content was deployed to Production prematurely
- You need to return to a known good state quickly

Warning:

Rollback should not be used lightly. All check-ins after the rollback point will be discarded. If
there are changes in those check-ins that you want to keep, you will need to re-implement them after
the rollback.

**How Rollback Works**

When you execute a rollback:

1. Any running calculations for the project are stopped
2. A new calculation starts using the configuration from the selected check-in
3. All check-ins after the selected point are discarded (branch operations are exempt)
4. A full Stage calculation runs, which may take time depending on configuration complexity

**Executing a Rollback**

1. Select any document in Project Explorer.
2. On the Build tab, select Check In History.
3. Right-click the check-in you want to roll back to and select Rollback To.
4. Enter a descriptive reason for the rollback and click Rollback Check In.
5. After the build completes, refresh any workspaces with checked-out documents by selecting Home >
   Update Workspace.

Tip:

If content was deployed to Production prematurely, consider using a hotfix branch instead of
rollback. A hotfix may be faster and doesn't discard intermediate check-ins.
