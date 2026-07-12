---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Upgrade Costing Standard from template v104+ to the latest version"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgradect-v104.html"
images:
  - "resources/images/ct_images/prereqs-uprading-to-v104-1.png"
  - "resources/images/ct_images/prereqs-uprading-to-v104-2.png"
  - "resources/images/ct_images/step-1-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-1-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-4.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-5.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-6.png"
  - "resources/images/ct_images/step-10-upgrading-to-v104-7.png"
  - "resources/images/ct_images/step-11-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-12-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-12-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-12-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-13-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-13-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-2-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-2-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-3-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-4-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-4.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-5.png"
  - "resources/images/ct_images/step-5-upgrading-to-v104-6.png"
  - "resources/images/ct_images/step-7-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-8-upgrading-to-v104-1.png"
  - "resources/images/ct_images/step-8-upgrading-to-v104-2.png"
  - "resources/images/ct_images/step-8-upgrading-to-v104-3.png"
  - "resources/images/ct_images/step-9-upgrading-to-v104-1.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Upgrade Costing Standard from template v104+ to the latest version

Applies to: Costing Standard on TBM Studio 12 and later, with Template
v104 and later

## Upgrade application components to latest version

This article provides general instructions for upgrading Costing Standard to the latest template
version. Complete the steps in this article only after you have upgraded the application to the
latest TBM Studio release. The images in this article are for Release 12.5 with an upgrade from
Template v104 to v105, but the instructions work for any template upgrade. These instructions prompt
you at [Step 6: Component-specific upgrade steps](#UpgradeCostingStandardfromtemplatev104tothelatestversion__Step6Componentspecificupgradesteps) to jump to another article for component-specific instructions, then return to this article to
complete the upgrade.

For a list of the data sets that need to be upgraded, see:

- Master dataset changes for applications on TBM Studio 12.5
- Master dataset changes for applications on TBM Studio 12.6
- Master dataset changes for applications on TBM Studio 12.7

Note: The upgrade to template v104 introduced a new user experience with newly
organized report collections and new, simplified reports. If you need to upgrade from v103 to a
newer template version (v104 or later), use the instructions in [Upgrade Costing Standard from template v103 to the latest version](upgrade-guide-v103-to-latest/upgradect.html) instead of this article.

## Best practice for parallel development during upgrade process

If you plan to continue with development activities while you upgrade components, the following
best practices are recommended:

- Check in all changes prior to creating an upgrade branch. Ideally, it is best to complete the upgrade and merge the branch as soon as possible.
- If development work needs to continue, the following activities can also continue while an upgrade branch is open:
  - Load data and publish to the Development, Staging, and Production environments.
  - Create new custom reports.
  - Modify existing customized reports.
- Avoid the following activities until after the branch has been merged:
  - Install new components.
  - Append and map datasets to master data sets.
  - Change model configurations or allocations.
  - Modify out-of-the-box (OOTB) reports.

The estimated time to complete the upgrade process depends on the number of components being
installed, the amount of customization made to your OOTB reports, and the level of validation needed
before you can merge the branch. For example, a recent upgrade of 25 components for Costing Standard
(full stack) and Vendor Insights took approximately 1-1/2 weeks.

## Prerequisite configuration

If you need to upgrade the Cloud Service Provider component, the Cloud Invoice Weighting metric
must be configured before you begin the upgrade process.

To update the Cloud Invoice Weighting metric prior to beginning the upgrade process.

1. Navigate to TBM Studio, then in the Project Explorer, click Metrics

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/prereqs-uprading-to-v104-1.png)
2. Find the Cloud Invoice Weighting metric and update as follows:
   - Update the Metric Type field to Costing
   - Ensure the value in the Value Calculation field is =TimePeriod(Cloud Invoice,-1)

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/prereqs-uprading-to-v104-2.png)
3. Check in the updates

## Step 1: Create a branch

Before performing this step, upgrade to the latest TBM Studio release.

Perform the upgrade process in a separate branch, rather than in a personal Development
environment.

1. Before creating the branch, complete and check in any changes in your main project.
2. On the Project tab, click Create Branch.

   The Create Branch dialog box opens.
3. Enter a new branch name, for example, Version Upgrade Branch.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-1-upgrading-to-v104-1.png)
4. Click OK.

   The Calculation Queue dialog opens. Wait for the calculations to
   complete.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-1-upgrading-to-v104-2.png)

## Step 2: Open the new branch

