---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Upgrade Costing Standard to Template v104"
breadcrumb: []
source_path: "cost-transparency/user-guide/upgradectto104-8841.html"
images:
  - "resources/images/ct_images/8841_1.png"
  - "resources/images/ct_images/8841_10.png"
  - "resources/images/ct_images/8841_11.png"
  - "resources/images/ct_images/8841_12.png"
  - "resources/images/ct_images/8841_13.png"
  - "resources/images/ct_images/8841_14.png"
  - "resources/images/ct_images/8841_15.png"
  - "resources/images/ct_images/8841_16.png"
  - "resources/images/ct_images/8841_17.png"
  - "resources/images/ct_images/8841_18.png"
  - "resources/images/ct_images/8841_19.png"
  - "resources/images/ct_images/8841_2.png"
  - "resources/images/ct_images/8841_20.png"
  - "resources/images/ct_images/8841_21.png"
  - "resources/images/ct_images/8841_22.png"
  - "resources/images/ct_images/8841_23.png"
  - "resources/images/ct_images/8841_24.png"
  - "resources/images/ct_images/8841_25.png"
  - "resources/images/ct_images/8841_26.png"
  - "resources/images/ct_images/8841_27.png"
  - "resources/images/ct_images/8841_28.png"
  - "resources/images/ct_images/8841_29.png"
  - "resources/images/ct_images/8841_3.png"
  - "resources/images/ct_images/8841_30.png"
  - "resources/images/ct_images/8841_31.png"
  - "resources/images/ct_images/8841_32.png"
  - "resources/images/ct_images/8841_4.png"
  - "resources/images/ct_images/8841_5.png"
  - "resources/images/ct_images/8841_6.png"
  - "resources/images/ct_images/8841_7.png"
  - "resources/images/ct_images/8841_8.png"
  - "resources/images/ct_images/8841_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Upgrade Costing Standard to Template v104

This document describes the reasons behind the Costing Standard user interface (UI)
upgrade and the recommended steps for upgrading Apptio application content from Template v103 to the
latest version of the application template.

Note: Applies to: Costing Standard on TBM Studio 12.3 and later, with Template v104 and later ([Learn
more](../reports-v104/ctreportcollections104-plus.html))

**SEE ALSO**:

- To understand the difference between templates v103 and v104, go to [Compare v104 and v103 Cost
  Transparency reports](../reports-v104/comparev103v104reports.html).
- To understand how the reports map to template v104, go to [Mapping Cost Transparency reports
  from Template v103 to v104](../reports-v104/mappingctreports103to104.html).
- For a spreadsheet that lists all the data sets that need to be upgraded for v104, go to [Template v103 to v104 Data
  Updates](template103to104dataupdates-9027.html).

## Goals

The user interface for Costing Standard was redesigned to do the following:

- Simplify the report navigation in Costing Standard
- Simplify and break apart complex reports
- Better support incremental configuration
- Segment products into top-level selection (e.g. separate Vendor Insights reports from Costing Standard)
- Support TBM Taxonomy v2 as the default (TBM Taxonomy v1 is still supported)
- Support Section 508 compliance
- Improve performance of known “expensive” reports

## Report collections in Template v104

The Costing Standard reports have been organized under the following report collections in
Template v104:

- Applications
- Benchmarking
- Business Units
- Data Dimensions
- Data Quality
- Infrastructure and Cloud
- IT Financials
- Projects
- Resources
- Services
- TBM Overview
- Vendors

## Reports types

The v104 report collections are organized around the following types of reports:

- Review reports provide a graphical overview of the top items in an area, such as the 10
  applications or categories with the largest spend.
  - Example: Financial Review
  - Example: Project Review
- Portfolio reports provide metrics across all the items in an area.
  - Example: Project Portfolio
- Analysis or List reports provide a tabular view for each area to quickly find a specific value.
  - Example: Financial Analysis
  - Example: Project List
- Other reports are added to a collection to handle insight use cases unique to an area.
  - Example: Projects at Risk
  - Example: Impact of Retiring Applications

