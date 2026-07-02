---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Filter slicers"
breadcrumb: []
source_path: "studio/reports/filter-slicers.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep046.png"
  - "resources/images/studio_images/studioimages/reports/rep143.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Filter slicers

**Applies to**: TBM Studio 12.0 and later

To limit the values displayed in the slicer, add one or more filters to the slicer. When a user
views the slicer, they will see the filtered results. A slicer before and after filtering is shown
in the following image:

![Filter slicers](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep046.png)

## Add a filter to a slicer

1. Drag a field from the **Project Explorer** into the **Filters** area of the **Slicer
   Configuration** pane.
2. Right-click on the field and select **Edit Filter** from the pop-up menu. The **Edit
   Filter** dialog is displayed as shown in the following image:![Add a filter to a slicer](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep143.png)
3. Select the values you want displayed in the slicer and click **OK**.
   - To add a custom value to the list, click the **Add a custom filter** link.
   - The **Values not currently shown option**, when checked, will include all values that cannot
     be displayed in the filter because they exceed the 1,000 value limit.
   - If there are more than 1,000 values available in the filter, you will see a message alerting you
     to that fact and suggesting you use the Filter box at the top of the list to find additional
     values.

## Publish the filter to a perspective

As with other object-based report components, you can publish a filter to a custom perspective.
The published filter can be used when creating other components.

To publish a filter:

1. Right-click the filter in the **Filters** area.
2. Point to **Publish** and select an existing perspective or create a new perspective.

## Remove a filter from a slicer

To remove a filter from a slicer, perform one of the following actions:

- Drag the filter out of the **Filters** area.
- Right-click the filter in the **Filters** area and select **Remove** from the pop-up
  menu.
