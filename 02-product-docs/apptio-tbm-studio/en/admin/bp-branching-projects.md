---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "Best practices: Branching projects"
breadcrumb: []
source_path: "admin/bp-branching-projects.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Best practices: Branching projects

Applies to: TBM Studio 12.1 and later

Branching is an advanced feature added to the platform for Apptio TBM Studio v.12.1. Branching is
a core feature found in most modern version control systems. Branching allows users to create a copy
of a complete project, make changes on the project copy in parallel, and then promote to production
those changes with the original project. Branching is an extremely powerful addition to the TBM
Studio experience, and it is important to understand its intended uses.

![](../../resources/images/studio_images/studioimages/studio_diagram_branching.png)

## Branches and workspaces

A *workspace* is a user-specific environment where changes to checked-out documents live
until they are checked back in. When you check out a document in a workspace, you have an exclusive
lock on that document. No one can check out that document until it is checked in.

A *branch* is a complete copy of the current project at the time when the branch was
created. When you check out a document from a branch, that document goes into a workspace on that
branch. Changes made to documents in branch workspaces appear on the branch only after those
documents are checked in. To see the changes on the trunk, the branch must be merged back into the
mainline project.

## Why would you use branching?

Branches are intended to support one of two key use cases:

- Long-running configuration: There is a set of changes to be made that
  will take a long time before they are ready to be promoted to Production. Meanwhile, changes, such
  as monthly data loads, need to be made and pushed to Production. You can create a branch and make
  the changes to the branch while your operational data loads continue on the trunk.
- Hotfix prod: There is a problem with something in Production, but
  development has taken place that isn't ready to promote to Production. You can create a branch, fix
  the specific issue, and then merge the branch into Production.
- Audit prior state or archived state: There is a business need to look at
  a past state of a project. For example, a prior fiscal year might be closed and changes are made to
  the model, but you need to look at numbers from that past state. Using branches, you can look at the
  exact state of the system at a previous point in time.

Branch concepts:

- Each branch is a complete copy of the trunk project. This has performance implications as
  discussed in the following Best practices and performance considerations section.
- The number of branches for an environment is limited to five (5)
- To open and close branches, you must be assigned to a role that has the *Create and close
  branches* permission.
