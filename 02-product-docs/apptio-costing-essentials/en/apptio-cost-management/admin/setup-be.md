---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "Cost Pool Benchmarking Configuration"
breadcrumb:
  - "Costing Essentials"
  - "Configuration"
source_path: "apptio-cost-management/admin/setup-be.html"
images:
  - "resources/images/acm_images/bm-1.jpg"
  - "resources/images/acm_images/bm-10.jpg"
  - "resources/images/acm_images/bm-2.jpg"
  - "resources/images/acm_images/bm-3.jpg"
  - "resources/images/acm_images/bm-4.jpg"
  - "resources/images/acm_images/bm-5.jpg"
  - "resources/images/acm_images/bm-6.jpg"
  - "resources/images/acm_images/bm-6a.jpg"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Cost Pool Benchmarking Configuration

Pre-Requisite

The COE or any individual with equivalent access needs to login to a general ITBMX (Interactive
Benchmarking) product and update the customer company profile (Revenue, OpEx spend etc.).

1. Login to ITBMX

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-1.jpg)
2. Click on the cogwheel (settings) icon on the top right section of the screen and select
   ‘Configuration’.

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-2.jpg)
3. In the ‘Organization Profile’ section, enter the ‘Organization Revenue’, ‘Organization OpEx’ and
   ‘Number of Employees’ sec1on with the desired numbers.

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-3.jpg)

   Note: Ensure that the numbers entered in the 3 sections are validate with the ‘Green tick’ mark
   before proceeding.
4. Click on the ‘Benchmarks’ dropdown in the top left of the screen.

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-4.jpg)
5. Scroll down to the bottom of the screen and click on ‘Download Benchmarks as CSV’ button.

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-5.jpg)
6. Click on the ‘Download’ button in the ‘Download Benchmarks message box and verify that the
   ‘.csv’ file has been downloaded.

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-6a.jpg)

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-6.jpg)
7. Navigate back to the desired customer instance and navigate to TBM Studio.

   Data Upload and Configuration
8. In TBM Studio, load the downloaded ‘.csv’ file to the project. Make the necessary
   transformations if applicable.
9. Map the uploaded dataset to Benchmarking Feed.

   ![image](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/bm-10.jpg)
