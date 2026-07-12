---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Integrate with Cost Transparency"
breadcrumb: []
source_path: "planning/integrate-ct.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Integrate with Cost Transparency

If your organization runs both Apptio Costing Standard and an Apptio planning
application, you can integrate them to share data.

p

Integrating Costing Standard with an Apptio planning application allows you to accomplish the
following:

- Import reference data from Costing Standard to your Apptio planning application
- Import monthly actuals from Costing Standard to your Apptio planning application
- Publish budget plans and forecasts from your Apptio planning application to Costing
  Standard

For more information, see [Troubleshoot Planning data upload
errors](troubleshooting.html)

## Enable integration

Tasks in this section can only be performed by users assigned to the Admin role. See Frontdoor
permissions and roles.

An enhanced Cost Transparency Integration (CTI) panel, introduced in Planning release 2.78, is a
self-contained space where Admin users can perform all Cost Transparency Integration tasks within a
single control panel. The panel provides centralized management and one-click import and export with
Costing Standard. To learn more, see [Cost Transparency Integration
Panel](cti_panel.html "The updated Cost Transparency Integration (CTI) panel, introduced in Planning release 2.78, is a self-contained space where admin users can perform all Cost Transparency Integration tasks within a single control panel. The new panel provides centralized management and one-click import and export with Cost Transparency.").

In Costing Standard, install the Apptio ITPF Integration component. Doing so automatically
installs all the templates of the reference data sets needed to integrate the products. If you are
using Assets and Vendor, you will need to install the Apptio ITPF Asset and Apptio ITPF Vendor
components as well. To learn more, see [Install the ITPF
Integration components](../../cost-transparency/configuration/installitpfintegration.html "Three components are available as part of the Costing Standard Foundation module to connect Costing Standard (CT) with IT Planning Foundation (ITPF).") in Costing Standard help .

You can integrate Costing Standard using one of the following authentication methods:

Token authentication (R12+) (recommended)
:   This method determines the Costing Standard instance and project domain from the environment
    settings. The Enhanced Access Administration environment and the authentication token for the user
    are included in the request.

    Any user with ManagePlans, CTIConfig, and ReadOnlyApi permissions
    (permissions included in the default Admin role) can authenticate to publish plans and import data
    from Costing Standard.

    If you authenticate using Token authentication (R12+), you must also choose an
    Environment. This allows you to use the same Costing Standard instance or project for both
    the main and sandbox Planning instances when exporting plan data or importing actuals and/or
    reference data to and from Costing Standard. For example, you can import actuals and reference data
    information from the same Costing Standard instance or project into both the Planning sandbox and
    the main or production instances.
