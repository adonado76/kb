---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Step 12: Upgrade the Production environment"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step12.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-26.png"
  - "resources/images/ct_images/upgrade-from-v3-27.png"
  - "resources/images/ct_images/upgrade-from-v3-28.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Step 12: Upgrade the Production environment

After you finish verifying the reports, push the upgraded application to Production.

1. Go to **TBM Studio**.
2. Select the **Staging** environment.
3. On the **Project** ribbon, click **Lock**.

   A brief
   pop-up message will indicate that the environment is locked. The environment is now ready to promote
   to Production.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-26.png)
4. On the **Projects** ribbon, click **Promotion Options**,
   then do one of the following:
   - Click **Promote Now**. The upgrade is pushed to Production immediately.
   - Click **Promote Later** to schedule when the upgrade will be published to
     Production.

     ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-27.png)
5. On the **Project** ribbon, click **Calculation Queue** to
   verify the production build.
6. Compare the build numbers for the Development, Staging, and Production environments.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-28.png)

## Related information

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
