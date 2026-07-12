---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Rollback and Recovery"
breadcrumb:
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
  - "Rollback and Recovery"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/rollback-recovery.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Rollback and Recovery

Sometimes changes need to be reversed—perhaps a configuration causes performance problems or content was deployed prematurely. TBM Studio provides rollback capabilities for these situations.

When to Use Rollback

Consider using the rollback feature when:

- A checked-in configuration is causing performance problems
- Content was deployed to Production prematurely
- You need to return to a known good state quickly

Rollback should not be used lightly. All check-ins after the rollback point will be discarded. If there are changes in those check-ins that you want to keep, you will need to re-implement them after the rollback.

How Rollback Works

When you execute a rollback:

1. Any running calculations for the project are stopped
1. A new calculation starts using the configuration from the selected check-in
1. All check-ins after the selected point are discarded (branch operations are exempt)
1. A full Stage calculation runs, which may take time depending on configuration complexity

Executing a Rollback

1. Select any document in Project Explorer.
1. On the Build tab, select Check In History.
1. Right-click the check-in you want to roll back to and select Rollback To.
1. Enter a descriptive reason for the rollback and click Rollback Check In.
1. After the build completes, refresh any workspaces with checked-out documents by selecting Home > Update Workspace.

If content was deployed to Production prematurely, consider using a hotfix branch instead of rollback. A hotfix may be faster and doesn't discard intermediate check-ins.