## Expectations for upgrading to Template v104

Because of the breadth of changes to the UI and underlying navigation, it's important that **all
existing components MUST be upgraded**. Ptherwise, navigation from the landing page to the
top-level reports can potentially break. Further, links from one report to a report in another area
can potentially break (for example, a link from the Service Portfolio report to a related project
report for a specific service.)

## Identifying Template v103

You can determine whether your application is using Template v103 by looking at the Costing Standard homepage or the list of Costing Standard report collections.

If the **Home** page looks similar to the page below, you have Template v103.
Look for sections like IT Finance and IT Management, each with three links below them.

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_1.png)

Alternatively, look at your Reports menu. In the navigation bar, click the **Reports** menu
and look at the list of report collections. If you see IT Management, you have Template v103.

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_2.png)

Tip: To understand the difference between the templates, go to [Compare v104 and v103 Cost
Transparency reports](../reports-v104/comparev103v104reports.html).

## Upgrade to the latest components

The following steps are required to upgrade the application from Template v103 to v104 and later.
Complete these steps *after* you've upgraded your platform from TBM Studio 12.3 or 12.4 or
later.

## Step 1: Create a branch

Perform the upgrade process in a separate branch, rather than in a personal **Development**
environment.

1. Before creating the branch, complete and check in any changes in your main project.
2. On the **Project** tab, click **Create Branch**.

   The **Create Branch** dialog opens.
3. Enter a new branch name, for example, “Version 104 Upgrade.”

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_3.png)
4. Click **OK**.

   The **Calculation Queue** dialog opens. Wait for the calculations to complete.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_4.png)

## Step 2: Open the new branch

Upgrade the project in a separate branch ([Learn more](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=step-2-open-new-branch "(Opens in a new tab or window)")).

1. On the **Project** tab, click the **Trunk** drop-down menu.
2. Select the branch you want, for example, Version 104 Upgrade.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_5.png)

   After selecting a branch, you'll see the active branch in the menu bar.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_6.png)
3. Each time you return to TBM Studio, verify that you are in the correct upgrade branch before
   proceeding. If not, and **Trunk** is displayed, you'll need to re-select the Version 104 Upgrade
   branch.

   **CAUTION**: Don't make changes in the main project (for example, Trunk) during the course of
   the upgrade activities in the separate upgrade branch. If you do, all changes made in the main Trunk
   will be lost after merging the upgrade branch.

## Step 3: Change component version

1. On the **Project** tab, click **Project Settings**.

   The **Edit Project Settings** dialog opens.
2. For **Component Version**, select the version you want, for example, **Version 104**.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_7.png)
3. Click **Save**.
4. Check in the change and enter a description, such as “Project Settings: change to v104.”

## Step 4: Review components to upgrade

Confirm that the new component versions are available, then upgrade them:

1. On the **Project** tab, click **Components**.

   The **Component Configuration** dialog opens.
2. View the list of components that are installed.

   An arrow in the bottom right corner of each installed component indicates that an upgraded
   version of the content for that component is available.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_8.png)
3. Install and upgrade all components for the new template version, v104 and later. Perform Step 5
   for each component to be upgraded.

## Step 5: Upgrade individual components and check in the changes

1. In the **Component Configuration** dialog, double-click a specific component (for example, CTF
   - Cost Source).

   A component dialog opens.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_9.png)
2. Scroll down below the list of included reports to the **Upgrade Available** section.
   1. A blue box indicates that no customizations have been made to any items in the component.
   2. A yellow box indicates that customizations have been found with the data, calculated metrics, or
      reports.

      ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_10.png)

      **NOTE**: Occasionally, the yellow box remains after you revert all the customizations. To
      proceed, click the Upgrade button in the yellow box.
