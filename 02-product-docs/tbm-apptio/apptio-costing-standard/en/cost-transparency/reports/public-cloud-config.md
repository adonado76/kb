---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Public Cloud TCO Configuration"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Public Cloud Collection"
source_path: "cost-transparency/reports/public-cloud-config.html"
images:
  - "resources/images/ct_images/bd-1.jpg"
  - "resources/images/ct_images/bd-2.jpg"
  - "resources/images/ct_images/bd-3.jpg"
  - "resources/images/ct_images/cloud-eco.jpg"
  - "resources/images/ct_images/map-table.jpg"
  - "resources/images/ct_images/pc-arch.jpg"
  - "resources/images/ct_images/pc-conf-s2.jpg"
  - "resources/images/ct_images/pc-conf-s2a.jpg"
  - "resources/images/ct_images/pc-ref-ss.jpg"
  - "resources/images/ct_images/pc-usecase.jpg"
  - "resources/images/ct_images/report-pcoverview.jpg"
  - "resources/images/ct_images/s-5.png"
  - "resources/images/ct_images/s3-accname.jpg"
  - "resources/images/ct_images/s3-buref.jpg"
  - "resources/images/ct_images/s4-c3.jpg"
  - "resources/images/ct_images/s4-cclist.jpg"
  - "resources/images/ct_images/s4-rh.jpg"
  - "resources/images/ct_images/s5-cc.jpg"
  - "resources/images/ct_images/samp-pc.jpg"
  - "resources/images/ct_images/tip-pc.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Public Cloud TCO Configuration

## Overview

The IBM Apptio Public Cloud TCO Reports offer Finance team members, typical users of the IBM
Apptio product, valuable insights into their monthly cloud spend. These reports provide a financial
perspective on which public cloud services are impacting costs, identifying primary cost drivers and
their effects. It also helps the Finance teams to understand trends, performance, and the necessity
of FinOps practices for optimal cloud operation for the following two major cloud service providers:

**Amazon Web Services (AWS)**

**Microsoft Azure**

The following specific problems can be solved by this solution.

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pc-usecase.jpg)

## Configuration Steps

1. (TBM Studio): Create a Project.
2. (TBM Studio):

   **Template\_V120**  : Install “Public Cloud TCO” component
   in the project.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pc-conf-s2.jpg)

   **Template\_V200**  : Install “Cost- Public Cloud
   TCO” & “Cost- Public Cloud TCO Reporting” component in the project.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pc-conf-s2a.jpg)

   **Architecture**

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pc-arch.jpg)

   Note: Data for “cldy\_monthly\_aws” & “cldy\_monthly\_azure” can be fetched from Cloudability CDI
   Datalink Connector. Data for Reserved Hours can be fetched from Cloudabitlity RI reports through
   REST Services Datalink Connector.

   *Reference Snapshot for Cloudability RI reports*

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/pc-ref-ss.jpg)
3. (TBM Studio):

   **Template v120 & Template v200**  : Create 5 input
   tables (refer to the Sample screenshot) to ensure relevant details are uploaded and map these
   datasets to the input data tables given below

   **Account Name Mapping**:
   This refers to the list of account names retrieved from the cldy\_monthly\_aws and cldy\_monthly\_azure
   datasets.

   New Name: This maps or groups the AccountName values to the corresponding chart of
   accounts.

   If an account cannot be mapped to a New Name, the model is designed to default to
   the existing AccountName. ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s3-accname.jpg)

   **Business Unit Reference**

   It is used to normalize various region names into standardized ones.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s3-buref.jpg)

   **Cloud
   Tower Mapping**

   It is used to map different Usage Families to their respective
   Cloud Tower Names.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s4-c3.jpg)

   **Cost Center Listing**

   It is used to map the Cost Center and
   Category to the master table; if not mapped, they will be marked as "Unassigned." ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s4-cclist.jpg)

   **Reserved Hours**

   It is used in the calculation of different metrics for Reserved Instances outlined below.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s4-rh.jpg)

   Sample for Reference:

   Name of the tables can be customer specific

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/samp-pc.jpg)

   Reference Mapping Sample: In the above example the mapping is done as followed:
   - Account Mapping -> Account Name Mapping
   - BU Reference Input -> Business Unit Reference
   - Cloud Tower Mapping Input -> Cloud Tower Mapping
   - CC Input -> Cost Center Listing
   - RI input -> Reserved Hours
4. (TBM Studio): Save and Check in the changes.

   \*\*  **Additional Step for Template v120
   (TBM Studio)**  : Map below tables to ‘IT Finance Cloud Master Data’.

   ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/map-table.jpg)

   Tip: Define the
   Data source Column = Name of the input CSP

   Ex: Map Data Source= ‘cldy\_monthly\_aws’ while
   mapping cldy\_monthly\_aws to IT Finance Cloud Master Data ![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/tip-pc.jpg)

   Note: In Template\_v200,
   these tables are already mapped to the ‘IT Finance Master Data’.
5. (TBM Studio):

**Template v120 & Template v200**  : Open ‘IT Finance Cloud’ and verify the cost
allocations.

**Cost**

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-5.png)

\*\*This screenshot is for reference purpose and the cost allocations may vary as per the data

**Cloud Credits**

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s5-cc.jpg)

\*\*This screenshot is for reference purpose and the cost allocations may vary as per the data

## Reporting Structure

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/report-pcoverview.jpg)

| Key Element Description |
| --- |
| 1. Financial and Operational Summary of Cloud for Cost YTD including any Credits applicable |
| 2. Additional metadata makes it self-intuitive, aligns taxonomy and makes it easy to comprehend. |
| 3. The cost trending across different Cloud Services (AWS & Microsoft Azure). |
| 4. The cost trends by business attributes such as Provider, Cost Centre, Account Name, etc. |

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/cloud-eco.jpg)

| Description |
| --- |
| 1. The Report enhances about the services driving the cost direction. |
| 2. The effectiveness of the Cloud Purchase model and how it compares to Best-in-Class benchmarks. |
| 3. The trend of the unit rate in relation to changes in consumption. |
| 4. Detailed breakdown of Costs, consumption and unit rates across Service Providers |

## Drilldown Reports

Drill down further to understand the Business & Technical drivers for each of the reports.

- The factors driving the service cost, including which account is responsible and the
  corresponding amount.
- The business service/application that drove the change.

**Cloud Cost - Details**

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/bd-1.jpg)

**CPU Hours - Details**

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/bd-2.jpg)

**Storage - Details**

![image](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/bd-3.jpg)
