---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Creating Collections"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Collections"
source_path: "studio/new-uc/reference/report-studio-reference/creating-collections.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Creating Collections

**Creating a New Collection**

Only Administrators can create report collections, and collections can only be created in the
Costing Standard project. Once created, collections are available across the entire project, and
other users with appropriate permissions can add and remove reports from the collection.

**To create a custom report collection:**

1. On the **Project** tab, in the **Project Data** group, click **Report Collections**.
2. In the **Manage Report Collections** dialog box, click **Add Collection**.
3. A new entry named "New report collection" is added to the list of collections.

1. To change the name, click the "New report collection" entry in the list, then click the
   collection name in the **Selected Collection** field to edit it.
2. Click **Close** to save the collection.

**Note:** You cannot delete out-of-the-box (OOTB) report collections. Only custom collections
can be deleted.

**Collection Metadata**

Each report collection has the following configurable metadata:

|  |  |
| --- | --- |
| **Property** | **Description** |
| Name | The display name shown in the collection navigator and management dialogs. Choose a clear, descriptive name that helps users understand the collection's purpose. |
| Color Palette | (R12.10.10 and later) An optional custom or preset color palette applied to all charts in reports within the collection. Individual reports can override the collection palette. |
| Reports | The list of reports assigned to the collection. Reports are displayed in the order they appear in this list. |

**Deleting a Collection**

**To delete a custom report collection:**

1. On the **Project** tab, in the **Project Data** group, click **Report Collections**.
2. In the **Manage Report Collections** dialog box, select the collection you want to delete.
3. Click the **Delete Collection** button.

Warning: Deleting a collection removes the grouping but does not delete the reports
themselves. Reports that were in the deleted collection will no longer have a collection assignment.

**Parent topic:** [Report Collections](../../../../studio/new-uc/reference/report-studio-reference/report-collection.html)