3. If customizations exist, click **View Conflicts**, or scroll to the bottom of the page.
4. Revert any customized reports and calculated metrics.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_11.png)
5. For customized data sets, revert the customized data sets for the following Cloud-related components:
   1. CTF- Cloud Service Provider
   2. CTF- Amazon Web Services
   3. CTF- Azure

      **RECOMMENDATION**: Take a screenshot of your current mappings to assist with the re-mapping
      of the tagging fields.

   **CAUTION**: Don't revert the data sets for any other components. If you revert data set
   changes, you'll be required to re-append and re-map your source files to the master data sets.
6. Click **Upgrade**.

   The application will take a few minutes to process the upgrade. After the component screen
   refreshes and returns to the **Component Configuration** page, you can continue. Confirm that the
   upgrade arrow is no longer displayed.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_12.png)
7. If you reverted data set changes for the Cloud reports, remap the source files to the Master
   Data, as follows:
   1. In Project Explorer, click **Tables**.
   2. Click **Master Data**.
   3. Append.
   4. Map the source columns to the appropriate Master Data columns.

      **NOTE**: Use the screenshot you captured in the previous step to verify the mappings.
8. After the upgrade is complete, you must manually change the data sets that were not reverted.
   For v104, refer to the cumulative list of [Template v103 to v104 Data Updates](template103to104dataupdates-9027.html) to identify what changes
   are required.
9. Check in all changes related to the single component upgrade one at a time, as follows:

   **CAUTION**: Failure to follow these steps to check in components one at a time could result
   in an error that causes you to loose your work and restart the upgrade from the beginning.
   1. Select **Projects**, then click **Check In**.

      The **Check In** dialog opens.
   2. Select **All items** in the left pane (default).
   3. Enter a description of the items in the **Message** panel.

      **NOTE**: Enter a useful description, such as “Cost Source: revert data set changes, upgraded
      component.” This is critical for the branch merge activities later in this upgrade process. Review
      [Step 9: Merge changes into the main project (Trunk)](#upgradectto104-8841__Step9MergechangesintothemainprojectTrunk) to understand why this
      is important.

      ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_13.png)
   4. Click **Check In**.
   5. Continue with Step 6.

## Step 6: Upgrade all other components in the Upgrade branch

All installed components need to be upgraded to the new template version. It's recommended that
you start with the lower level components (for example, CTF- components, then CT Apps, etc.).
However, you don't need to follow an exact order. For this example, the installed components are for
a CT Base configuration on Template v103.

Note: If you open the Costing Standard project during the upgrade process, you'll notice that some
of the navigation links are broken in the upgrade branch. These will be resolved when all components
have been upgraded.

Repeat Steps 4 and 5, to continue upgrading all the other components. The following order is
recommended; however, you might not have all these components installed in your environment:

- **TBM Review** component:
  1. Disable the component.
  2. Check in the change, “TBM Review: disable component.”
- **ATUM v2.0** component:
  1. Disable the component.
  2. Check in the change, “ATUM v2.0: disable component.”
- **CTF- Cost Source** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Remap the source files to the Cost Source Master Data set, if you reverted data set
     changes.
  4. Check in the change, “CTF- Cost Source: revert calculated metrics, upgrade component.”
- **CT- Quality** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Check in the change, “CT- Quality: upgrade component.”
- **CTF-Labor** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Remap the source files to the Labor Master Data set, if you reverted data set changes.
  4. Check in the change, “CT- Labor: upgrade component.”
- **CTF-IT Towers** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Remap the source files to the IT Resource Tower Master Data set.
  4. Check in the change, “CTF- IT Towers: revert calculated metrics, upgrade component.”
- **CTF-Time Tracking** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Remap the source files to the Time Tracking Master Data set, if you reverted data set
     changes.
  4. Check in the change, “CTF- Time Tracking: upgrade component.”
- **CTF-Projects** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Remap the source files to the Projects Master Data set, if you reverted data set changes.
  4. Check in the change, “CTF- Projects: upgrade component.”
- **CTF-Cloud Service** component:
  1. Revert any data set, calculated metric, or report customizations.
  2. Upgrade the component.
  3. Check in the change, “CTF- Cloud Service: revert calculated metrics, upgrade component.”
