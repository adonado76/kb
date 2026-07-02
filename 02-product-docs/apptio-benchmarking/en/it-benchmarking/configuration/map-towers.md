---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Map the towers"
breadcrumb: []
source_path: "it-benchmarking/configuration/map-towers.html"
images:
  - "resources/images/it_benchmarking_images/map-towers-map.jpg"
  - "resources/images/it_benchmarking_images/map-towers.jpg"
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Map the towers

Standard towers have been defined for the benchmark data provided by the Costing Standard
Benchmarking Infrastructure application. To light up the Benchmarking reports, you must map your
towers to the application towers.

The standard towers are:

Application

Communication

Compute

Delivery

End User

IT Mgmt (Management)

Network

Output

Security & Compliance

Storage

When you created the Costing Standard project, you defined the towers in your IT infrastructure.
If you accepted the default tower definitions, will match the standard towers defined in the
benchmark data. Where possible, you need to match the towers in the benchmark data to the towers in
your IT infrastructure. Complete tower mapping gives the most complete benchmarking data in the
reports. You map the towers using the instructions in the application, as shown below.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-towers.jpg)

In the
Towers
tab shown,
Remaining
is a tower that has been mapped to Delivery, IT Mgmt, and Security & Compliance. These are not mapped out-of-the-box, but are recommended rules.

**Prerequisites**

Before you can map the sub-towers and cost pools, you must have:

Imported the AIB benchmarking .

Installed the CTF-Benchmarking component ( [https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration](https://www.ibm.com/docs/en/apptio-commercial/costing-standard/saas?topic=costing-standard-foundation-module-configuration "(Opens in a new tab or window)") ).

Appended the AIB benchmarking data to the Benchmarking master data .

**To map the towers**

Select the
Reporting
tab.

1. On the Home page, select
   Benchmarking
   .
2. In the Benchmarking navigation toolbar, select the Map icon highlighted below.

![img](../../../../../03-media/apptio-benchmarking/resources/images/it_benchmarking_images/map-towers-map.jpg)

1. Select the
   Towers
   tab.
2. Follow the instructions on the
   Mapping
   page.

You can map a benchmark tower to one or more customer towers, but you cannot map multiple
benchmark towers to the same customer tower

1. If you mapped a benchmark tower to many customer towers, you must modify the Benchmark model.

**To modify the Benchmark model**

Navigate to the Benchmark model.

1. Select the allocation line between the
   Cost Source
   and
   IT Resource Tower
   objects.
2. On the
   Selected Allocation
   tab, select the
   Automatically create many to many relationship
   option.
