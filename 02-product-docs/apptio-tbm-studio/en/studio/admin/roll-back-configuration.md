---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Roll back a configuration"
breadcrumb: []
source_path: "studio/admin/roll-back-configuration.html"
images:
  - "resources/images/studio_images/changehist-rollback.png"
  - "resources/images/studio_images/rollback-dialog.png"
  - "resources/images/studio_images/rollback-result.png"
  - "resources/images/studio_images/rollback.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Roll back a configuration

In Apptio TBM Studio version 12.2.2 and later, it is possible to use the **rollback**
feature in Check In History to roll back a configuration to an earlier point in time. This feature
is useful for reversing changes when something has gone wrong, and is similar to the Undo All After
feature in the v.11 audit log.

Note: There are important considerations prior to executing a rollback. We recommend you fully read
and understand this article prior to attempting a rollback. If you still have questions or concerns,
contact Apptio Support for assistance.

Here are some reasons you might consider using the rollback feature:

- Something has been checked in that is causing performance problems.
- Something was deployed to production prematurely. See [Check out and check in best practices](bp-check-out.html "◆ Applies to: Apptio TBM Studio 12.x and later. In Apptio TBM Studio R12, all elements are documents, including data tables, metrics, perspectives, and models. To edit a document, you must first check it out. When you check out a document, it is locked so that others cannot edit it. You can save your changes to the document without triggering a recalculation. When you finish editing a document, you can check it in. Checking in a document triggers a recalculation. Others will now see the changes you made to the document when the dev mode calculation is complete and their workspace is updated. Also, others will now be able to check out this document.") for information on how
  to hotfix a project if this is your reason for considering a rollback, as that may be faster.

## Important considerations

Rollback should not be used lightly. When a roll back is executed, any running calculations for
the project are stopped, and a new calculation is started, using the configuration associated with
the check in you are rolling back to. When rollback is executed, the following considerations apply:

- Any check ins that follow the check in you are rolling back to will be discarded. If there are
  changes in those check-ins that you want, you will need to re-implement those changes. See the last
  section of this document on how to make this easier.
- A full-stage calculation will need to run, and it may take a while depending on the project's
  configuration in the check in you are rolling back to.
- If existing calculations for other projects are taking place, then the calculation resulting
  from a rollback may be queued behind those.

## Roll back a configuration

[Check out and check in best
practices](bp-check-out.html "◆ Applies to: Apptio TBM Studio 12.x and later. In Apptio TBM Studio R12, all elements are documents, including data tables, metrics, perspectives, and models. To edit a document, you must first check it out. When you check out a document, it is locked so that others cannot edit it. You can save your changes to the document without triggering a recalculation. When you finish editing a document, you can check it in. Checking in a document triggers a recalculation. Others will now see the changes you made to the document when the dev mode calculation is complete and their workspace is updated. Also, others will now be able to check out this document.").

1. Select the document in **Project Explorer**.
2. On the **Build** tab select **Check In History**.
3. Right-click on the check in you want to roll back to and select **Rollback To**.

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rollback.png)
4. Enter your reason for rolling back (it is recommended to be as descriptive as possible), and
   then click **Rollback Check In**.

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rollback-dialog.png)

   After the rollback, the result is displayed similar to
   the example below:

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rollback-result.png)

   You can see the calculation status in the Builds
   tab:

   ![image](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/changehist-rollback.png)

   Note: All check ins after the check in selected for
   rollback are undone with the exception of the branch closure (branch operations are
   exempt from a rollback).
5. When the build is complete, refresh any workspaces with checked-out documents. In the Home tab,
   select **Update Workspace**.
6. To forcibly update the workspace, you might need to temporarily disable Auto Calculate. In the
   Home tab, select Auto Calculate, then select Update Workspace, then select Auto Calculate
   again.

   Note: Refreshing workspaces is especially important if the rollback is due to performance
   issues. If the documents were checked out while the suspect configuration was in play, then the
   user's workspace may suffer the same ill effects that first led to the rollback.

## Examine something that was rolled back

After a rollback, you may want to examine what was in check ins that became undone either to
debug what was causing performance issues, or to see a configuration that you want to re-implement.
To do this, you would use a branch. See [Check out and check in best practices](bp-check-out.html "◆ Applies to: Apptio TBM Studio 12.x and later. In Apptio TBM Studio R12, all elements are documents, including data tables, metrics, perspectives, and models. To edit a document, you must first check it out. When you check out a document, it is locked so that others cannot edit it. You can save your changes to the document without triggering a recalculation. When you finish editing a document, you can check it in. Checking in a document triggers a recalculation. Others will now see the changes you made to the document when the dev mode calculation is complete and their workspace is updated. Also, others will now be able to check out this document.") to understand how to create a branch.
You can branch from undone check ins. It is also possible to copy report content from a branch and
paste it into checked-out documents in your workspace. In some cases, this may be desirable to
minimize rework.
