---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "FAQ: Automated Data Management"
breadcrumb:
  - "Planning"
  - "Troubleshooting and FAQs"
source_path: "it-planning/planning/adm/adm_faq.html"
images:
  - "resources/images/gear.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# FAQ: Automated Data Management

- [Where can I
  view and edit the Costing Standard connection settings?](adm_faq.html#FAQAutomatedDataManagement__WherecanIviewandedittheCostingStandardconnectionsettings)
- [Can I change the Costing Standard environment (development, production)
  when using Automated Data Management?](adm_faq.html#FAQAutomatedDataManagement__CanIchangetheCostingStandardenvironmentdevelopmentproductionwhenusingAutomatedDataManagement)
- [Can I
  connect to Costing Standard instance in another Apptio
  environment?](adm_faq.html#FAQAutomatedDataManagement__CanIconnecttoCostingStandardinstanceinanotherApptioenvironment)
- [Where can I view and edit the dataset mappings for reference
  data dimensions, actuals and plan data after Automated Data Management is enabled?](adm_faq.html#FAQAutomatedDataManagement__WherecanIviewandeditthedatasetmappingsforreferencedatadimensionsactualsandplandataafterAutomatedDataManagementisenabled)
- [What if I do not want to enable Automated Data Management for certain
  functions? For example, in the earlier Cost Transparency Integration implementation, I was able to
  enable only those reference data sharing or actuals sharing or publishing plan data as per my
  need.](adm_faq.html#FAQAutomatedDataManagement__WhatifIdonotwanttoenableAutomatedDataManagementforcertainfunctionsForexampleintheearlierCostTransparencyIntegrationimplementationIwasabletoenableonlythosereferencedatasharingoractualssharingorpublishingplandataaspermyneed)
- [How can I view the Automated Data Management status?](adm_faq.html#FAQAutomatedDataManagement__HowcanIviewtheAutomatedDataManagementstatus)
- [How can I delete the custom entity/dimension from Automated Data
  Management > Entity Mapping for the custom dimension that has already been deleted in Apptio Planning?](adm_faq.html#FAQAutomatedDataManagement__HowcanIdeletethecustomentitydimensionfromAutomatedDataManagementEntityMappingforthecustomdimensionthathasalreadybeendeletedinApptioPlanning)
- [I have added a new custom dimension in Apptio Planning. I want to import data into
  this custom dimension from Costing Standard. What should I do?](adm_faq.html#FAQAutomatedDataManagement__IhaveaddedanewcustomdimensioninApptioPlanningIwanttoimportdataintothiscustomdimensionfromCostingStandardWhatshouldIdo)
- [Since most of the configuration settings have been moved to
  Automated Data Management UI what happens to the Cost Transparency
  Integration panel in the old version of Planning?](adm_faq.html#FAQAutomatedDataManagement__Since)

## Where can I view and edit the Costing Standard connection settings?

After enabling Automated Data Management, you can check if the connection settings are
appropriate by navigating to Automated Data Management > Connections.
For enabling Automated Data Management Integration, see Enable
Automated Data Management Integration in ApptioOne Plan. Any changes to connection details
should be made at the **Automated Data Management > Connections** page. See [Connections](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(Opens in a new tab or window)") for more information.

## Can I change the Costing Standard environment (development, production) when using Automated Data Management?

Automated Data Management also known as Automated Data Management only supports development
environments in TBM Studio. Any changes will be imported from or published only to the development
environment.

## Can I connect to Costing Standard instance in another Apptio environment?

At present, Automated Data Management does not support connecting Costing
Standard instance in a different Apptio environment. You can configure connection
settings only to the Costing Standard instance that is using the
same environment as that of the Planning instance. For configuring
the connection settings, see [Connections](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=administration-connections "(Opens in a new tab or window)").

## Where can I view and edit the dataset mappings for reference data dimensions, actuals and plan data after Automated Data Management is enabled?

Any changes to the dataset mappings can be done at the Automated Data
Management **> Entity Mapping** page. See [Entity Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-entity-planning "(Opens in a new tab or window)") for more information.

## What if I do not want to enable Automated Data Management for certain functions? For example, in the earlier Cost Transparency Integration implementation, I was able to enable only those reference data sharing or actuals sharing or publishing plan data as per my need.

If you do not want to use Automated Data Management for certain functions, ensure that these
specific functions are not mapped on the Automated Data Management > Entity
Mapping page. See [Entity Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-entity-planning "(Opens in a new tab or window)") for more information.

## How can I view the Automated Data Management status?

Automated Data Management status can be viewed from the Status page in
**Automated Data Management**. For more details, see [Status](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=management-status "(Opens in a new tab or window)").

However, if you want to get a detailed error log to troubleshoot data sharing issues, follow the
steps below:

1. On the Apptio Planning menu, select Settings
   (![image](../../../../../../03-media/apptio-planning/resources/images/gear.png)) then
   select Cost Transparency Integration.
2. Select the Status tab.

   This page shows the details of Automated Data Management jobs
   and further information on each, if any.

| Field | Description |
| --- | --- |
| Start & End | The start and end times for the corresponding job |
| Initiated By | The email ID of the user that initiated the job |
| Status | The progress of the job: QUEUE, SUCCESS, SUCCESS WITH WARNINGS, or FAIL |
| Actions | Follow-up actions that must be performed:  • Publish data once Import jobs are successful (for example, publish reference data after import).  • View, to find and download error logs for failed jobs. |

## How can I delete the custom entity/dimension from Automated Data Management > Entity Mapping for the custom dimension that has already been deleted in Apptio Planning?

The beta release does not support the ability to delete custom entities/dimensions from
Automated Data Management > Entity Mapping. However, you can remove the dataset name in the
Entity Mapping page to disable data updates. If you want to delete the entity itself from the
page, we recommend logging a support ticket so that we can perform the action in the back-end. This
feature would be made available with the general release, and end users will have the ability to
delete unwanted custom entities from Entity Mapping.

## I have added a new custom dimension in Apptio Planning. I want to import data into this custom dimension from Costing Standard. What should I do?

We are working on a solution to automatically add the newly created custom dimension in
Automated Data Management > Entity Mapping. However, in this beta release we recommend you
follow the steps below to enable the newly created custom dimension for the automatic data
update.

1. Create a new custom dimension in Planning.
2. Create a dataset in TBM Studio that you want to use for importing in to the newly created custom
   dimension.
3. From the Planning page, navigate to Company Profile > Settings, disable **Automated Data
   Management** and save the changes.
4. Now, using the same steps above, re-enable Automated Data Management and
   save changes. Disabling and re-enabling Automated Data Management
   will automatically sync the newly added custom dimension in Entity
   Mapping. See [Access Automated Data Management](https://www.ibm.com/docs/en/apptio-platform/adm/saas?topic=started-access-automated-data-management "(Opens in a new tab or window)") for more information on
   enabling the feature.

## Since most of the configuration settings have been moved to Automated Data Management UI what happens to the Cost Transparency Integration panel in the old version of Planning?

In the beta release after Automated Data Management is enabled, Costing
Standard Integration panel will still be available, however, only to view status of various
data sharing jobs and to import actuals data from Costing Standard to Planning.

Before this capability is made generally available, the plan is to make actuals import completely
automated, similar to reference data import. Once this change happens the
Import tab will be removed from the Costing Standard
Integration panel. The panel will only be used for Automated Data Management status reporting post
this change.
