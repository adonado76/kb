---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "troubleshooting"
title: "Assignment Ratio table is too large"
breadcrumb: []
source_path: "troubleshooting/studio-troubleshooting-assignment-ratio.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Assignment Ratio table is too large

The Assignment Ratio limiter prevents the creation of Assignment Ratio tables that are
too large.

The largest size for allocation Assignment Ratio tables is determined by the following factors:

- The identifier row count of the source table
- The identifier row count of the destination table

  ![](../../resources/images/studio_images/troubleshooting/assingment-ratio-too-large-rec.png)

This error is typically caused by not using a Data Relationship style allocation. Without using
Data Relationship, a large *many to many* or *all to all* types of allocations are
created. Such allocations have low performance and reduce the effectiveness of allocations.

## Configuration recommendation for the Assignment Ratio table is too large error

To resolve this error, you can do one or more of the following:

- Add Data Relationship to the affected allocation.

  ![](../../resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution.png)
- Add a From or To filter to the affected allocation.

  ![](../../resources/images/studio_images/troubleshooting/assingment-ratio-too-large-solution-2.png)
- Reduce the number of identifier rows in the source objects.
- Reduce the number of identifier rows in the target objects.
