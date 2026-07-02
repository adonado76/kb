---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Install the ITPF Integration components"
breadcrumb: []
source_path: "configuration/installitpfintegration.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Install the ITPF Integration components

Three components are available as part of the Costing Standard Foundation module to
connect Costing Standard (CT) with IT Planning Foundation (ITPF).

## Introduction

Use the ITPF Integration components to do the following:

- Ensure that the reference data across CT and ITP has one source of truth in TBM Studio and makes
  the data available to ITP.
- Make the actuals data in the Costing Standard application available to the ITP application.
- Make the budget and forecast data in the ITP application available to the CT application.

Note:

The exchange of data is initiated from the ITP application.

For the integration to work, you must configure both CT and ITPF.

Components

- Apptio ITPF Integration — This component passes budget, forecast, and actuals data between CT and ITPF. The Cost Source component must be installed before you install the Apptio ITPF Vendor Integration component. Three data sets are installed:
  - ITPF Actuals is a transform of the Cost Source Master Data that enables the transfer of actuals from CT to ITPF.
  - ITPF Budget and ITPF Forecast are the destinations for the fiscal year budget and the latest forecast data transferred from ITPF to CT. These data sets are mapped to the Cost Source Master Data in CT.
- Apptio ITPF Asset Integration — This component passes asset plan data from ITPF to CT. The component installs the ITPF Asset Budget and ITPF Asset Forecast data sets. The following components must be installed before you install the Apptio ITPF Integration component:
  - Cost Source
  - Fixed Assets
- Apptio ITPF Vendor Integration — This component passes data related to vendor contract plans from ITPF to CT. The component installs the ITPF Contract Budget and ITPF Contract Forecast data sets. The Cost Source component must be installed before you install the Apptio ITPF Vendor Integration component.

## Install the components

To install the components:

1. Open the TBM Studio.
2. In the Project tab, click Components.
3. Click the Apptio ITPF Integration component.
4. Click Install.
5. Click the Apptio ITPF Asset Integration component.
6. Click Install.
7. Click the Apptio ITPF Vendor Integration component.
8. Click Install.

If you want to use the Vendors and Assets components in ITP, you must install the ITPF Vendor
Integration and ITPF Asset Integration components to ensure that the following data sets are
installed:

- ITP Vendor Master Data
- ITPF Contract Type Master
- ITPF Contract Budget
- ITPF Contract Forecast
- ITP Asset Class Master

## Master data

For a description of the master data table fields and reports installed with each component, see
the description listed in each component. To display the descriptions, do the following:

1. In the Project tab, click Components.
2. Click a component to open it to the description page.

## Configure the ITPF application

To configure ITPF, open the ITPF application, click the Settings icon (![](../../resources/images/ct_images/gear_icon.png)), then click **Cost Transparency
Integration**. For information about completing the required fields, see [Integrate with Costing Standard](../../it-planning/planning/integrate-ct.html "If your organization runs both Apptio Costing Standard and an Apptio planning application, you can integrate them to share data.").

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