- **CTF-Amazon Web Services** component:
  1. Revert any data set, calculated metric, or report customizations.
  2. Upgrade the component.
  3. Check in the change, “CTF- Amazon Web Services: upgrade component.”
- **CTF-Azure** component:
  1. Revert any data set, calculated metric, or report customizations.
  2. Upgrade the component.
  3. Check in the change, “CTF- Azure: upgrade component.”
- **CT Apps-Applications** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Remap source files to the Applications Master Data set, if you reverted data set changes.
  4. Check in the change, “CT Apps- Applications: revert calculated metrics, upgrade component.”
- **CT- Business Units** component:
  1. Revert any calculated metric, or report customizations.
  2. Upgrade the component.
  3. Remap source files to the Business Unit Master Data set, if you reverted data set changes.
  4. Check in the change, “CT- Business Units: revert calculated metrics, upgrade component.”

## Step 7: Review upgraded application in the upgrade branch

1. On the **Project** tab, click **Components**.

   The **Component Configuration** dialog opens.
2. Verify that the builds have finished.

   You'll see a list of the individual check-ins.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_14.png)
3. In the navigation bar, select **Cost Transparency** from the Application menu.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_15.png)
4. Select the upgrade branch (for example, **Version 104 Upgrade**).

   The new home page opens.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_16.png)

   **NOTE**: If **TBM Review** appears in the menu bar and the new landing page is not
   displayed, you'll need to change the landing page from **TBM Review** to **Service Costing**
   using the params data set, as follows:
   1. Return to **TBM Studio**.
   2. On the **Project** tab, open the **Tables** section in the left pane.
   3. Search for “params.”
   4. Click **Params**.
   5. Check out the document.
   6. Click the **Upload** transform step.
   7. Click **Params.csv**, then select **Download**.
   8. Open Excel.
   9. Change the value for the column “InitialReport” to “.View:tab:Service Costing.”
   10. Click **Save**.
   11. Click **Params.csv**, then select **Overwrite**.
   12. Select the saved file and upload it into Apptio.
   13. Click the **Table** transform step.
   14. Verify that the **InitialReport** value has changed to “.View:tab:Service Costing.”
   15. Click **Save**.
   16. Check in the change.

## Step 8: Compare v103 reports to reports on the new template version

1. Open the Costing Standard project in one browser.
2. Select **Trunk** to view the Template v103 reports.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_17.png)
3. Open the Costing Standard project in another browser.
4. Select the branch for the new template (such as **Version 104 Upgrade**) to view the updated
   reports.
5. Review reports side-by-side.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_18.png)
6. If desired, re-apply customer-specific changes to the reports directly in the branch for the new
   template version (for example, Version 104 Upgrade).

   **RECOMMENDATION**: Avoid making changes to out-of-the-box reports so you can minimize the
   effort involved with future upgrades.

   **RECOMMENDATION**: If report customizations must be made, apply them to the out-of-the-box
   reports after you complete Step 7, merge the upgrade changes. This will minimize the amount of time
   you have to work in the Version 104 Upgrade branch. Remember, DO NOT make changes (other than data
   loads) into the main project (Trunk) after you create your Upgrade branch.
7. After you verify that the reports use the template version yoiu want, proceed to Step 9 to merge
   the changes into your main project.

**TIP**: See [Cost
Transparency reports from Template v103 to v104](../reports-v104/mappingctreports103to104.html) to understand where the v103 reports and
related information appear in v104.

## Step 9: Merge changes into the main project (Trunk)

Tip: Refer to [Branching, Hotfix, and Branch best practices](https://community.apptio.com/docs/DOC-5472 "(Opens in a new tab or window)") in Product Central.

1. Return to **TBM Studio**.
2. Select the upgrade branch (for example, Version 104 Upgrade).
3. On the **Project** tab, click **Check In History**.
4. Scroll down to the bottom of the list, then click the first item above the bootstrap entries, for
   example, Project Settings: change to v104 check in.

   **NOTE**: You can select additional items to check in as a single merge, but select no more
   than 5 items at one time.

   **CAUTION**: Merging more than 5 items in a single check-in could cause the application to
   fail.
5. Right-click the line item and select **Merge changes to branch**.

   For the screenshots in this example, we will use the CT-Apps Application merge item.
6. Select **Trunk** as the recipient of the merge.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_19.png)

   The **Merge Change sets** dialog opens.
