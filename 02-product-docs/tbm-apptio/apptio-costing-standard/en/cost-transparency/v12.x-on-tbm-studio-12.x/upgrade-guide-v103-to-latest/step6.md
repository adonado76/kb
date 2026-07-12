---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Step 6: Upgrade all other components in the Upgrade branch"
breadcrumb: []
source_path: "cost-transparency/v12.x-on-tbm-studio-12.x/upgrade-guide-v103-to-latest/step6.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Step 6: Upgrade all other components in the Upgrade branch

All installed components need to be upgraded to the new template version. It is recommended that
you start with the lower level components (for example, CTF- components, then CT Apps, etc.).
However, you do not need to follow an exact order. For this example, the installed components are
for a CT Base configuration on Template v103.

Note: If you open the Costing Standard project during the upgrade process, you'll
notice that some of the navigation links are broken in the upgrade branch. These will be resolved
when all components have been upgraded.

Repeat Steps 4 and 5, to continue upgrading all the other components. The following order is
recommended; however, you might not have all these components installed in your environment:

- **TBM Review** component:
  - Disable the component.
  - Check in the change, "TBM Review: disable component."
- **ATUM v2.0** component:
  - Disable the component.
  - Check in the change, "ATUM v2.0: disable component."
- **CTF- Cost Source** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Remap the source files to the Cost Source Master Data set, if you reverted data set
    changes.
  - Check in the change, "CTF- Cost Source: revert calculated metrics, upgrade component."
- **CT- Quality** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Check in the change, "CT- Quality: upgrade component."
- **CTF-Labor** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Remap the source files to the Labor Master Data set, if you reverted data set changes.
  - Check in the change, "CT- Labor: upgrade component."
- **CTF- IT Towers** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Remap the source files to the IT Resource Tower Master Data set.
  - Check in the change, "CTF- IT Towers: revert calculated metrics, upgrade component."
- **CTF- Time Tracking** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Remap the source files to the Time Tracking Master Data set, if you reverted data set
    changes.
  - Check in the change, "CTF- Time Tracking: upgrade component."
- **CTF- Projects** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Remap the source files to the Projects Master Data set, if you reverted data set changes.
  - Check in the change, "CTF- Projects: upgrade component."
- **CTF- Cloud Service** component:
  - Revert any data set, calculated metric, or report customizations.
  - Upgrade the component.
  - Check in the change, "CTF- Cloud Service: revert calculated metrics, upgrade component."
- **CTF- Amazon Web Services** component:
  - Revert any data set, calculated metric, or report customizations.
  - Upgrade the component.
  - Check in the change, "CTF- Amazon Web Services: upgrade component."
- **CTF- Azure** component:
  - Revert any data set, calculated metric, or report customizations.
  - Upgrade the component.
  - Check in the change, "CTF- Azure: upgrade component."
- **CT Apps- Applications** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Remap source files to the Applications Master Data set, if you reverted data set changes.
  - Check in the change, "CT Apps- Applications: revert calculated metrics, upgrade component."
- **CT- Business Units** component:
  - Revert any calculated metric, or report customizations.
  - Upgrade the component.
  - Remap source files to the Business Unit Master Data set, if you reverted data set changes.
  - Check in the change, "CT- Business Units: revert calculated metrics, upgrade component."

## Related information

- ![](../../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
