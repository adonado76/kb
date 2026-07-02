---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Represent a hierarchy code in perspectives"
breadcrumb: []
source_path: "studio/reports/hierarchy-codes-perspectives.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep219_151x368.png"
  - "resources/images/studio_images/studioimages/reports/rep220_151x369.png"
  - "resources/images/studio_images/studioimages/reports/rep221_150x369.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Represent a hierarchy code in perspectives

**Applies to**: TBM Studio 12.0 and later

When you publish a field to a custom perspective in the **Perspectives** section of the
**Project Explorer**, one of the options in the **Publish Field** dialog is **Represents a
hierarchy code**. If you check this option, it changes the behavior of the field when it is used
with a slicer. When a user enters text in the slicer search field, the option finds all values that
begin with the entered text plus one additional character. It then creates a group entry for each in
the slicer.

## Example

Assume you have the slicer shown in the following image. It is defined using a published field
without the **Represents a hierarchy code** option set. If you enter ABC in the search field, you
get the result shown in the following image:

| Standard slicer | Search result | Search result with the  hierarchy option set |
| --- | --- | --- |
| image Standard slicer | image Search result | image Search result with the  hierarchy option set |