:   [Integrate using Token authentication (R12+)](#IntegratewithCostTransparency__Integrat)

Service Account authentication
:   Service Account authentication is no longer supported for Costing Standard v12.9.0 or later.

    This method determines the Costing Standard instance and project domain from the user-entered
    settings for that particular integration type. The service account credentials are passed as an HTTP
    "basic" authentication header.

    If your Costing Standard application runs on TBM Studio v.11, then you must use Service Account
    authentication.

    [Integrate using Service Account authentication](#IntegratewithCostTransparency__Integrat2)

## Integrate using Token authentication (R12+)

1. On the Apptio planning menu, select Settings then select Cost
   Transparency Integration.
2. From the Cost Transparency Integration panel, select Configure.
3. In General, enter the following:

   Authentication Method
   :   Select Token authentication (R12+).

   Environment
   :   Select the Environment from the drop-down menu.

   Instance
   :   Enter the Costing Standard Instance.

   Project Domain
   :   Enter the Costing Standard Project Domain.

   Import From
   :   Select one of the following:
       - Development
       - Production

         If you import from Production, you will have to wait for calculations to
         complete before data is displayed.

   Enabled Features
   :   Select any of the following:

       - Plan Integration: enable exporting budget plans and forecasts to Costing Standard. From
         the Export Format list, select from the following options:
         - Publish Months for all Fiscal Years as columns in a single row: publish monthly column
           headers using the date format period number fiscal year. For example, P1 FY2018.
         - Publish Months for all Fiscal Years as individual rows: includes a Date column for
           the month and fiscal year, and an Amount column with the appropriate amount for that period
           and fiscal year. This option also uses the format period number fiscal year.
       - Actuals: enable importing monthly actuals from Costing Standard
       - Reference Data: enable importing of default and custom dimensions, such as Cost Centers
         and a chart of accounts. If you choose to integrate reference data, ensure the names of the
         reference data sets in the Planning Costing Standard section match what was uploaded to Costing
         Standard.
4. Select Save.

## Integrate using Service Account authentication

1. On the Apptio planning menu, select Settings () then select
   Cost Transparency Integration.
2. From the Cost Transparency Integration panel, select Configure.
3. In General, enter the following:

   Authentication Method
   :   Select Service account.

   Username
   :   Enter the username you want to use to authenticate by HTTP.

   Password
   :   Enter the password you want to use to authenticate by HTTP.

   Enabled Features
   :   Select any of the following:
       - Plan Integration: enable exporting budget plans and forecasts to Costing Standard. From
         the Export Format list, select from the following options:
         - Publish Months for all Fiscal Years as columns in a single row: publish monthly column
           headers using the date format period number fiscal year. For example, P1 FY2018.
         - Publish Months for all Fiscal Years as individual rows: includes a Date column for
           the month and fiscal year, and an Amount column with the appropriate amount for that period
           and fiscal year. This option also uses the format period number fiscal year. For example, P1
           FY2018.
       - Actuals: enable importing monthly actuals from Costing Standard.
       - Reference Data: enable importing of default and custom dimensions, such as Cost Centers
         and a chart of accounts. If you choose to integrate reference data, ensure the names of the
         reference data sets in the Planning Costing Standard section match what was uploaded to Costing
         Standard
4. Select Save.

## Import actuals from Costing Standard

1. Select ![](../../resources/images/icons/icon-settings_20x20.png).
2. Select Cost Transparency Integration.
3. Select Import Actuals.
4. Choose Start Period and End Period of the data you want to import.
5. Select Import.

The import works in the background.

To see the progress of the import process, on the Import of Actuals has been queued window,
select Status.

- If the Import from Cost Transparency option is not available, or if the
  import fails, your Cost Transparency Integration may not be configured correctly. Contact your
  designated support contact or Admin.
- If your organization uses multiple currencies, you must use the same actuals currency rate table
  for both your Apptio planning application and Costing Standard. See [Support for multiple
  currencies](support-multiple-currencies.htm "(Opens in a new tab or window)").

## Publish plans to Costing Standard

Before publishing a data set to Costing Standard from your Apptio planning application, ensure
the data set exists in Costing Standard.

1. Select ![](../../resources/images/icons/icon-settings_20x20.png).
2. Select Cost Transparency Integration.
3. Select Publish.
4. From the dropdown, select the plan you want to publish.
5. Select the line item types you want to publish.
6. Select Publish.

The publish works in the background.

To see the progress of the publishing process, on the Your plan has been queued for publishing
window, select Status.

- If Project Financial Planning is enabled, the Publish Financials to Costing Standard
  action will be moved from the All Departments > Expenses > Summary page to the
  All Plan Sections > Ledger page. This will publish all direct, indirect, and charge
  financial line items to Costing Standard.
- If the Publish to Costing Standard option is not available, or if the
  publish fails, your Cost Transparency Integration may not be configured correctly. Contact your
  designated support contact or Admin.
- If your organization uses multiple currencies, Apptio planning applications can publish up to 72
  months of data in a single publish action (see [Support for multiple currencies)](support-multiple-currencies.htm "(Opens in a new tab or window)").

## Import reference data from Costing Standard

Tasks in this section can only be performed by users assigned to the Admin role. See Frontdoor
permissions and roles.

Reference data must be consistent in order for all reporting features to function properly. See
[Manage reference data](manage-reference-data.html "(Opens in a new tab or window)").
Your Apptio planning application and Costing Standard data formats are not initially an exact match.
Before continuing, consider the following data differences:

| Table | What to look for |
| --- | --- |
| Accounts | The Account reference data in Costing Standard does not include:   - Account Group - Account Subgroup - Fixed/Variable - Discretionary/Non-Discretionary   These dimensions appear in several reports in Planning. You must include these dimensions in addition to the standard Account information. |
| Department | Department reference data in Costing Standard does not include:   - Owner - Budget owner   These dimensions appear in several reports in Planning. You must include these dimensions in addition to the standard Department listing information. |

Follow these steps to import reference data from Costing Standard. When you import reference
data, the most recent reference data set is imported regardless of the active date setting in
Costing Standard.

1. Select ![](../../resources/images/icons/icon-settings_20x20.png)
2. Select Cost Transparency Integration.
3. Select Import Ref Data.
4. In Categories and Import Values, select datasets you want to import.
5. Select Import.

The import works in the background.

To see the progress of the import process, on the Import of Reference Data has been queued
window, select Status.
