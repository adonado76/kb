---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "apptio-cost-management"
title: "Financial Mapping"
breadcrumb:
  - "Costing Essentials"
  - "Workbench"
source_path: "apptio-cost-management/workbench/financial-mapping.html"
images:
  - "resources/images/studio_images/ce-fm-1_931x555.png"
  - "resources/images/studio_images/ce-fm-2_955x585.png"
  - "resources/images/studio_images/ce-fm-3_938x585.png"
  - "resources/images/studio_images/ce-fm-4.png"
  - "resources/images/studio_images/ce-fm-5_998x592.png"
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Financial Mapping

## Chart of Accounts

Users can map their Chart of Accounts to following dimensions, to aid in expense categorization
and reporting analysis:

- Cost Pool
- Cost Sub Pool
- Addressable
- Expense Type

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/ce-fm-1_931x555.png)

## General Ledger

Users can map General Ledger Transactions to the following dimensions to improve accuracy of
allocation and reporting insights:

- Vendor ID
- Project ID
- Offering ID
- Organization ID

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/ce-fm-2_955x585.png)

## Other Mappings

The Other Mappings table provides the ability to map expenses within designated Cost Centers
directly to Solution Types and Solution Categories together with an allocation weighting.

- Solution Type and Solution Category
- Weighting
- Maybe 100% allocation (insert ‘1’), or split across multiple Solution Types/Categories
- All expenses with the source Cost centers will be allocated to the target Solution
  Types/Categories, based on the define weighting(s)
- The cost received by each Service Type/Category, will in turn be even spread to their
  *child* service offerings

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/ce-fm-3_938x585.png)

## Accounts Payable

Provides ability to map Transactions in the Accounts Payable (AP) sub ledger (ie. Invoices) to:

- Vendor ID
- Project ID
- PO Number

This mapping enables the relationship of Vendor Purchase Orders to Accounts Payable invoices.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/ce-fm-4.png)

## Purchase Orders

This table provides the user the ability to map Purchase Orders to:

- Cost Centers
- Vendor ID
- Project ID
- Contract Number

This mapping enables the relationship of Vendor Contracts to their associated PO’s.

![image](../../../../../03-media/apptio-costing-essentials/resources/images/studio_images/ce-fm-5_998x592.png)
