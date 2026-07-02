---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Prerequisites"
breadcrumb: []
source_path: "planning/adm/adm_prerequisites.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Prerequisites

The following are the prerequisites for enabling Automated Data Management in an Costing
& PlanningPlan.

## Install Cost Transparency Integration Components for Reference Data and Actuals Sharing

This step is required only if you have not configured Costing Standard Integration. Follow this
procedure only if this is the first time you are configuring integration with Costing Standard.

1. In Costing Standard, install the Apptio ITPF Integration component. See [Install the ITPF Integration components](../../../cost-transparency/configuration/installitpfintegration.htm#Install) for more information.

   This step automatically
   installs all the templates of reference data sets needed to integrate the products.
2. If you use Assets and Vendor, you will need to install the Apptio ITPF Asset and Apptio ITPF
   Vendor components as well. For more information, see [Install the components](../../../cost-transparency/configuration/installitpfintegration.htm#Install2).

## Install Costing Standard Integration Components for Plan Automated Data Management

1. In Costing Standard, install the ApptioOne Plan Integration component.

   This step automatically
   installs all the templates of Plan data sets needed to import the plan data from Costing to
   Planning.

## Configure Connection to Costing Standard Instance in Automated Data Management

To configure Automated Data Management manually, navigate to [Connections](../../../data-sharing/data_sharing_connections.htm "(Opens in a new tab or window)").

To configure Automated Data Management connection settings automatically, ensure that **Enable
Automated Data Management Integration** option is selected in [Edit the Company Profile](../edit-company-profile.htm "(Opens in a new tab or window)")
page.

![](../../../resources/images/it%20planning_images/adm-auto-connection.png)
