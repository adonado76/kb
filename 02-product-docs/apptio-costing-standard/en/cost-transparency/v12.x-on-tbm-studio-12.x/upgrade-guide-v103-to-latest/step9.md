---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Step 9: Merge changes into the main project (Trunk)"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step9.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-17.png"
  - "resources/images/ct_images/upgrade-from-v3-18.png"
  - "resources/images/ct_images/upgrade-from-v3-19.png"
  - "resources/images/ct_images/upgrade-from-v3-20.png"
  - "resources/images/ct_images/upgrade-from-v3-21.png"
  - "resources/images/ct_images/upgrade-from-v3-22.png"
  - "resources/images/ct_images/upgrade-from-v3-23.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Step 9: Merge changes into the main project (Trunk)

Refer to [Branching, Hotfix, and Branch best practices](https://community.apptio.com/docs/DOC-5472 "(Opens in a new tab or window)") in Product Central.

1. Return to **TBM Studio**.
2. Select the upgrade branch (for example, Version 104 Upgrade).
3. On the **Project** tab, click **Check In History**.
4. Scroll down to the bottom of the list, then click the first item above the “bootstrap” entries,
   for example, "Project Settings: change to v104" check-in.

   Note: You can select
   additional items to check in as a single merge, but select no more than 5 items at one time. Merging
   more than 5 items in a single check-in could cause the application to fail.
5. Right-click the line item and select **Merge changes to branch**.

   For the
   screenshots in this example, we will use the CT-Apps Application merge item.
6. Select **Trunk** as the recipient of the merge.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-17.png)

   The **Merge
   Changesets** dialog box opens.
7. Select all items for merge (default).

   Note: Do not de-select any individual items.
   All items are merged whether selected or not.
8. Click **OK**.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-18.png)

   **RECOMMENDATION:** Manually track your merged steps as you upgrade the components
   because the Check In History dialog won't indicate which items have been merged. If you attempt to
   check in an item twice and the following message appears, click **Cancel**, then proceed with a
   different component.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-23.png)
9. After complete, the window might switch to **Trunk**.
10. Change to **Trunk** to check in the merged item in your project.
11. To verify that the change has propagated to the Development environment:
    1. In the navigation bar, select the **In Development** environment.
    2. Click the **Project** tab.
    3. Click **Components**.
    4. Verify that the component no longer displays the upgrade arrow, as in this example, for the
       CT-Apps Application component. ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-19.png)
12. From the Environment menu in the navigation bar, select **Staging**.
13. In the **Project** ribbon, ensure that the Locked icon is grayed out (not locked).

    You
    need to do this only once.
14. Click **Components**, and notice that the CT Apps Applications component displays the upgrade
    arrow for v103.
15. From the Environment menu in the navigation bar, select **In Development**, then click
    **Check In**.

    The **Check In** dialog opens.

    Note: If the **Check In**
    icon on the ribbon is grayed out, you might need to wait a few minutes for the documents to be
    processed, then go to the **Staging** environment, then back to the **Development**
    environment, and try again.
16. Select all items in the left pane (default). This should be limited to the merged items.
17. Enter a description of the items in the **Message** panel.

    **RECOMMENDATION:** Use a useful description such as "Merge – CTF- Cost Source: revert data
    set changes, upgraded component."
18. Click **Check In**.

    ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-20.png)

    Wait for the build to
    complete.

    ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-21.png)
19. Verify that the expected change from the branch merge step is applied to the Staging
    environment.

    In this example, on the **Project** tab, click **Components** to verify that
    v104 is now active.

    ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-22.png)
20. Return to the upgrade branch (for example, Version 104 Upgrade) to proceed with the next item to
    merge.

Known issues:

- **Error message** — The first item merged should be the **Project Settings change to
  v104** (or whatever version you're upgrading to). After you merge the item, you might see an error
  message, “Server Error: Contact your administrator.”

  **Solution** — Exit the browser, re-open
  the browser, then proceed with the check-in step in Trunk. After the upgrade branch change is made
  and propagated to Staging, you should no longer see the error message.
- **Conflicting information in the navigation bar** — When switching between Trunk and the
  branch for the new template (such as Version 104 Upgrade), the new upgrade branch might appear in
  the navigation bar while the Check In History is from Trunk. If this occurs, follow these steps:
  1. Close the **Check In History** dialog, and perhaps all other dialogs.
  2. Change to **Trunk**.
  3. Change back to the **Version 104 Upgrade** branch.
  4. Re-open the **Check In History**.
  5. Proceed with merging the next step.
- **Merging disable components** — After a merged step for a disabled component, the items from
  the previous merge might still be listed in the left panel.

  **Solution** — Enter the
  appropriate description for what was just merged (for example, "Merge – ATUM 2.0 component
  disabled"). When the calculation is finished, you can verify the expected changes in
  Staging.

## Related information

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