Upgrade the project in a separate branch. For more information, see [Best practices: Branching projects](../../studio/admin/bp-branching-projects.html "Applies to: TBM Studio 12.1 and later").

1. On the Project tab, click Trunk.
2. Select the branch you want, for example, Version Upgrade Branch.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-2-upgrading-to-v104-1.png)

   After selecting a
   branch, you will see the active branch in the menu bar.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-2-upgrading-to-v104-2.png)
3. Each time you return to TBM Studio, verify that you are in the correct upgrade branch before
   proceeding. If not, and Trunk is displayed, you will need to re-select the Version Upgrade
   Branch.

CAUTION:

Do not make changes in the main project (for example, Trunk) during the course
of the upgrade activities in the separate upgrade branch. If you do, all changes made in the main
Trunk will be lost after merging the upgrade branch.

## Step 3: Change component version

1. On the Project tab, click Project Settings.

   The Edit Project Settings dialog opens.
2. For Component Version, select the latest version, for example, Version 105.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-3-upgrading-to-v104-1.png)
3. Click Save.
4. Check in the change and enter a description, such as Project Settings: change to [upgrade
   template version].

## Step 4: Review components to upgrade

Confirm that the new component versions are available, then upgrade them.

1. On the Project tab, click Components.

   The Component Configuration dialog opens.
2. View the list of installed components.

   An arrow in the bottom right corner of each installed
   component indicates that an upgraded version for that component is available.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-4-upgrading-to-v104-1.png)
3. Install and upgrade all components for the new template version. Perform the following step for
   each component that needs to be upgraded.

## Step 5: Upgrade individual components and check in the changes

1. In the Component Configuration dialog, double-click a specific component, for example, CTF -
   Cost Source.

   A component page opens.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-1.png)
2. Scroll down below the list of included reports to the Upgrade Available section.
   - A blue box indicates that no customizations have been made to any items in the component.
   - A yellow box indicates that customizations have been found with the data, calculated metrics, or
     reports.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-2.png)

   Note: Occasionally, the yellow box remains after you revert all the customizations. To
   proceed, click the Upgrade button in the yellow box.
3. If customizations exist, click View Conflicts, or scroll to the bottom of the page.
4. Revert any customized reports and calculated metrics.

   Note: Do not revert the datasets. If any of
   the standard master data set columns or formulas have been customize, you might need to review the
   configuration after the upgrade to make sure your datasets have the proper columns and
   configuration. See Step 6 for more information.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-3.png)
5. Click Upgrade, then confirm that the upgrade arrow is no longer displayed.

   The application
   takes a few minutes to process the upgrade. After the component page refreshes and returns to the
   Component Configuration page, you can continue.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-4.png)
6. After the upgrade is complete, you must manually change any other customized datasets that were
   not reverted. Refer to one of the following cumulative lists to identify what changes are required:
   - Master dataset changes for applications on TBM Studio 12.5
   - Master dataset changes for applications on TBM Studio 12.6
   - Master dataset changes for applications on TBM Studio 12.7

   Note: This activity could potentially require time to understand and correctly implement the
   changes to the master dataset.
7. Do the following procedures as needed to revert your customized datasets:
   - To add new columns to an existing master data set:
     1. Navigate to Tables and check out Cost Source Master Data.
     2. Add a Formula step before the Append step.
     3. In the new Formula step, add the new columns.

     ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-5.png)
   - To upgrade the following Cloud Cost Management (CCM) components, perform the steps outlined
     here, then return to this article:
     - CT Apps - AWS Recommendations
     - CTF - Amazon Web Services
     - CTF - Azure
     - CTF - Cloud Service Provider
     - CTF - Public Cloud MTD
     - CTF - CCM to CT Integration
   - To upgrade the following Vendor Insights components, click the corresponding link below for
     detailed instructions:
     - Vendor Insight Foundation
     - Vendor Insight PO
8. When you are finished updating your customized datasets, check in the changes related to a
   single component upgrade one at a time, as follows:

   CAUTION:

   Failure to check in
   components one at a time could result in an error that causes you to lose your work and restart the
   upgrade from the beginning.

   1. Select Projects, then click Check In.
   2. Select All items in the left pane (default).
   3. Enter a description of the items in the Message pane.

      The Check In dialog
      opens.

      Note: Enter a useful description, such as Cost Source: revert data set changes, upgraded
      component. This is critical for the branch merge activities later in this upgrade process. Review
      [Step 10: Merge changes into the main project (Trunk)](upgradect-v104.html) to understand why this is
      important.

      ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-5-upgrading-to-v104-6.png)
   4. Click Check In.