7. Select all items for merge (default).

   **NOTE**: Don't de-select any individual items. All items are merged whether selected or
   not.
8. Click **OK**.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_20.png)

   **RECOMMENDATION**: Manually track your merged steps as you upgrade the components because the
   Check In History dialog won't indicate which items have been merged. If you attempt to check in an
   item twice and the following message appears, click **Cancel**, then proceed with a different
   component.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_21.png)
9. After complete, the window might switch to **Trunk**.
10. Change to **Trunk** to check in the merged item in your project.
11. To verify that the change has propagated to the Development environment:
    1. In the navigation bar, select the **In Development** environment.
    2. Click the **Project** tab.
    3. Click **Components**.
    4. Verify that the component no longer displays the upgrade arrow, as in this example, for the
       CT-Apps Application component.

       ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_22.png)
12. From the Environment menu in the navigation bar, select **Staging**.
13. In the **Project** tab, ensure that the Locked icon is grayed out (not locked).

    You need to do this only once.
14. Click **Components**, and notice that the CT Apps Applications component displays the upgrade
    arrow for v103.
15. From the Environment menu in the navigation bar, select **In Development**, then click
    **Check In**.

    The **Check In** dialog opens.

    **NOTE**: If the **Check In** icon is grayed out, you might need to wait a few minutes for
    the documents to be processed, then go to the **Staging** environment, then back to the
    **Development** environment, and try again.
16. Select all items in the left pane (default).

    This should be limited to the merged items.
17. Enter a description of the items in the **Message** panel.

    **RECOMMENDATION**: Use a useful description such as “Merge – CTF- Cost Source: revert data
    set changes, upgraded component.”
18. Click **Check In**.

    ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_23.png)

    Wait for the build to complete.

    ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_24.png)
19. Verify that the expected change from the branch merge step is applied to the Staging
    environment.

    In this example, on the **Project** tab, click **Components** to verify that v104 is now
    active.

    ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_25.png)
20. Return to the upgrade branch (for example, Version 104 Upgrade) to proceed with the next item to
    merge.

    **Known issues:**

