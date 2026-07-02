---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "End User Devices Configuration"
breadcrumb:
  - "Costing Essentials"
  - "Additional Solutions"
  - "End User Devices"
source_path: "apptio-cost-management/getting_started/ce-eud.html"
images:
  - "resources/images/acm_images/17-1.jpg"
  - "resources/images/acm_images/17-2.jpg"
  - "resources/images/acm_images/8-a.jpg"
  - "resources/images/acm_images/8-b.jpg"
  - "resources/images/acm_images/8-c.jpg"
  - "resources/images/acm_images/apdx-1.jpg"
  - "resources/images/acm_images/apdx-2.jpg"
  - "resources/images/acm_images/apdx-3.jpg"
  - "resources/images/acm_images/eud-mc.jpg"
  - "resources/images/acm_images/s-10.jpg"
  - "resources/images/acm_images/s-11.jpg"
  - "resources/images/acm_images/s-12.jpg"
  - "resources/images/acm_images/s-13.jpg"
  - "resources/images/acm_images/s-14.jpg"
  - "resources/images/acm_images/s-15.jpg"
  - "resources/images/acm_images/s-16.jpg"
  - "resources/images/acm_images/s-3.jpg"
  - "resources/images/acm_images/s-4.jpg"
  - "resources/images/acm_images/s-5.jpg"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# End User Devices Configuration

Complete these steps to start using End User Devices

**Install the End User Devices component**

(TBM Studio): Create a Project.

1. (TBM Studio): End User Devices support Multi-currency. Click
    [here](#multi-cu "(Opens in a new tab or window)")  for the configuration
   details.
2. (TBM Studio): Configure Time Settings and check-in the changes.
3. (TBM Studio): Install  **Cost- End User Devices**  component
   in the project.

![component](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-4.jpg)

What’s in the component?

![eud](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-3.jpg)

1. (TBM Studio): Create three input tables to ensure that relevant
   details are uploaded.

Active Directory

End User Devices

Labor Data

Sample for Reference - Name of the tables can be customer specific.

![](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-5.jpg)

1. (TBM Studio): Save and check-in the changes.
2. (TBM Studio): Refer to the  [Appendix](#appendix "(Opens in a new tab or window)")  section for a review of transformation formulas used in
   the reference project.
3. (TBM Studio): Map the following tables to the corresponding
   Master and Feed tables:

EUD Active Directory Master (Active directory table)

![appendix](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/8-a.jpg)

EUD Labor Master (Labor data)

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/8-b.jpg)

EUD Feed (End User Devices)

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/8-c.jpg)

1. (TBM Studio): Save and check-in the changes.

If there are any changes, please upload the input table on an
adhoc/monthly basis to ensure the accuracy of the reports.

Use the 'MM/dd/yyyy' date format for all data uploads and transformations to avoid formula
changes in the Master tables.

**EUD Workbench**

1. (Report View): Navigate to Workbench > EUD Workbench > Exemptions

Use this table to edit, add and remove users for exemption of device
from reports and dashboards.

Click on Save and then press Publish to propagate to all reports and
models, “EUD Exemptions ET Transform”

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-10.jpg)

1. (Report View): Navigate to Workbench > EUD Workbench > Device Estimate Refresh Cost

Use this table to edit, add and remove the details of the Estimated
Device Refresh Cost for device models in your inventory ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-11.jpg)

Click on Save and then press Publish to propagate to all reports and
models, ‘Device Estimate Refresh Cost ET Transform’.

1. (Report View): Navigate to Workbench > EUD Workbench > Device Models with Missing
   Refresh Cost Info

Verify the list of Device Models from your Inventory, which are missing
Est Device Annual Refresh Cost.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-12.jpg)

1. (Report View): Navigate to Workbench > EUD Workbench > Device EOL EOW Term

Use this table to edit, add and remove the End of Life and End of
Warranty terms in years for device models in your inventory.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-13.jpg)

Click on Save and then press Publish to propagate to all reports and
models, ‘Device EOL and EOW Term ET Transform’.

1. (Report View): Navigate to Workbench > EUD Workbench > Device Models with Missing
   EOL and EOW Term

This provides the list of Device Models from your Inventory, which are
missing End of Life and End of Warranty Term information and add the information in tab
‘Device EOL EOW Term’.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-14.jpg)

1. (Report View): Navigate to Workbench > EUD Workbench > In Stock Definition

Use this table edit, add and remove the different end-user device
statuses that are to be considered as "In Stock". The list of statuses available in this table
is transformed to "In Stock" in all End User Insight reports

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-15.jpg)

Click on Save and then press Publish to propagate to all reports and
models, ‘EUD In Stock Status Definition ET Transform’.

1. (Report View): Navigate to Workbench > EUD Workbench > Latest OS Version

Use this table to edit, add and remove Operating Systems and
corresponding latest version details, to flag non-compliant OS devices.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/s-16.jpg)

Click on Save and then press Publish to propagate to all reports and
models, ‘EUD OS Version ET Transform’.

1. (TBM Studio): Open End User Devices Model and verify the cost
   allocations

**Acquired Cost**

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/17-1.jpg)

**Est Refresh Cost**

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/17-2.jpg)

Both the screenshots are for reference purpose and the cost allocations
may vary as per the data

**Appendix**

Formulas applied to transform the reference input data to meet the requirements of the EUD
Master and EUD Feed.

The formulas listed below are intended solely for reference data.
Customers may update these formulas to align with their specific data and industry standards.

Appended snapshot of the formulas applied to the

**ACME Active Directory Input**

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/apdx-1.jpg)

**ACME End User Devices Input**

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/apdx-2.jpg)

**ACME Labor Data Input**

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/apdx-3.jpg)

**Multi-Currency**

If customer uses Multi-currency this would be a good time to set that up. Multi-currency is
the same in Costing Essentials as in CT projects. You can reference
the  [Multi-currency
configuration](../../multi-currency/home.html)  in Help Center.

However – if your customer uses a non-Gregorian calendar, the newer version of MCC doesn’t
support non-gregorian. If your customer requires a non-Gregorian Calendar, follow the Legacy
Multi-currency configuration  [here](../../studio/admin/configure-multi-currency.html)  .

Select the preferred  **Base Currency**  .

![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/eud-mc.jpg)
