---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "AWS Services Mapping"
breadcrumb: []
source_path: "cost-transparency/configuration/awsservices.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# AWS Services Mapping

Apptio's CBM and AWS DataLink connectors allow you to map billing line items from your
cloud provider billing line items to ATUM attributes, including IT Towers and Subtowers, the TBM
Services hierarchy, as well as a normalized unit of measure.

Applies to: Cloud for Costing Standard and Cloud Business Management on TBM Studio 12.5.x

## Overview

These mappings allow you to do the following:

- Analyze various cloud services across multiple providers using a common classification of cloud
  services
- View cost, consumption, and unit costs for all public cloud services in a like manner across
  multiple providers
- Automatically allocate cloud costs into the appropriate IT Resource Towers

## Mapping updates

Because cloud providers consistently and rapidly update their service offerings, the mappings
created and maintained by Apptio can become out-of-date. To address this dynamic environment, Apptio
updates the mapping files monthly. The action you need to take depends on whether you use the
Multicloud Connector:

- Multicloud Connector. To automate the ingestion of cloud billing, ATUM mapping is performed in the Apptio cloud billing pre-processor. The mapping files live in a central location and mapping occurs before the bill makes it into the customer CBM environment. If ATUM mapping gaps occur, no action on your part is necessary. Instead, Apptio identifies the gaps, fills them, then updates the mapping file to ensure that those gaps are eliminated from your environment.
- AWS Connector. If you use the legacy AWS Connector, ATUM mappings continue to take place in CBM via the Cloud Service Provider Lookup dataset, into which you need to append the AWS Service Mapping file. The mapping file can either be updated automatically via the AWS legacy connector or by manually overwriting the dataset with mapping file.

To update the mapping file:

1. Right-click on the file attachment below, then click Save Link (or Target) As.
2. Navigate to the place where you want to save the file, then click Save.
3. Unzip and open the .cvs file in a suitable application, such as Microsoft Excel.
4. Select the file for the ATUM version you want.
5. Log in to Apptio TBM Studio.
6. In the Project Explorer, navigate to **Tables > AWS Service Mapping**
7. Check out the AWS Service Mapping file and overwrite it with the updated
   .csv file.

The mapping file is updated frequently. Refer to this article for the most current content
release.

## Mapping gaps

If you are an AWS user and you encounter mapping gaps, please email a list of those gaps to
Apptio at [cloudmapping@apptio.com](mailto:cloudmapping@apptio.com "(Opens in a new tab or window)"). We will do our best to fill the gaps identified in the next mapping
update release. For your email, please export and attache the ATUM Mapping Quality report (in the
Maintenance report collection), and include the following information for every Cloud Service
Provider line item with a blank Subtower field:

- Provider
- Product
- Item
- Procedure
- Cost (optional, but helpful to understand impact of the gaps)

## Automated mapping for ATUM 2.1 and 3.0

As of April 2019, CBM was updated to support the automated mapping of cloud provider services to
ATUM classifications. CBM can map public cloud provider services to ATUM 1.0, 2.0, 2.1, and 3.0,
depending on your organization’s requirements.

## Change history

| Date | ATUM v1.0 | ATUM v2.0 | Update |
| --- | --- | --- | --- |
| 11/30/2020 | v1.35 | v2.25 | Includes new entries for ATUM v1 and v2 and customer report gaps as of end of Nov 2020 |
| 10/12/2020 | v1.33 | v2.23 | Includes new entries for ATUM v1 and v2 and customer report gaps as of end of Sep 2020 |
| 09/01/2020 | v1.32 | v2.22 | Includes new entries for ATUM v1 and v2 and customer report gaps as of Aug 2020 |
| 05/22/2020 | v1.31 | v2.21 | Includes new entries for ATUM 1.0 and 2.0 and customer-reported gaps |
| 04/23/2020 | v1.30 | v2.20 | Includes new entries for ATUM 1.0 and 2.0 and customer-reported gaps |
| 01/23/2020 | v1.29 | v2.19 | Includes new entries for ATUM 1.0 and 2.0 and customer-reported gaps |
| 11/15/2019 | v1.28 | v2.18 | Includes new entries for ATUM 1.0 and 2.0 and customer-reported gaps |
| 09/06/2019 | v1.27 | v2.17 | Includes new entries for ATUM 1.0 and 2.0 and customer-reported gaps |
| 06/03/2019 | v1.26 | v2.14 | Includes new entries for ATUM 1.0 and 2.0 and customer-reported gaps |
| 04/24/2019 | v1.25 | v.2.13 | Includes new entries for ATUM v1 and v2 and customer-reported gaps |
| 04/9/2019 | v1.24 | v.2.12 | Includes new entries for ATUM v1 and v2 |
| 2/15/2019 | v1.23 | v.2.11 | Includes new entries for ATUM v1 and v2 |
| 12/4/2018 | v1.22 | v2.10 | Includes new entries for ATUM v1 and v2 |
| 10/23/2018 | v1.21 | v2.9 | Includes new entries for ATUM v1 and v2 |
| 8/28/2018 | v1.20 | v2.8 | Includes additional spot instance entries and RI entries for R4 and R5 instance families |
| 08/16/2018 | v1.19 | v2.07 | Includes new entries for ATUM v1 & v2 |
| 07/12/2018 | v1.18 | v2.06 | Includes new entries for ATUM v1 & v2 |
| 04/18/2018 | v1.17 | v2.05 | Includes new entries for ATUM v1 & v2 |
| 03/16/2018 | v1.16 | v2.04 | Includes new entries for ATUM v1 & v2 |
| 01/11/2018 | v1.15 | v2.03 | Includes new entries for ATUM v1 & v2 |
| 12/13/2017 | v1.14 | v2.02 | Includes new entries for ATUM v1 & v2 |
| 10/27/2017 | v1.13 | v2.01 | Includes new entries for ATUM v1 & v2  Update missing mappings for ATUM v1 |
| 09/08/2017 | v1.12 | v2.0 | Updated ATUM v1 mapping gaps |
| 07/27/2017 | v1.11 | v2.0 | Includes large amount of new entries based on known gaps and AWS Pricing API  ATUM v2 mapping included as additional file v2.0 |
| 05/15/2017 | v1.10 |  | Includes new entries based on AWS Pricing API content |
| 03/13/2017 | v1.9.1 |  | Includes new entries based on AWS Pricing API content |
| 01/19/2017 | v1.9 |  | Includes large amount of new entries based on AWS Pricing API content |
|  | v1.8 |  | Includes new entries for known gaps |
|  | v1.7 |  | Includes large amount of new entries based on AWS Pricing API content |
| 10/06/2016 | v1.6 |  | Various sub-tower gaps | New AWS Pricing API content | Cleansed Subtowers and Units of Measure  *Note on v1.6 - a new column, ProductCode, was added. This new piece of data will not affect lookups and was added to support the mapping update process* |
|  | v1.5.1 |  | Includes large amount of new entries based on AWS Pricing API content |
|  | v1.5 |  | Includes some new CloudSearch entries + a default support entry (where UsageType and Operation are blank in the bill) |
|  | v1.4 |  | Includes a large number of new entries for new products and regions |

You can download the mapping file from the Apptio Community:

[https://community.apptio.com/viewdocument/aws-services-mapping](https://community.apptio.com/viewdocument/aws-services-mapping "(Opens in a new tab or window)")

## Related information

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
