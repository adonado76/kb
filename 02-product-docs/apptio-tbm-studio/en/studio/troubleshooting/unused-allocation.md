---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Unused Allocations"
breadcrumb: []
source_path: "studio/troubleshooting/unused-allocation.html"
images:
  - "resources/images/studio_images/ua-1.jpg"
  - "resources/images/studio_images/ua-2.jpg"
  - "resources/images/studio_images/ua-5.jpg"
  - "resources/images/studio_images/ua-6.jpg"
  - "resources/images/studio_images/unusd-alloc.jpg"
  - "resources/images/studio_images/za-1.jpg"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Unused Allocations

Navigate to  **TBM Studio**  >�  **Recommendations**  tab >  **Zero Unit
Allocations**  , and then select  **Troubleshoot All Identified Problems**  .

![Unused Allocations](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/unusd-alloc.jpg)

Switch to  **Development**  workspace and select  **Next**  .

![Recommendations Wizard](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-1.jpg)

You can see the issue description and what actions will be taken to resolve it. Unused
Allocations are listed under each model object. I can see unused allocations by Allocation Name, To
Object, and Tagged Metrics for the AWS Cost Allocation Bill object.

![Unused Allocations](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-2.jpg)

Select the  **Delete Allocation**  button to fix individually.

Scrolling down to the "Applications" model object, one can see Allocations with multiple Tagged
Metrics. Metrics in "black" are active allocations, whereas metrics in "red" are unused allocations.

I have selected the checkbox for  *App Dev\_Budget,Budget*  Business Services and selected
 **Perform selected fixes for Applications**  button.

![ Delete Allocation](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/za-1.jpg)

Similarly take appropriate action for rest of the sections.

Once complete, a the status of the Unused Allocation changes.

![Done](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-5.jpg)

Select  **Next**  , and then select  **Checkin**  in the last page.

![Checkin](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/ua-6.jpg)
