---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Azure Services Mapping"
breadcrumb: []
source_path: "configuration/azuremap.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Azure Services Mapping

Apptio's CBM and AWS DataLink connectors allow you to map billing line items from your
cloud provider billing line items to ATUM attributes, including IT Towers and Subtowers, the TBM
Services hierarchy, as well as a normalized unit of measure.

Applies to: Cloud for Costing Standard on TBM Studio 12.5.x

## Overview

These mappings allow you to do the following:

- Analyze various cloud services across multiple providers using a common classification of cloud services
- View cost, consumption, and unit costs for all public cloud services in a like manner across multiple providers
- Automatically allocate cloud costs into the appropriate IT Resource Towers

You can download the mapping files from the Apptio Community:

[https://community.apptio.com/viewdocument/azure-services-mapping](https://community.apptio.com/viewdocument/azure-services-mapping "(Opens in a new tab or window)")

## Mapping updates

Because cloud providers consistently and rapidly update their service offerings, the mappings
created and maintained by Apptio can become out-of-date. To address this dynamic environment, Apptio
updates the mapping files monthly. The action you need to take depends on whether you use the
Multicloud Connector.

The updated mapping files are attached to this article and tracked in the Change History table,
below.

- Multicloud Connector. To automate the ingestion of cloud billing, ATUM mapping is performed in the Apptio cloud billing pre-processor. The mapping files live in a central location and mapping occurs before the bill makes it into the customer CBM environment. If ATUM mapping gaps occur, no action on your part is necessary. Instead, Apptio identifies the gaps, fills them, then updates the mapping file to ensure that those gaps are eliminated from your environment.
- Azure Connector. If you use the legacy Azure Connector, ATUM mappings continue to take place in CBM via the Cloud Service Provider Lookup dataset, into which you need to append the Microsoft Azure Service Mapping file. The mapping file must be updated manually by overwriting the dataset with mapping file.

To update the mapping file:

1. Right-click on the file attachment below, then click Save Link (or Target) As.
2. Navigate to the place where you want to save the file, then click Save.
3. Unzip and open the .cvs file in a suitable application, such as Microsoft Excel.
4. Select the file for the ATUM version you want.
5. Log in to Apptio TBM Studio.
6. In the Project Explorer, navigate to Tables > Microsoft Azure Service Mapping.
7. Check out the Microsoft Azure Service Mapping file and overwrite it with the updated .csv file.

The mapping file is updated frequently. Refer to this article for the most current content
release.

## Automated mapping for ATUM 2.1 and 3.0

As of April 2019, CBM was updated to support the automated mapping of cloud provider services to
ATUM classifications. CBM can map public cloud provider services to ATUM 1.0, 2.0, 2.1, and 3.0,
depending on your organization’s requirements.

## Change history

The Microsoft Azure Mapping Services files have been updated on the following dates. Apptio
recommends that you click **Action > Follow** so you can be notified when newly updated mapping
files are available.

| Date added | Version | Description |
| --- | --- | --- |
| Nov. 30, 2020 | 2.19 | New entries for ATUM 2.0 and customer-reported gaps. |
| Oct. 12, 2020 | 2.17 | New entries for ATUM 2.0 and customer-reported gaps as of end of Sep 2020 |
| Sep. 1, 2020 | 2.16 | New entries for ATUM 2.0 and customer-reported gaps as of Aug 2020. |
| May 22, 2020 | 2.15 | New entries for ATUM 2.0 and customer-reported gaps. |
| Apr. 23, 2020 | 2.14 | New entries for ATUM 2.0 and customer-reported gaps. |
| Jan 30, 2020 | 2.13 | New entries for ATUM 2.0 and customer-reported gaps. |
| Nov. 15, 2019 | 2.12 | New Azure entries to address customer-reported gaps. |
| June 3, 2019 | 2.11 | New entries for ATUM 1.0 and 2.0 and customer-reported gaps. |
| Mar. 7, 2019 | 2.10 | New entries based on the March Azure Pricing API Content with ATUM 2.0 and customer-reported gaps. |
| Jan. 15, 2019 | 2.9.2 | Corrected column formatting and added missing data. |
| Jan. 10, 2019 | 2.9.1 | Correction to the December file. |
| Dec. 26, 2018 | 2.9 | Includes new entries based on December Azure Pricing API Content with ATUM 2.0 and customer report gaps. |
| Oct 24, 2018 | 2.8.1 | Added new column, Subtower 2.0, as a direct copy of SubTower 2.0 to address case issues in CCM lookup functions. |
| Oct 23, 2018 | 2.8 | Incorporated large number of service naming changes introduced by Azurein mid October, 2018 |
| Sept 20, 2018 | 2.7 | Includes new entries based on Aug Azure Pricing API Content with ATUM 2.0. |
| May 7, 2018 | 2.6 | Includes new entries based on April Azure Pricing API Content with ATUM 2.0 and customer report gaps. |
| Mar 2, 2018 | 2.5 | Includes new entries based on February Azure Pricing API Content with ATUM 2.0. |
| Jan 19, 2018 | 2.4 | Includes new entries based on January Azure Pricing API Content with ATUM 2.0. |
| Jan 9, 2018 | 2.3 | Includes new entries based on December Azure Pricing API Content with ATUM 2.0 and updates with renamed Azure meter mappings. |
| Sept 8, 2017 | 2.2 | Includes all services of new entries based on September Azure Pricing API content with ATUM 2.0. |
| July 27, 2017 | 2.1 | Includes all services of new entries based on July Azure Pricing API content with ATUM 2.0. |
| May 24, 2017 | 2.0 | Added new ATUM 2.0 fields (Tower 2.0, Subtower 2.0, Service Type, Service Category, Service Name); Includes all services in May 2017 published service catalog. |
| Jan 24, 2017 | 1.5.1 | Updated typo from Azure service catalog where Windows Azure Storage was mislabeled Windows Azure Service Bus for Resource GUID5E7A80E5-0273-44B8-A179-E4F62EA6EC9F. |
| Jan 19, 2017 | 1.5 | Includes all services in Jan 2017 published service catalog. |
| Dec 4, 2016 | 1.4 | Includes all services in Nov 2016 published service catalog | large number of Units normalization improvements. |
| May 23, 2016 | 1.3 | Includes all services in Apr 2016 published service catalog. |
| Feb 2, 2016 | 1.2 | Initial publish. |

You can download the mapping files from the Apptio Community:

[https://community.apptio.com/viewdocument/azure-services-mapping](https://community.apptio.com/viewdocument/azure-services-mapping "(Opens in a new tab or window)")

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
