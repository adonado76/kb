---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Step 7: Review upgraded application in the upgrade branch"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step7.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-12.png"
  - "resources/images/ct_images/upgrade-from-v3-13.png"
  - "resources/images/ct_images/upgrade-from-v3-14.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Step 7: Review upgraded application in the upgrade branch

1. On the Project tab, click **Components**.

   The **Component Configuration** dialog box
   opens.
2. Verify that the builds have finished.

   You will see a list of the individual
   check-ins.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-12.png)
3. In the navigation bar, select **Cost Transparency** from the Application menu.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-13.png)
4. Select the upgrade branch (for example, **Version 104 Upgrade**).
5. The new home page will appear.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-14.png)

   Note: If TBM
   Review appears in the menu bar and the new landing page is not displayed, you will need to change
   the landing page from TBM Review to Service Costing using the "params" data set, as follows:
   1. Return to **TBM Studio**.
   2. On the **Project** tab, open the **Tables** section in the
      left pane.
   3. Type "params" in the search box.
   4. Click **Params**.
   5. Check out the document.
   6. Click the **Upload** transform step.
   7. Click **Params.csv**, then select **Download**.
   8. Open Excel.
   9. Change the value for the column "InitialReport" to ".View:tab:Service Costing."
   10. Click **Save**.
   11. Click **Params.csv,** then select **Overwrite**.
   12. Select the saved file and upload it into Apptio.
   13. Click the **Table** transform step.
   14. Verify that the **InitialReport** value has changed to ".View:tab:Service
       Costing."
   15. Click **Save**.
   16. Check in the change.

## Related information

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
