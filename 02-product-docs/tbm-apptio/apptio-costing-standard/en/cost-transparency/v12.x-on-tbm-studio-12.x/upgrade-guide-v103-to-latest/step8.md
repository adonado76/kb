---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Step 8: Compare v103 reports to reports on the new template version"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step8.html"
images:
  - "resources/images/ct_images/upgrade-from-v3-15.png"
  - "resources/images/ct_images/upgrade-from-v3-16.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Step 8: Compare v103 reports to reports on the new template version

1. Open the Costing Standard project in a browser.
2. Select **Trunk** to view the Template v103 reports.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-15.png)
3. Open the Costing Standard project in another browser.
4. Select the branch for the new template (such as **Version 104 Upgrade**) to
   view the updated reports.
5. Review reports side-by-side.

   ![](../../../../../../03-media/apptio-costing-standard/resources/images/ct_images/upgrade-from-v3-16.png)
6. If desired, re-apply customer-specific changes to the reports directly in the branch for the new
   template version (for example, Version 104 Upgrade).

   Note:
   - Avoid making changes to out-of-the-box reports so you can minimize the effort involved with
     future upgrades.
   - If report customizations must be made, apply them to the out-of-the-box reports after you
     complete Step 7, merge the upgrade changes. This will minimize the amount of time you have to work
     in the Version 104 Upgrade branch. Remember, DO NOT make changes (other than data loads) into the
     main project (Trunk) after you create your Upgrade branch.
7. After you verify that the reports use the template version you want, proceed to Step 9 to merge
   the changes into your main project.

See [Mapping Cost Transparency
reports from Template v103 to v104](../../reports-v104/mappingctreports103to104.html) to understand where the v103 reports and related
information appear in v104.

## Related information

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
