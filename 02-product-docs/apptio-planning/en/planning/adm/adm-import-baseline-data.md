---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Import Plan baseline data from Costing Standard"
breadcrumb: []
source_path: "planning/adm/adm-import-baseline-data.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Import Plan baseline data from Costing Standard

When Automated Data Management is enabled (see Enable Automated Data Management
Integration in ApptioOne Plan), the **Entity Mapping** page in **Automated Data Management**
is updated with the following new entities:

- **A1Plan Labor** - Entity that represents the labor line items in the planning **Expenses >
  Labor**
- **A1Plan Contract** - Entity that represents the contract line items in the planning
  **Expenses > Contract**
- **A1Plan Asset** - Entity that represents the asset line items in the planning **Expenses >
  Asset**
- **A1Plan Financial** - Entity that represents the financial line items in the planning
  **Expenses > Other**
- **A1Plan Labor Activity** - Entity that represents the labor activity line items in the
  planning **Expenses > Labor Activity**. This is applicable only if **Integrated Investment
  Planning** feature is enabled. For more information, see [Admin or Budget Process Owner tasks](https://help.apptio.com/en-us/it-planning/planning/iip/admin-bpo-tasks.htm "(Opens in a new tab or window)").

These entities facilitate mapping to the corresponding datasets in ApptioOne Cost which can then
be imported to the respective Expenses tabs in the selected plan in ApptioOne Plan.

Note: Ensure that **Automated Data Management > Entity Mapping** has the appropriate Costing
& Planning Cost dataset mapping. You can do this in either of the following ways:

- Use the data templates installed by the **ApptioOne Plan Integration** component.
- Create your own tables in **TBM Studio** that you want to import into Planning, and map them
  to the entities mentioned above.

After you make any changes in the datasets that are mapped with **A1Plan Contract**, **A1Plan
Asset**, **A1Plan Labor Activity**, **A1Plan Labor** or **A1Plan Labor Activity** and
check these changes in, Costing will send them to the calculation queue. Once the calculation is
complete in the development environment, you can import these changes into Planning by following the
steps below:

1. On the left navigation menu, select **Planning > Expenses**.

   Ensure that you have enabled
   the **New View**. For information on enabling **New View**, see [Working with Apex tables](https://help.apptio.com/en-us/it-planning/planning/working-with-apex-table.htm "(Opens in a new tab or window)").
2. From the top left menu, select the plan (budget or forecast) to which you want to import changes
   from Costing.
3. Navigate to the desired Expenses category for which you want to import the data.
4. Select ![](https://help.apptio.com/en-us/resources/images/icons/3-dots_20x20.png) from the top left of the table view, and select **Import from cost
   transparency...**.

   ![](https://help.apptio.com/en-us/resources/images/it%20planning_images/import_plan_baseline_fromct.png)
5. To import lines from Apptio Costing by Replacing all existing data, select **Replace All
   Data** option and then select**Import**.

   Note:

   The beta version supports only the **Replace All Data** option. This option does an import by
   deleting all existing data from the selected tab and replacing it with the data imported from the
   Costing dataset.

   While imported data is validated against the plan’s reference data, you may receive import
   warnings related to row modifications or row omissions. An import confirmation dialog might be
   displayed in such a case.
6. Select **Import with Issues** if you want to proceed with the import after validating the
   import validation warnings. Select **Go Back** if you want to go back to the Import options
   page.
7. Updating existing plan data with changes from Apptio Costing is supported if **External
   Code** feature is configured. To learn more about **External Code** feature, visit [here.](https://help.apptio.com/en-us/it-planning/planning/external-unique-identifier.htm "(Opens in a new tab or window)")
8. Ensure the existing plan lines have **External Code** defined and the same **External
   Code** is also used in the Apptio Costing dataset. Lines from Apptio Costing and Apptio Planning
   will be matched using the **External Code** to make updates.
9. To update existing plan data with the changes from Apptio Costing, select <…> from the top
   left of the table view, and select **Import from cost transparency...**.
10. Select Update Data option and click Import.

Note: If **External Code** feature is disabled, you won’t be able to use Update Data option when
importing plan data from Cost Transparency. Carefully understand all the Upload Cases described in
https://help.apptio.com/en-us/it-planning/planning/external-unique-identifier.htm to avoid any
unwanted results after you import data using Update Data option
