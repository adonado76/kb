---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Labor Mapping"
breadcrumb:
  - "Costing Standard"
  - "Report Walkthrough"
  - "Cost Take-out Collection"
source_path: "cost-transparency/workbench/cs-labor-mapping.html"
images:
  - "resources/images/ct_images/lm-1.jpg"
  - "resources/images/ct_images/lm-2.jpg"
  - "resources/images/ct_images/lm-3.jpg"
  - "resources/images/ct_images/s-1.jpg"
  - "resources/images/ct_images/s-3.jpg"
  - "resources/images/ct_images/s-5.png"
  - "resources/images/ct_images/s-6.jpg"
  - "resources/images/ct_images/s-7.jpg"
  - "resources/images/ct_images/s-8.jpg"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Labor Mapping

Labor Workbench provides the ability for finance, cost center owners, and resource managers to enter and maintain labor related information to enrich and improve the data quality of information from HR and other systems and to map labor to the IT Resource Towers the people support including applications, products, and/or services.

****Labor Workbench - Configuration****

1. (TBM Studio): Install CTF-Labor Workbench component.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-1.jpg)
2. (TBM Studio): Load customer Labor dataset. Make necessary transformations if applicable.
3. (TBM Studio): Map the customer dataset to Labor Feed.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-3.jpg)
4. (TBM Studio): Save and Check in the changes.

   **Labor Workbench**
5. (Report View): Navigate to Workbench > Labor Mapping report > Labor Data Enrichment Tab.
   Verify that labor data is shown and update columns including Role Type, Employee Type, Vendor ID and
   Location as required.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-5.png)
6. (Report View): Navigate to Workbench > Labor Mapping report > Labor Mapping tab and map
   each labor row to one or more IT Resource Towers, IT Resource Sub-Towers and Application ID as
   required. Additionally, you may also, verify the column Weighting Factor as required. Save any
   changes and publish to downstream Labor Mapping ET Transform file.

   **Recommendations**:

   “Weighting Factor can be used to capture the true
   cost of the labor in the scenarios where they have been part of one or more IT Resource Towers/ IT
   Resource Sub-Towers.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-6.jpg)

   Note:
   - IT Resource Towers and IT Resource Sub-Towers drop downs are dependent upon IT Resource Towers
     Master Data.
   - Application ID drop down is dependent upon Applications Master Data.
7. (Report View): Navigate to Workbench > Labor Mapping report > Missing Mappings tab and
   verify if any labor rows are missing assignments to IT Resource Towers and IT Resource Sub-Towers.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-7.jpg)
8. (TBM Studio): Open Labor model object and verify the cost allocations from Labor to Time
   Tracking and Other Labor Allocations.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/s-8.jpg)

## Reports

**Labor Data Enrichment**

Provides ability to improve the metadata for the Internal and External Labor resources, ingested
from IDP’s workforce data, and enable richer analysis of your Workforce spend:

- Team (Example: Squads)
- Role
- Employee Type
- Vendor ID (if applicable)
- Location

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lm-1.jpg)

**Labor Mappings**

Users can update their Labor roster by mapping a Labor resource to:

- Solution Type and Solution Category
- Addressable
- Offering ID
- Project ID
- Allocation Weighting
  - Provides the ability to determine which Solution Type/Solution Category/Project the resource
    works on. The default weighting is 1 (100%) for each employee; however, users can adjust or split
    the resources percentages into their appropriate areas.

  ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lm-3.jpg)

**Missing Mappings**

Identifies labor resources that have not been mapped to Solutions.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/lm-2.jpg)
