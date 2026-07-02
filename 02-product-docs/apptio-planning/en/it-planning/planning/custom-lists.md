---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Custom Lists"
breadcrumb:
  - "Planning"
  - "Configuration and Administration"
source_path: "it-planning/planning/custom-lists.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Custom Lists

Note: *Admin or Budget Process Owner roles are required to manage custom lists.*

Custom Lists allow administrators to define a set of allowable values for a single attribute
in a line-item table. They are commonly used to standardize data entry—for example, creating a
*Status* list with values like Screened, Interviewed, and Hired for use on Labor line
items.

## Create a Custom List

1. Navigate to **Configuration** → **Custom Lists**.
2. Select **Add** (➕).
3. Enter a **name** for the list.

   Note: List names cannot be renamed later.
4. In the **Values** section, click **Add**(➕) to enter values.
5. Use the drag handle (⋮⋮) to reorder values, or select **Delete** (🗑) to remove them.
6. When finished, click **Add** to finalize the list.

## Using Custom Lists in Line Item Schemas

Custom Lists are used to create single-attribute picklists that can be added to any line-item
schema as a custom attribute.

1. Navigate to **Configuration → Schema** and select a schema type.
2. Select **Add** to create a custom attribute.
3. Set **Data Type = List**.
4. Choose the **Custom List** you previously created.
5. Click **Add** to create the list attribute.

Once added, the attribute will appear as a dropdown field in the associated line-item
table, ensuring standardized and controlled data entry for end users.
