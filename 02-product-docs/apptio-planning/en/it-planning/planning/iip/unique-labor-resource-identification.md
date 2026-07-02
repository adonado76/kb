---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Using External Codes to Identify Labor Resources"
breadcrumb:
  - "Planning"
  - "Project Labor Activity Planning"
source_path: "it-planning/planning/iip/unique-labor-resource-identification.html"
images:
  - "resources/images/it_planning_images/extla-1.png"
  - "resources/images/it_planning_images/extla-s2.png"
  - "resources/images/it_planning_images/extla-s3.png"
  - "resources/images/it_planning_images/lap-5.22release.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Using External Codes to Identify Labor Resources

Important: *Available with the* ***Apptio Planning Standard****subscription*

Remember: *Integrated Investment Planning (IIP) feature is enabled*

By default, labor resources are identified in **Labor Activity** by **Resource Name**.
When two or more resources share the same name, it becomes difficult to distinguish them
during allocation. This creates challenges both in the UI and when importing Labor Activity
data.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/extla-1.png)

To ensure every resource is uniquely identifiable, Apptio Planning supports assigning an
**External Code** (such as Employee ID or Position ID) to each labor resource. When
enabled, resources appear as **<External Code> – <Name>**, allowing accurate project
allocation, clean imports, and reliable synchronization with external labor management
systems.

## Configuring External Code

To uniquely identify resources, you can enable **External Code** and assign a unique
identifier from your HR or labor system.

**Step 1 — Enable External Code**

Note: *Admin or Budget Process Owner roles are required to perform this task.*

1. Navigate to **Settings (Gear icon)** → **Company Profile**.
2. Enable the **External Code** option.
3. The **External Code** column will appear in **Expenses** → **Labor**.

For more details, see [External Codes](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=configuration-external-unique-identifier "(Opens in a new tab or window)").

**Step 2 — Assign External Codes to Labor Resources**

In the **Expenses** → **Labor** tab, assign a unique **External Code** for each labor
resource:

- **Existing Employees:** Use Employee ID, Employee Number, or another unique identifier from
  your HR system.
- **Planned Labor:** Use Position ID or a unique placeholder code.
  - When the position is filled, replace the Position ID with the actual Employee ID.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/extla-s2.png)

**Step 3 — View External Codes in Labor Activity**

In the **Expenses** → **Labor Activity** tab, the **Resource** dropdown will now display
resources as:

**<External Code> – <Name>**

This ensures that identical names can be distinguished clearly.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/extla-s3.png)

Note: After you select a resource, the **Resource** column will display only the resource’s name.
The External Code remains visible in the **Resource: External Code** column.

## Using Resource External Codes in Imports

- When exporting a Labor Activity template, the file will include the **Resource External
  Code** column.
- **To Import** labor activity lines using Resource External Code follow the steps mentioned
  below:
  1. Enter an External Code (e.g., Employee ID) for labor line items.
  2. Create a Labor Activity import CSV file, ensuring the Resource: External Code column is
     populated with the corresponding External Code for each labor resource.
  3. Navigate to Expenses > Labor Activity, and from the Actions menu, select Import Labor Activity.
  4. In the Import File dialog, select Update Data.
  5. Choose Resource: External Code from the dropdown.
  6. Click Import.
- Import Result:
  - The system will update Labor Activity lines in the plan by matching records based on the
    Resource: External Code values in the CSV file.
  - If there are multiple Labor Activity lines using the same Resource:External Code and user is
    importing with Update Data option, a combination of Resource: External Code and Line Item Code will
    be used to uniquely identify lines to be updated.

    ![image of importing using external codes](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/lap-5.22release.png)

Note: Importing Labor Activity data using **Resource:External Code** is currently not supported
for imports via Apptio Costing through Automated Data Manager.