## Step 6: Component-specific upgrade steps

The following components require special instructions:

- v106 Components - Upgrade all Cloud components with instructions for Upgrade Cloud for Cost
  Transparency R12.6 (v106), then return to the next step in this guide.
- v107 Components - Upgrade the Apptio Value Explorer (AVE) with
  instructions for [Upgrade to Apptio Value Explorer 12.7
  (v107)](../configuration-additional/upgradetoave1.7v107.html).

## Step 7: Upgrade the remaining components in the upgrade branch

Repeat Steps 4 and 5 to upgrade as many components as needed.

While there is no prescriptive order to the component upgrade, it is recommended that you upgrade
components in the same order that the object related to the component is allocated in your models.
For example, for Costing Standard, upgrade Cost Source before IT Resource Towers, and IT Resource
Towers before Applications.

The recommendation is to upgrade all installed components to the latest release to ensure that
you have the latest features and highest quality content. You can also choose to upgrade only a
select set of components with the features you want. Contact Apptio if you have questions.

**CAUTION**

When you finish upgrading the components, perform the following steps to prevent potential data
loss.

1. Open the CT Apps-Application component.
2. In the Customized Elements section, look for the following metrics:
   - App Dev (deleted)
   - App Run (deleted)
   - App Run Budget (deleted)
   - App Dev Budget (deleted)
3. Click each missing metrics to revert to the original, or stock, version.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-7-upgrading-to-v104-1.png)
4. Check in the change.
5. Open the CT-Business Units component.
6. In the Customized Elements section, look for the following metrics:
   - CapEx Fixed (deleted)
   - CapEx Variable (deleted)
   - Project Investments (deleted)
7. Click each missing metric to revert it to the original, or stock, version.
8. Check in the change.

## Step 8: Review upgraded application in the upgrade branch

1. On the Project tab, click Calculation Queue.

   The Builds dialog box opens.
2. Verify that the builds have finished.

   You will see a list of the individual
   check-ins.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-8-upgrading-to-v104-1.png)
3. In the navigation bar, select Costing Standard from the Application menu.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-8-upgrading-to-v104-2.png)
4. Select the upgrade branch, for example Version Upgrade Branch.

   The home page
   opens.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-8-upgrading-to-v104-3.png)

## Step 9: Compare previous version to the newest version reports

1. Open the Costing Standard project in a browser.
2. Select Trunk to view the reports for the older template.
3. Open the Costing Standard project in another browser.
4. Select the Version Upgrade Branch to view the new reports for the upgraded template.
5. Review reports side-by-side.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-9-upgrading-to-v104-1.png)
6. If desired, re-apply customer-specific changes to the reports directly in the Version Upgrade
   Branch.

   Note:
   - Avoid making changes to out-of-the-box reports so you can minimize the effort involved with
     future upgrades.
   - If report customizations must be made, apply them to the out-of-the-box reports after you
     complete Step 7 to merge the upgrade changes. This minimizes the amount of time you have to work in
     the Version Upgrade Branch. **Remember** - do not make changes, other than data loads, into the
     main project (Trunk) after you create your upgrade branch.
7. After you verify the latest version of the reports, proceed to the next step to merge the
   changes into your main project.

## Step 10: Merge changes into the main project (Trunk)

Refer to [Best practices: Branching projects](../../studio/admin/bp-branching-projects.htm "(Opens in a new tab or window)") for more information.

Note: Do not merge all changes in one step. If you do, the merge process fails. The
recommendation is to merge small batches of check-in records - up to 5 records at one time. This
requires keeping notes to ensure that all check-in records are merged into the trunk in the proper
order.

1. Return to TBM Studio.
2. Select the upgrade branch, for example, Version Upgrade Branch.
3. On the Project tab, click Check In History.
4. Scroll down to the bottom of the list, then click and begin with the first item above the
   *bootstrap* entries. This should be the Project Settings: change to [new template version]
   check-in.

   NOTE: You can select additional items to check in as a single merge, but select no more
   than 5 items at one time.

   CAUTION Merging more than 5 items in a single check-in could cause
   the application to fail.
5. Right-click the line item and select Merge changes to branch.

   This example uses the CT-F Cost
   Source merge item.
6. Select Trunk as the recipient of the merge.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-1.png)

   The Merge Changesets
   dialog box opens.
7. Select all items for merge (default).

   NOTE: Do not de-select any individual items.