- **Error message** - The first item merged should be the **Project Settings change to v104**
  (or whatever version you're upgrading to). After you merge the item, you might see an error message,
  “Server Error: Contact your administrator.”

  **Solution** - Exit the browser, re-open the browser, then proceed with the check-in step in
  Trunk. After the upgrade branch change is made and propagated to Staging, you should no longer see
  the error message.
- **Conflicting information in the navigation bar** - When switching between Trunk and the
  branch for the new template (such as Version 104 Upgrade), the new upgrade branch might appear in
  the navigation bar while the Check In History is from Trunk. If this occurs, follow these steps:
  1. Close the **Check In History** dialog, and perhaps all other dialogs.
  2. Change to **Trunk**.
  3. Change back to the **Version 104 Upgrade** branch.
  4. Re-open the **Check In History**.
  5. Proceed with merging the next step.
- **Merging disable components**. After a merged step for a disabled component, the items from
  the previous merge might still be listed in the left panel.

  **Solution**. Enter the appropriate description for what was just merged (for example, Merge –
  ATUM 2.0 component disabled). When the calculation is finished, you can verify the expected changes
  in Staging.

## Step 10: Merge all other components

Repeat Step 9 to continue merging up to 5 individual upgrade branches (at one time) and
subsequent Trunk (in Development) check-ins in the same order recommended in [Step 6: Upgrade all other components in the Upgrade branch](#upgradectto104-8841__Step6UpgradeallothercomponentsintheUpgradebranch):

- Merge 1 (up to 5 merge items)
  1. **Project Settings**: Change to the new template version, such as v104.

     **NOTE** This must be the first item in the first merge.

     Verify in Trunk that Project Settings changed in Development and Staging.
  2. **TBM Review**: Disable the component.

     Verify in Trunk that the TBM Review component is no longer installed for Development and
     Staging.
  3. **ATUM v2.0**: Disable the component.

     Verify in Trunk that ATUM v.2.0 component no longer installed for Development and Staging.
  4. **CTF- Cost Source**: Revert the calculated metrics and upgrade the component.

     Verify in Trunk that no upgrade arrow is displayed on the CTF- Cost Source component in
     Development and Staging.
  5. **Params**: Change to the Service Costing home page.

     Go to the Costing Standard application. You should see the new landing page for the version you
     selected. ([Learn
     more](../reports-v104/comparev103v104reports.html))

     **NOTE**: This step is only necessary if you installed the TBM Review component available in
     v103.
- Merge 2 (up to 5 merge items)
  1. **CT- Quality**: Upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the CT- Quality component in Development and
     Staging.
  2. **CT- Labor**: Upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the CTF- Labor component in Development and
     Staging.
  3. **CTF- IT Towers**: Revert the calculated metrics and upgrade the component.

     Verify in Trunk that there's no up arrow on the CTF- IT Towers component in Development and
     Staging.
  4. **CTF- Time Tracking**: Upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the CTF- Time Tracking component in Development
     and Staging.
  5. **CTF- Projects**: Upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the CTF- Projects component in Development and
     Staging.
- Merge 3 (up to 5 merge items)
  1. **CTF- Cloud Service**: Revert the calculated metrics and upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the CTF- Cloud Services component in Development
     and Staging.
  2. **CTF- Amazon Web Services**: Upgrade the component.

     Verify in Trunk that there's noupgrade arrow on CTF- AWS component in Development and
     Staging.
  3. **CTF- Azure**: Upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the CTF- Azure component in Development and
     Staging.
  4. **CT Apps- Applications**: Revert the calculated metrics and upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the Applications component in Development and
     Staging.
  5. **CT- Business Units**: Revert the calculated metrics and upgrade the component.

     Verify in Trunk that there's no upgrade arrow on the CT- Business Units component in Development
     and Staging.

## Step 11: Validate v104 reports in the main project (Trunk)

1. Open the Costing Standard project in one browser.
2. Select **Trunk** to view the upgraded reports.
3. Open the Costing Standard project in a second browser.
4. Select **Version 104 Upgrade** branch to compare.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_26.png)
5. Compare and review reports side-by-side.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_27.png)
6. If desired, re-apply customer-specific changes to the reports directly in the main (for example,
   Trunk) branch.

   **RECOMMENDATION**: Avoid making changes to the out-of-the-box reports to minimize the effort
   involved with future upgrades.

## Step 12: Upgrade the Production environment

After you finish verifying the reports, push the upgraded application to Production.

1. Go to **TBM Studio**.
2. Select the **Staging** environment.
3. On the **Project** tab, click **Lock**.

   A brief pop-up message will indicate that the environment is locked. The environment is now ready
   to promote to Production.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_28.png)
4. On the **Projects** tab, click **Promotion Options**, then do one of the following:
   1. Click **Promote Now**. The upgrade is pushed to Production immediately.
   2. Click **Promote Later** to schedule when the upgrade will be published to Production.

      ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_29.png)
5. On the **Project** tab, click **Calculation Queue** to verify the production build.
6. Compare the build numbers for the Development, Staging, and Production environments.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_30.png)

## Step 13: Close the merge trunk

1. Select the branch for the new template version (such as Version 104 Upgrade).
2. On the **Project** tab, click **Close Branch**.

   The **Confirm Close** dialog opens.
3. Click **OK** to close the branch.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_31.png)
4. Confirm that Trunk is no longer displayed in the navigation bar.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/8841_32.png)
5. **RECOMMENDATION**: Close the upgrade branch as soon as possible. The branch consumes the
   same amount of resources as the main trunk project. Closing the upgrade branch will free up
   resources and improve the overall performance.
