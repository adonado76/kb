---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "user-guide"
title: "Cloud Compute Attributes mapping"
breadcrumb: []
source_path: "user-guide/cloudcomputeattributesmapping-9568.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cloud Compute Attributes mapping

Note: Applies to: Cloud Cost Management on TBM Studio 12.5 and later

Use the Cloud Compute Attributes file (attached below) to map your Compute attributes, such as
Memory, Storage, and CPU cores, to the corresponding columns in the Cloud Service Provider Master
Data table. The values between the Memory, Storage, and CPU cores are determined by the instance
type listed in your bill. These attributes are used in normalizing server sizes and appear in the
Compute Comparisons report in CBM.

![](../../resources/images/ct_images/cloudcomputeattributesmapping_1.png)

The Cloud Compute Attributes file must be manually loaded into the Cloud Compute Attributes table
beginning with TBM Studio 12.5.

**To download the Cloud Compute Attributes file**:

1. Right-click the file attachment below and click Save Link (or Target) As.
2. Choose where you want to save the file, and then click Save.

Note: To get the latest updates to this file, refer to this article every content
release.

| Date | Update |
| --- | --- |
| 1/03/2022 | Comprehensive update of all new Instance Types through 3 Jan 2022 for AWS, Azure and Google Cloud. |
| 3/01/2019 | Added Instance Family column.  Added newer instance types including:   - AWS: a1, c5n, m5a, p3dn, r5, r5d, t3, u, z1d - Azure: S (SAP Hana on Azure Large Instances) |
| 7/07/2018 | Initial Version |

[Download the mapping file](https://community.apptio.com/viewdocument/updated-hbm-cloud-pricing-data-for-1 "(Opens in a new tab or window)")

**Parent topic:** [Costing Standard](../home.html)
