---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Reporting - AHQ Configuration and Common Error Messages"
breadcrumb: []
source_path: "cost-transparency/reports-v103/reportingahqconfig.html"
images:
  - "resources/images/ct_images/reportingahqconfig_1.png"
  - "resources/images/ct_images/reportingahqconfig_2.png"
  - "resources/images/ct_images/reportingahqconfig_3.png"
  - "resources/images/ct_images/reportingahqconfig_4.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Reporting - AHQ Configuration and Common Error Messages

## Reporting Tab (AHQ)

**Application**

The Ah-hoc query configuration appears when inserting a table, chart, waterfall, etc. The setup
from using the AHQ will determine what the reports/reporting looks like within the reporting
surface.

**AHQ Objects**

The following image shows what object the report will be based off of. The current object(s)
chosen are “Applications” and “Projects.” This will populate all perspectives within the AHQ based
upon the values of the backing object(s). Apptio only supports reporting off of two objects and
filtering off of a third object.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_1.png)

**NOTE**: When the AHQ is locked to an object the option will be grayed out and locked to
backing object. This doesn’t necessarily mean it is the data from that object.

**Common Error #1**

The error below will appear when you have slicer/picker values that are doing a lookup across
three different objects.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_2.png)

**Common Error #2**

- This error will occur when a slicer/picker value has a calculated metric associated with the
reporting results.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_3.png)

- The calculated model type metric can be viewed on the **Metrics** tab. The following example
uses the **Fixed** metric.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/reportingahqconfig_4.png)
