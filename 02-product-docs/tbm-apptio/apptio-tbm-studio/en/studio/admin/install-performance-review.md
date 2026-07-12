---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Install the Performance Review component"
breadcrumb: []
source_path: "studio/admin/install-performance-review.html"
images:
  - "resources/images/studio_images/studio-components-version_cropped.png"
  - "resources/images/studio_images/studio_admin_analyze_performance_sui.png"
  - "resources/images/studio_images/studioimages/checkin_sui.png"
  - "resources/images/studio_images/studioimages/components_sui.png"
  - "resources/images/studio_images/studioimages/customized-element-sui.png"
  - "resources/images/studio_images/studioimages/perf-rev-upgrade_sui.png"
  - "resources/images/studio_images/studioimages/project-settings-sui.png"
  - "resources/images/studio_images/studioimages/revert-check-out_sui.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Install the Performance Review component

Applies to: Apptio Costing Standard on TBM Studio 12.5 and later. The Performance Review
component is an in-application utility that creates reports that an Apptio TBM Studio Admin can use
to gain insight into the impact their current project configuration has on application
performance.

## Availability

| Platform Version | Content Version |
| --- | --- |
| R12.5 and later | v.105 content payload |
| R12.9.3 | v.109 content payload |

Note: To install the component, you must be on a platform version that supports the associated
content version.

## Prerequisites for installation

Follow these steps to verify your environment has access to a suitable content version:

1. Open TBM Studio in the project where you want to install the Performance Review component.
2. Navigate to Project > Project Settings.
3. To validate the content version, in Component Version, make sure Version 109 is available to
   select.
4. Click Cancel.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio-components-version_cropped.png)

## Install the Performance Review component on a project with v.109 content configured

If your project is currently using the v.109 content version, follow these steps to install the
Performance Review component.

1. On the Project tab in the Project Data group, click Components.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/components_sui.png)
2. Click Performance Review.
3. On the Component Installation dialog, click Enable.

After you finish installing the component, the Analyze Performance reports appear in the Project
Explorer under Reports > Service Costing > Analyze Performance.

## Install the Performance Review component in a project with a content version earlier than v.109

If your project is not using the v.109 content version, but you do see it in the Components
Version drop down in Project Settings per the Prerequisites at the beginning of this document, then
you can still install it without committing to a full upgrade of content or even saving the content
version change.

Follow these steps to install the Performance Review component without having to migrate to v.109
content templates.

1. On the Project tab in the Project Setup group, click Project Settings.
2. In the Components Version drop-down list, select Version 109, then click Save.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/project-settings-sui.png)
3. On the Project tab, in the Project Data group, click Components. You should now see the
   Performance Review component.
4. Click Performance Review.
5. On the Component Installation dialog, click Enable. After you finish installing the component,
   the Analyze Performance reports appear in the Project Explorer under Report > Service Costing >
   Analyze Performance.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studio_admin_analyze_performance_sui.png)
6. From the menu ribbon at the top of the screen, select Home > Revert Changes.
7. In the Revert Check Out dialog, select Project Settings, leave all other options unselected, and
   click Revert Check Out.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/revert-check-out_sui.png)

   You have
   now reverted the Project Settings.
8. From the menu ribbon, select Home > Check In.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/checkin_sui.png)

   You have now
   checked in the new version of the Performance Analyzer.

## Upgrading the Performance Review component

If you already have an older version of the Performance Review component installed, you must
revert existing customizations. Follow these steps.

1. From the menu ribbon at the top of the screen, select Project > Components > Performance
   Review.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/components_sui.png)

   If there are customizations present they will appear toward the bottom of the page. To
   revert the customized elements, click on the arrow next to the customization. Do this for each
   customization.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/customized-element-sui.png)
2. Navigate to the Project Settings and change the Components Version to Version 109.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/project-settings-sui.png)
3. Navigate back to Components > Performance Review.
4. Scroll down if needed and click Upgrade.

   ![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/perf-rev-upgrade_sui.png)

## Use the Performance Review component

For information about using the Performance Review component and the Analyze Performance reports,
see [Use the Performance
Review component](use%20the%20performance%20review.htm "(Opens in a new tab or window)").