8. Click OK.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-2.png)

   RECOMMENDATION: Manually track your merged steps as you upgrade the components because the
   Check In History dialog does not indicate which items have been merged. If you attempt to check in
   an item twice and the following message appears, click Cancel, then proceed with a different
   component.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-3.png)
9. After complete, the window should switch to Trunk. If not, change to Trunk to check in the
   merged item in your project.
10. To verify that the change has propagated to the Development environment:
    1. In the navigation bar, select the In Development environment.
    2. Click the Project tab.
    3. Click Components.
    4. Verify that the component no longer displays the upgrade arrow, as in this example, for the CTF-
       Cost Source component.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-4.png)
11. From the Environment menu in the navigation bar, select Staging.
12. In the Project ribbon, ensure that the Locked icon is grayed out (not locked).

    You need to do
    this only once.
13. From the Environment menu in the navigation bar, select In Development, then click Check
    In.

    The Check In dialog opens.
14. Select all items in the left pane (default).

    This should be limited to the merged
    items.
15. Enter a description of the items in the Message pane.

    RECOMMENDATION: Use a useful description
    such as Merge – CTF-Cost Source: revert Service Costing report customizations, upgrade
    component.
16. Click Check In.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-5.png)

    Wait for the build to complete.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-6.png)
17. Verify that the expected change from the branch merge step is applied to the Staging
    environment.

    In this example, on the Project tab, click Components to verify that the new template
    version is now active.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-10-upgrading-to-v104-7.png)
18. Return to the upgrade branch, for example, Version Upgrade Branch, to proceed with the next item
    to merge.
19. Repeat the above steps to continue merging up to 5 individual upgrade branches (at one time) and
    subsequent Trunk check-ins (In Development) until all have been merged.

## Step 11: Validate latest version reports in the main project (Trunk)

1. Open the Costing Standard project in one browser.
2. Select Trunk to view the upgraded reports.
3. Open the Costing Standard project in a second browser.
4. Select Version Upgrade Branch to compare.
5. Compare and review reports side-by-side.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-11-upgrading-to-v104-1.png)
6. If desired, re-apply customer-specific changes to the reports directly in the main branch, for
   example, Trunk.

   RECOMMENDATION Avoid making changes to the out-of-the-box reports to minimize the
   effort involved with future upgrades.

## Step 12: Upgrade the Production environment

After you finish verifying the reports, push the upgraded application to Production.

1. Go toTBM Studio.
2. Select the Staging environment.
3. On the Project ribbon, click Lock.

   A brief pop-up message will indicate that the environment
   is locked. The environment is now ready to promote to Production.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-12-upgrading-to-v104-1.png)
4. On the Projects ribbon, click Promotion Options, then do one of the following:
   - Click Promote Now. The upgrade is pushed to Production immediately.
   - Click Promote Later to schedule when the upgrade will be published to Production.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-12-upgrading-to-v104-2.png)
5. On the Project ribbon, click Calculation Queue to verify the production build.
6. Compare the build numbers for the Development, Staging, and Production environments.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-12-upgrading-to-v104-3.png)

## Step 13: Close the upgrade branch

1. Select the Version Upgrade Branch.
2. On the Project ribbon, click Close Branch.

   The Confirm Close dialog opens.
3. Click OK to close the branch.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-13-upgrading-to-v104-1.png)
4. Confirm that Trunk is no longer displayed in the navigation bar.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/step-13-upgrading-to-v104-2.png)

   RECOMMENDATION:
   Close the upgrade branch as soon as possible. The branch consumes the same amount of resources as
   the main trunk project. Closing the upgrade branch frees up resources and improves the overall
   performance.

## Step 13: Make Infrastructure reports visible

Beginning with TBM Studio 12.6 (and Template v106), the Infra Server and
Storage reports moved to the Infrastructure Insights report collection. Because of this change, the
default in Enhanced Access Administration shows that the reports are
viewable by Nobody, which can create confusion when you try to access your old reports. To correct
the navigation, see [Update visibility of
Infrastructure reports after v106 upgrade](ct-upgrade-inf-visibility-after-v106.html "Beginning with TBM Studio 12.6 (with Template v106), the Infra Server and Storage reports moved to the Infrastructure Insights report collection from the Infrastructure & Cloud report collection in Costing Standard. Because of this change in navigation, the default in Enhanced Access Administration shows that the reports are viewable by Nobody, which can create confusion when you try to access your old reports.").

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
