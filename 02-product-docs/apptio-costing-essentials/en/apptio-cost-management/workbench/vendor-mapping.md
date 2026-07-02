---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "Vendor Mapping"
breadcrumb:
  - "Costing Essentials"
  - "Workbench"
source_path: "apptio-cost-management/workbench/vendor-mapping.html"
images:
  - "resources/images/acm_images/vendor-missing-mapping.png"
  - "resources/images/studio_images/ce-vm-1_969x598.png"
  - "resources/images/studio_images/vm-2_950x589.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Vendor Mapping

## Vendor Data Enrichment

This tab provides ability to improve Vendor metadata, ingested from IDP’s Vendor master list, and
enable richer analysis of your Vendor spend.

- Vendor Type
- Vendor Primary Service
- Vendor Category
- Is CSP (Is this a Cloud Service Provider)
- Vendor Manager and Owner
- Annual Target Spend
  - Represents Vendor Budget for current FY not the total Target spend across the forecasted
    lifetime of the Vendor (e.g. 3 year Contract)

One of the Key mappings in the Labor Data Enrichment is the “Is CSP” Column. This will determine
which vendor will be defined as a Cloud Vendor and will allocate to the Cloud Master Data instead of
the Solutions based on the Vendor Mappings Workbench. By allocating cost to the Cloud Master Data,
the cost will allocate to the Solutions based on a Cloud Specific Mapping to Solutions weighted by
the Resources Invoice Amount.

## Cloud Master Datamapping

Unlike other costs that are allocated to the Solutions layer, cloud costs will be based on the
Accounts and/or Application Services associated with a Solution.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/ce-vm-1_969x598.png)

## Vendor Mappings

Provides ability to map Vendor spend directly to Solution Types and Solution Categories together
with an allocation weighting:

- Solution Type
- Solution Category
- Solution Offering
- Delivery (On Prem vs Public Cloud) \*\*
- Offering ID
- Project ID \*\*
- Allocation Weighting
  - Provides the ability to determine the % allocation of Vendor spend to each Solution. The default
    weighting is 1 (100%) for each vendor; however, users can adjust or split the vendor percentages
    into their appropriate areas.

|  |  |  |
| --- | --- | --- |
|  | • | Solution Type |

|  |  |  |
| --- | --- | --- |
|  | • | Solution Category |

|  |  |  |
| --- | --- | --- |
|  | • | Solution Offering |

|  |  |  |
| --- | --- | --- |
|  | • | Delivery (On Prem vs Public Cloud) \*\* |

|  |  |  |
| --- | --- | --- |
|  | • | Offering ID |

|  |  |  |
| --- | --- | --- |
|  | • | Project ID \*\* |

|  |  |  |
| --- | --- | --- |
|  | • | Allocation Weighting |

|  |  |  |
| --- | --- | --- |
|  | • | Provides the ability to determine the % allocation of Vendor spend to each Solution. The default weighting is 1 (100%) for each vendor; however, users can adjust or split the vendor percentages into their appropriate areas. |

\*\* Delivery and Project Id are optional attributes that can be leveraged to increase the
granularity of the allocations. For example, enable Projects for the same Vendors to allocate to
different Service offerings.

![](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/vm-2_950x589.png)

## Missing Mappings

Identifies Vendors that have not been mapped to a Solution Type/Category and Offering(s).

![Vendor Missing Mapping](../../../../../03-media/apptio-costing-essentials/resources/images/acm_images/vendor-missing-mapping.png)
