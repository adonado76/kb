---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Configure Automated Data Management"
breadcrumb: []
source_path: "it-planning/planning/adm/adm_prerequisites.html"
images:
  - "resources/images/it_planning_images/adm-auto-connection.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Configure Automated Data Management

The following are the prerequisites for enabling Automated Data Management in an
Costing & Planning - Plan.

## Install Cost Transparency Integration Components for Reference Data and Actuals Sharing

This step is required only if you have not configured Costing Standard Integration. Follow this
procedure only if this is the first time you are configuring integration with Costing Standard.

1. In Costing Standard, install the Apptio ITPF Integration component. See
   [Install the ITPF Integration components](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=install-itpf-integration-components "(Opens in a new tab or window)") for more
   information.

   This step automatically installs all the templates of reference data sets
   needed to integrate the products.
2. If you use Assets and Vendor, you will need to install the Apptio ITPF Asset and Apptio ITPF
   Vendor components as well. For more information, see [Install the components](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=install-itpf-integration-components "(Opens in a new tab or window)").

## Install Costing Standard Integration Components for Plan Automated Data Management

1. In Costing Standard, install the ApptioOne Plan Integration
   component.

   This step automatically installs all the templates of Plan data sets needed to import
   the plan data from Costing to Costing & Planning -
   Plan.

## Configure Connection to Costing Standard Instance in Automated Data Management

To configure Automated Data Management manually, navigate to [Connections](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(Opens in a new tab or window)").

To configure Automated Data Management connection settings automatically, ensure that **Enable
Automated Data Management Integration** option is selected in [Edit the Company Profile](../edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.")
page.

![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/adm-auto-connection.jpg)

**Parent topic:** [Connect to Apptio Costing](../../../it-planning/planning/adm/adm_capabilities.html)
