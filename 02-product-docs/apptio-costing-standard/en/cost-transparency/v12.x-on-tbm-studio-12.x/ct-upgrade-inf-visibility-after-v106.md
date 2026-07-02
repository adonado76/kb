---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Update visibility of Infrastructure reports after v106 upgrade"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/ct-upgrade-inf-visibility-after-v106.html"
images:
  - "resources/images/ct_images/ct-upgrade-inf-vis-1.png"
  - "resources/images/ct_images/ct-upgrade-inf-vis-2.png"
  - "resources/images/ct_images/ct-upgrade-inf-vis-3.png"
  - "resources/images/ct_images/ct-upgrade-inf-vis-4.png"
  - "resources/images/ct_images/gear_icon.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Update visibility of Infrastructure reports after v106 upgrade

Beginning with TBM Studio 12.6 (with Template v106), the Infra
Server and Storage reports moved to the Infrastructure Insights report collection from the
Infrastructure & Cloud report collection in Costing Standard. Because of
this change in navigation, the default in Enhanced Access Administration
shows that the reports are viewable by Nobody, which can create confusion when you try to access
your old reports.

Applies to: Costing Standard on TBM Studio 12.6 and later, with
Template v106 and later

To correct the navigation, use the following steps to reconfigure the CT Server and Storage
components.

## Upgrade to 12.6

1. Be sure to upgrade the following components during your upgrade to TBM Studio 12.6:
   - CT Apps - Data Centers
   - CT Apps - Servers
   - CT Apps - Storage

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-1.png)

   For more information, see [Upgrade Costing Standard from template v104+ to the latest
   version](../../cost-transparency/v12.x%20on%20tbm%20studio%2012.x/upgradect-v104.htm "(Opens in a new tab or window)").
2. Click the Settings ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/gear_icon.png) icon, then
   click Access Administration.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-2.png)
3. Click the Applications tab.
4. In the Infrastructure Insights row, click Show.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-3.png)

The Visible to column changes from Nobody to Visible to any user with permissions for Costing Standard.

The Costing Standard report menu now shows Infrastructure Insights. If you click Infrastructure
& Cloud, you will be rerouted to the updated path of the Infrastructure reports.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/ct-upgrade-inf-vis-4.png)

## TBM Studio (12.6 and later) reports in Infrastructure Insights

Beginning with 12.6, the following reports are still in the Costing Standard core, but they are
also visible in Infrastructure Insights:

- Compute:
  - Utilization Summary
  - Host Server Details
  - By Applications
- Data Centers:
  - Summary
  - Operational Summary
  - Financial View
- Storage:
  - Utilization Summary
  - By Applications
- Service Desk:
  - Summary
  - Task Details
  - Resource Details
  - By Applications

## Costing Standard (12.5 and earlier) reports in Costing Standard components

The following reports comprised the core of Costing Standard before 12.6.

- Compute:
  - Summary
  - Spend Profile
  - Operational Summary
  - Logical Server Details
  - Financial View
- Storage:
  - Summary
  - Spend Profile
  - Operational Summary
  - Device Details
  - Storage LUN Details
  - Financial View

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
