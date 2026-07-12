---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Branches and Hotfixes"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "Build and Deployment Lifecycle"
source_path: "studio/new-uc/concepts-architecture/branch-hotfix.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Branches and Hotfixes

Branching allows you to create a complete copy of a project, make changes in parallel, and then
merge those changes back. This advanced feature supports complex workflows where normal check-in
processes aren't sufficient.

**Branches vs. Workspaces**

**A workspace** is a user-specific environment where changes to checked-out documents live
until check-in. When you check out a document, you have an exclusive lock on it.

**A branch** is a complete copy of the project at the time of branch creation. Changes made on
a branch are independent of the main trunk until merged. Your workspace on a branch is separate from
your workspace on the trunk.

**When to Use Branching**

Branches support three primary use cases:

**1. Long-Running Configuration Changes**

When configuration changes will take weeks or months to complete, create a branch to work in
parallel while operational data loads continue on the trunk. Example: Major model restructuring that
requires extensive testing.

**2. Hotfix to Production**

When Production has a problem but Development contains changes not ready for deployment, create a
hotfix branch. Fix the specific issue on the branch, promote it to Production, then merge the fix
back to the trunk. Hotfix branches calculate in parallel with other builds, bypassing the normal
queue.

**3. Audit or Archive Past State**

When you need to view a past state of the project—such as a closed fiscal year—create a branch
from that point in time. This lets you see the exact numbers as they were, even if the current model
has changed.

**Branch Limits and Performance Considerations**

- **Branch limit:** Maximum of 5 branches per environment (across all projects)
- **Resource usage:** Each branch uses the same resources as the source project. Creating a
  branch effectively doubles your resource consumption.
- **Calculation queuing:** Branch calculations (except hotfix) queue with trunk calculations.
  If the trunk takes 3 hours to calculate, the branch will too.
- **Right-size time:** Limit the time range in your branch (Project Settings > Time Settings)
  to minimize calculation time. Use only the periods needed for testing.

Attention:

**Performance Impact:** Before creating a branch, consider the impact on calculation times. If
your trunk project takes 3 hours to calculate, creating a branch will immediately trigger a 3+ hour
calculation, potentially queuing behind or in front of trunk calculations.

**Creating a Hotfix Branch**

When Production needs an urgent fix but Stage isn't ready for promotion:

1. Navigate to the document in Production.
2. Check out the document. When prompted, select Hotfix (not Development).
3. Make your changes and check in. The hotfix branch calculates in parallel with other builds.
4. Lock the hotfix branch in Stage and select Promote Now.
5. Merge the changes back to the trunk so they aren't lost.
6. Promote the trunk build that includes the merged fix.
7. Close the hotfix branch to conserve resources.

**Merging Branches**

Before merging, ensure:

- No documents to be merged are checked out on the trunk
- You have no documents checked out on the trunk yourself
- All documents on the branch are checked in

To merge: In Check In History on the branch, select the check-ins to merge (Ctrl+click for
multiple), right-click, and select Merge changes to branch. Resolve any conflicts if the same
document was modified on both the branch and trunk. After merging, check in the merged documents on
the trunk.

Note:

**Best Practice:** Limit branch check-ins to approximately 30 documents at a time. If you have
100 documents checked out, check in batches of 30. This addresses a limitation when merging large
numbers of check-ins.
