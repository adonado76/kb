---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Set Up and Manage Cloud Financial Planning Integration"
breadcrumb:
  - "Planning"
  - "Integrations"
  - "Connect to Cloudability Financial Planning"
source_path: "it-planning/planning/cfp-integration.html"
images:
  - "resources/images/it_planning_images/cfp-drn.png"
  - "resources/images/it_planning_images/cfp-liv.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Set Up and Manage Cloud Financial Planning Integration

Note: Admin or Budget Process Owner roles are required to perform these tasks.

Important: Available with the ***Apptio Planning Standard****subscription*

Remember: The New View is enabled.

Cloud Financial Planning (CFP) Integration Settings are configured **per plan** within
Plan Settings. These settings establish the connection between Apptio Planning and the
specific **CFP Plan** and **Cost Ownership View**, and they define how Planning
dimensions (Department, Cost Center, Account, etc.) map to CFP’s cost ownership
structures.

**To configure CFP Integration Settings**

1. **Open the plan** you want to connect to CFP.
2. In the left navigation, go to **Plan Settings → Cloud Financial Planning
   Integration**.
3. On the CFP Integration Settings page, review the **generated environment details** (read‑only):
   - **Domain** – Your Apptio customer domain
   - **Environment Name** – Your Apptio environment name
   - **Cloudability Currency** – The currency configured in CFP
4. From the **View Name** dropdown, select the appropriate CFP Cost Ownership View.
5. Select the **Plan Name** from CFP. Only CFP Plans with the **same start year** as
   the current Apptio Planning plan will appear.
6. Configure the default mappings used when CFP Cost Ownership values do not have explicit mappings:
   - **Default Department** – Applied when a Cost Ownership value has no
     department-level mapping
   - **Default Cost Center** – Applied when no cost center mapping exists
   - **Default Account** – Applied when no account mapping exists
   - **Default Project**
     *(optional)* – Used if project mapping is needed
   - **Default Vendor**
     *(optional)* – Used when vendor mapping is relevant
7. Select the **Fill Forward** behavior that determines how CFP data is extended into
   future years in Apptio Planning:
   - **None** – No data is copied into years not present in the CFP Plan
   - **Copy Last Period** – The final period of the CFP Plan is copied to all remaining
     years
   - **Copy Last Year** – The final year of the CFP Plan is copied into all remaining
     years

## To configure Data Mappings

This configuration defines how **Cost Ownership values** in CFP map to the corresponding
**business dimensions** in Apptio Planning. These mappings ensure that all expenses
imported from CFP are assigned the correct Planning dimensions.

1. Each **Cost Ownership** value must be mapped to a **Department**, **Cost
   Center**, and **Account** for the mapping to be valid.
2. You may also optionally map Cost Ownership values to **Project** and **Vendor**
   dimensions.
3. To create a mapping, select a **Cost Ownership** value from the dropdown and choose
   the appropriate **Department**, **Cost Center**, **Account**, **Project**, and
   **Vendor** values from the respective lists.
4. You can also **upload mappings via CSV** for bulk updates.
5. During import, Apptio Planning performs reference‑data validation to ensure that the
   mapped **Department aligns with the Cost Center** and the **Project aligns with the
   Cost Center**.

Note: erence‑data validation check is performed during the CFP import process to ensure that
the mapped Department is correctly associated with the selected Cost Center, and that the
mapped Project is valid for that Cost Center.

## Import Plan Data from Cloud Financial Planning

Note: Admin or Budget Process Owner roles are required to perform these tasks. Additionally,
custom user roles with CanImportFromCloudability permission can also perform these
tasks.

***To import data from Cloud Financial Planning:***

- Open your plan and navigate to the **Cloud** tab within the **Expenses** > **New
  View**
- From the table level action menu (3-dot button), select **Import cloudability line
  items**
- On the import confirmation dialog, review the CFP Plan name and View Name and click the
  **Import** button.
- Once Import is complete, a success message with the number of lines imported will be
  displayed.
- In case of import errors, details will be displayed along with an option to download the
  CSV help file for further analysis of failed import.

***Import Behavior:***

1. Imported lines follow the **Fill Forward** setting defined in Plan Settings:
   - **None** – No data is projected into future years.
   - **Copy Last Period** – The final period of the CFP Plan is copied into future
     years.
   - **Copy Last Year** – The final year of the CFP Plan is copied into future
     years.
2. All lines imported from CFP are created as **External Lines**, meaning they are
   **read‑only** for all users.
3. Each imported line receives a unique **Line Item** **Code** prefixed with
   **CL** the first time it is imported into the plan.
4. Subsequent imports from CFP **overwrite existing CFP‑imported lines** with updated
   values while retaining the same Line Item Codes.
5. CFP‑imported lines are added to the **latest cost object version** and are visible
   only within departments where the importing user has edit access.
6. Imported cloud lines also appear in **Expenses → Summary** in read‑only mode with
   **Line Item** **Type = Cloud**.
7. Importing is **blocked** if the target department is locked due to budget
   submission.
8. For multi‑currency plans, all currency conversions follow the **Multi‑Currency
   Rates** defined in Apptio Planning.
9. To remove all CFP‑imported lines from the Cloud tab, use **Delete Cloudability line
   items** from the **table‑level actions** menu. This action deletes *all*
   CFP‑imported lines for the plan.

**CFP Line Item Detail View**

Note: User needs permission in CFP Plan to view detailed line item view.

1. Lines imported from CFP are displayed in Apptio Planning as summarized entries based on
   the Data Mapping configuration defined in the plan’s Cloud Financial Planning Integration
   settings.
2. To view the underlying detail, users can click the **Details** button in the
   **Details** column of the Cloud tab.
3. This opens a **read‑only drawer** that displays the lines from CFP plan.

![image of cf line item view](../../../../../03-media/apptio-planning/resources/images/it_planning_images/cfp-liv.png)

**CFP Data Refresh Notification**

**Note:** Viewing this notification requires the **CanImportFromCloudability**
permission.

1. When updates are made to the connected Plan in CFP, Apptio Planning displays a
   **notification banner** to users with the appropriate access—including **Admins**,
   **Budget Process Owners**, and users granted
   **CanImportFromCloudability**—indicating that new data is available to import.
2. To refresh the data in the Cloud tab, users can simply **re‑import the Cloudability
   line items**, which updates the plan with the latest information from CFP.

![image of cf data refresh notification](../../../../../03-media/apptio-planning/resources/images/it_planning_images/cfp-drn.png)

**Parent topic:** [Connect to Cloudability Financial Planning](../../it-planning/planning/connect-cfp.html)
