---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "admin"
title: "How to find Unused Documents"
breadcrumb: []
source_path: "admin/lineage-unused-docs.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# How to find Unused Documents

Under Project tab, Enable Feature, click on Enable Show Unused Documents. Now this feature will
be available in Project tab itself to use. Let’s select it and its going to open a list of table
that has any calculated metric, table name or report that has been user introduced but not used by
anything. So this actually gives you an opportunity to remove these entities.

![](../../resources/images/studio_images/unused-doc.png)

Note: The results for Unused documents are shown only while using Lineage, where we are not
considering any external project dependencies, and there is a prospective future scope for it. In
such cases, we may tend to remove any entity, but ensure to double check that it is not used in any
other project.
