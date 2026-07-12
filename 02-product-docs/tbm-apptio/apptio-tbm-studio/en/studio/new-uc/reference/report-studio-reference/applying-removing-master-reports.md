---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Applying and Removing Master Reports"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Master Reports"
source_path: "studio/new-uc/reference/report-studio-reference/applying-removing-master-reports.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Applying and Removing Master Reports

**Apply a Master Report**

To apply a master report to a custom report:

1. **Check out** the custom report in edit mode.
2. Navigate to the **Report** tab in the ribbon.
3. Open the **Masters** drop-down list.
4. Select the master report you want to apply.
5. Save and check in the report.

**Remove a Master Report**

To remove a master report from a custom report:

1. **Check out** the custom report.
2. Navigate to the **Report** tab.
3. Open the **Masters** drop-down list.
4. Select **None** at the bottom of the list.
5. Save and check in the report.

**Deleting Master Reports**

To delete a custom master report:

1. In Report Edit mode, click the **Reports** section in the **Project Explorer**.
2. Filter the list of reports by **Master Reports** to display only masters.
3. **Check out** the master report you want to delete.
4. Click **Delete** on the **Home** tab.
5. **Check in** to complete the deletion.

Warning: Deleting a master report may affect all child reports that use it. Before
deleting, verify which reports depend on the master and either remove the master from those reports
or apply a different master.

**Parent topic:** [Master Reports](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
