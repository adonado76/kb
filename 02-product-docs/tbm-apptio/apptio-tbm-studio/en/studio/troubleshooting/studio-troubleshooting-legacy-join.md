---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Legacy model join operation used"
breadcrumb: []
source_path: "studio/troubleshooting/studio-troubleshooting-legacy-join.html"
images:
  - "resources/images/studio_images/troubleshooting/legacy-join-automatic-relationship-checkbox.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-link-to-issue.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-locate-legacy-allocation.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-source-and-destination-columns-2.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-source-and-destination-columns.png"
  - "resources/images/studio_images/troubleshooting/legacy-join-warning.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Legacy model join operation used

The *Legacy model join operation used* error is a result of the way data
relationship allocations were created in the R11 version of TBM Studio. Some of the default
allocations are configured this way to maintain backwards compatibility with current versions, as
well as to minimize friction when upgrading content.

## About this task

The data relationship as shown:

| Data relationship comparison | |
| --- | --- |
| R11 legacy data relationship in TBM Studio R12 | TBM Studio R12 data relationship |
| In the R12 version of TBM Studio, this type of error, specifically the **Automatic relationship** checkbox, displays as seen below. | In R12, data relationship allocations are created by determining which column data should match between objects. Below, you can see the source and target columns selected. |

## Configuration recommendation for the Legacy model join operation used error

Note: Due to object versioning, you may have to fix the issue in several different time periods for
the same object.

To resolve this error:

1. In the Document row, select the link to open the affected object.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-link-to-issue.png)
2. In the Home tab, select Check Out.
3. Go through the outbound allocations until you locate the legacy allocation and then select
   it.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-locate-legacy-allocation.png)

   You are redirected to the appropriate Model object and the time period the legacy allocation
   exists in. Allocations used for all available metrics are listed, not just the one that is selected.
   Go through the available allocations one by one until you locate the legacy allocation. Currently,
   TBM Studio cannot directly navigate you to the exact allocation line.
4. In Distributing, clear the Automatic relationship checkbox and save the changes.
5. Select Yes to continue.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-warning.png)
6. In Source Column and Destination Column, select the required values to establish new data
   relationship for the allocation line.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/troubleshooting/legacy-join-source-and-destination-columns-2.png)

   You can use one or more data relationships as needed.
7. Confirm the changes and validate that the allocation is functioning as desired. You can compare
   the performance of the new configuration with the previous configuration still available in
   Staging.
8. Check in the changes if new performance is satisfactory.

Warning: You cannot re-enable the legacy configuration for this allocation after
you check in your new configuration. Apptio Support can assist in recovering legacy configurations
if needed.