- Closing a branch removes the branch project along with any build projects, workspaces, and so
  on. A branch cannot be closed if it has a build used in Production. Once a Staging build from the
  trunk is promoted to Production, the branch may be closed. See also [Troubleshoot a
  branched project that cannot be closed](https://community.apptio.com/docs/DOC-8743 "(Opens in a new tab or window)").
- When you merge changes to a branch, you can:
  - Select the documents that you want to merge.
  - See a list of conflicts, if any exist (a conflict occurs when changes are made to the same
    document in two different branches).
- You cannot merge a document if it is *checked out* by another user working in trunk.
- All documents in a branch must be *checked in* before you can merge the branch.
- Tags exist for all builds, and custom tags can be created to identify specific builds.
- For hotfix branches, when the branch is promoted to production, it overrides the trunk
  branch.

## Best practices and performance considerations

Branches use the same amount of resources (for example, memory, CPU, and so on) as the project
from which they are branched. Therefore, when you create a branch, you are adding a load to your
Apptio environment equal to the load of any activity you might engage in with your main project.
Therefore, it is important to right-size time in your branch. To do this you would change the "Start
of Project" and "End of Project" in the "Time Settings" of the project to constrain time to an
appropriate number of periods. For example, if you are working on modeling, you probably only need
one time period. If you are working on reports with trends you could test those with 3 periods. If
you have a need to validate the changes with the full time frame you can change the time back to the
original or final range for a final test when you are done.

When creating a branch, consider the impact on both stage calculations and workspace load and be
sure to right-size time for your branch. For more information on branch impacts to workspace
performance, see [Managing performance in your development environment](https://community.apptio.com/docs/DOC-10828 "(Opens in a new tab or window)").

Additionally, except for hotfix branches, calculations for branches will be queued with
calculations for the project from which they are branched. If you create a branch from a version of
the project that took three hours to calculate, then the moment the branch is created, dev and stage
calculations will start. If someone checks in a change on the trunk after you have branched, then
the resulting dev and stage calculations for the trunk will be queued behind your branch
calculation.

The following image shows the AdminDB project view of the calculations for all the projects
branch calculations. Note the two sets of branch calculations in yellow and orange, and the trunk
calculation for the project on which those branches are based in green:

![](../../resources/images/studio_images/studio-calculation-queue_sui_1.jpg)

TBMAs wanting to navigate to this view should navigate to Enhanced Access Administration, select
the TBM Studio tile, and then open the Calculation
Queue.

## Create a branch based on the most recent completed build

When in the Stage environment, create a branch using the Create branch
command on the Project tab, Manage group.

When in the Development environment, you can use the Create branch command
only if you have nothing checked out. This restriction is by design. The implication is that you may
wish the changes in your workspace to be a part of the branch, but they will not be until all
materials are checked in and calculated.

## Apply a custom tag to a build

While all builds have default tags, as indicated in [Create a branch from a
past build that did not have a custom tag applied](#BestpracticesBranchingprojects__Createabranchbasedonthemostrecentcompletedbuild), after you have locked stage, the
Tag Project button becomes available. You can select Tag
Project to apply a custom tag to a build, which can help make finding a build much
easier.

![](../../resources/images/studio_images/studio_tag_project.png)

This tag will appear on the Builds page so that you can search for it easily and use it for branching.

Note:

At the time of this writing, the Tag Project button will *not* be available after you
promote a build.

## Create Branch with Auto-Checkout Option

When working with reports that contain editable tables, the auto-checkout feature automatically
checks out the underlying table when a report is modified, eliminating the need for manual checkout.
This feature is available only in the branch project and provides several benefits, including
improved user experience, increased productivity, and reduced errors. If an editable table is
checked out by someone else, an error message will be displayed to prevent conflicts and ensure
transparency.

1. Navigate to the branch.

   ![](../../resources/images/studio_images/ac-1.jpg)
2. Update the column value IT to IT Extension and **Save** the changes.

   ![](../../resources/images/studio_images/ac-2.jpg)
3. The **Check in** button is enabled and the underlying editable table is checked out.

   ![](../../resources/images/studio_images/ac-3.jpg)

## Create a branch from a tag

To branch from a tag:

1. Find the tag in the Check In History.
2. Right-click the tag, and then select Create branch from this
   point.

   ![](../../resources/images/studio_images/studio-create-branch-from-tag_sui.jpg)

## Create a branch from a default build that did not have a custom tag applied

Sometimes, you may want to create a branch from a prior build that was not tagged. For example,
if you discover that something has changed and you need to figure out when that change was
introduced. To create a branch from a default build

1. Select the Project tab, and then click Check In History.
2. Right-click the Check In History tab at the bottom and select Verbose View. When you are in
   Verbose View, you can see all the default builds without custom tags marked in green.

   ![](../../resources/images/studio_images/studio-verbose-view_sui.jpg)
3. Right-click a default build and select Create branch from this
   point.

## Navigate between branches and the trunk

When a branch for a project exists, you can navigate to the branch, or back to the trunk, using
the drop-down menu on the menu bar:

![](../../resources/images/studio_images/studio-navigate-branches_sui.jpg)

## Use a branch

- Limit branch check ins to ~30 documents - When working in a branch, the
  current recommended best practice is to limit check ins to approximately thirty (30)
  documents.Example: You have 100 documents checked out on the branch. Check in
  approximately thirty documents, then check in another thirty documents, and so forth. This action
  provides a limit to the individual check in sizes. This practice is recommended to address a
  limitation when merging the check ins to the trunk.
- Make changes - After a branch has been created, changes are made in the
  same way they are made to the trunk. Documents can be checked out, modified, and checked back in to
  the branch.
- Branches and workspaces - Your workspace on the trunk is separate from
  your workspace on branches. If you check out a document on a branch, and then navigate to the trunk,
  you will not see the document checked out there because it is a *separate workspace*.
- Check out considerations - It is possible to have the same document
  checked out on both the branch and the trunk at the same time. The implication is that one person
  could be working on the document and commit changes on the trunk that are not in the branch.

## Merge a branch back into the trunk

Before you merge, there are some prerequisites:

- None of the documents to be merged can be checked out in the trunk.
- The user executing the merge cannot have any document checked out in the trunk.
- Do not merge from the trunk to branches, or between branches.

While the UI supports merging between branches and from the trunk to branches, there are
limitations which make this action outside of best practices currently.

## Execute the merge

After changes have been checked in on a branch, the check ins as viewed in the Check In History
can be selected to merge into the trunk:

1. Select one or more check ins in the Check In History by using Ctrl+click
   or Shift+click.
2. Right-click on the selected records and select Merge changes to branch.
   At this time, it is recommended to merge branch changes to the trunk.

   ![](../../resources/images/studio_images/studio-merge-to-branch_sui.jpg)

## Resolve conflicts

When you execute a merge, a merge dialog window may display indicating there are conflicts.
Conflicts occur when the trunk has a document version that has been modified since the time the
branch was created. Therefore, if you were to merge the document *and* check it in, then the
branch document would overwrite the trunk document. To resolve these conflicts, you must either
manually integrate the changes present in the copy of the document in the *trunk* into the copy
of the document in the *branch*, or you must be willing to let the changes be overwritten.

## Check in after the merge

After you merge the changes, they will be checked out on the trunk. You must check them in on the
trunk before the merge operation is complete. Also, note that there is a document with the name of
the branch itself, which must also be checked in.

## Manage Branches

Admins can use this feature to avoid accidental deletion of a branch, thereby eliminating the
need for backup to recover a deleted branch.

In TBM Studio, navigate to **Project** tab, select **Manage Branches** option and then
select ‘X’ to close a branch.

![](../../resources/images/studio_images/mb-1.png)

A confirmation dialog popup appears. The Admin must type ‘delete’ and then select OK button.

![](../../resources/images/studio_images/mb-2.png)

## Close the branch

After you finish merging your changed documents to the trunk, close the branch. Closing the
branch conserves resources.

![](../../resources/images/studio_images/studio_close_branch_sui.jpg)

## Use a branch to hotfix prod

Occasionally, a change may be needed in prod quickly and changes in stage may not be ready for
deployment. In this scenario, a *hotfix* may be appropriate. To apply a hotfix to a document in
prod, follow these steps:

1. Navigate to the document in prod.
2. *Check out* the document. When the dialog appears, you can select either
   Development or Hotfix
3. Select Hotfix.

   ![](../../resources/images/studio_images/studio-create-hotfix_sui.jpg)
4. Wait until the hotfix branch calculates in stage. The system will calculate hotfix branches in
   parallel with other calculations, so normal build queuing does not apply.
5. Select Lock to lock the hotfix branch in stage.
6. Select Promote Now to promote the hotfix branch to production:

   ![](../../resources/images/studio_images/studio-promote-now_sui.jpg)

   The system will
   generate a branch called Hotfix, where you can make your change.

If you try to close the hotfix branch at this point, you will receive an error. This is because
the build in prod isn't based on the hotfix build and the system will not allow the hotfix branch to
be closed.

To close out the hotfix process:

1. Merge the changes into the trunk. See the [Merge a
   branch back into the trunk](bp-branching-projects.html#BestpracticesBranchingprojects__Mergeabranchbackintothetrunk) section above for details.
2. Promote the build with the hotfix changes to prod.
3. Close the hotfix branch.

See also [Troubleshoot a branched project that cannot be closed](https://community.apptio.com/docs/DOC-8743 "(Opens in a new tab or window)").

## Archive time periods and access archives

Periodically, it is useful to archive past time periods. For example, when you want to turn off
calculation for one or more past fiscal years to reduce calculation time.

To archive time periods:

1. Before changing the time settings, apply a custom tag. Use a naming convention for the tag, such
   as adding a prefix to the tag name with the word "Archive" so that it is easy to find all builds
   that correspond to archived events.
2. Adjust the time settings to make the project start date what you want it to be, and then check
   it in. This will close the old time periods.

If you want to access the archived time periods, search for the archive tags and generate a
branch from the archive tag.

## Branching FAQ

Why is Create Branch not available?

If the Create Branch button isn't available, or if it doesn't appear in
the context menu when you are right-clicking a build tag, you might have exceeded the number of
branches allowed for your environment. The branch limit is five branches for the environment
(inclusive of all projects).

Why can't I close a branched project?

If you click Close Branch on the Project tab and a
warning message appears stating that the branched project cannot be closed, see [Troubleshoot a
branched project that cannot be closed](https://community.apptio.com/docs/DOC-8743 "(Opens in a new tab or window)").
