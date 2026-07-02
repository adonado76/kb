---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Identify shared services"
breadcrumb: []
source_path: "configuration/idsharedservices.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Identify shared services

A portion of your cloud costs might be attributable to public cloud infrastructure
services shared across the departments that build applications on the public cloud. A good example
is Enterprise Support, whose costs could be a large lump sum amount that needs to be allocated to
the cloud services that are directly consumed by teams and departments in your organization. The
costs of these shared infrastructure services can be allocated to those services that are directly
consumed, ensuring that the costs to the application departments account for all the costs incurred
from using public cloud providers.

Applies to: Apptio Costing Standard or Apptio Cloud Cost Management running on TBM Studio v12.3.3
or later.

Note:

Shared service costs will be spread across all directly consumed cloud services and weighted by
the cost of those directly consumed services.

## Overview

To allocate those shared infrastructure costs, you must identify the costs in your provider bill
that are shared. Apptio is flexible in terms of the billing columns you use to identify the sets of
billing line items that represent shared services. For example, for Enterprise Support, you could
identify shared services through values in the product column or some other account that creates
deployment and delivery tooling that is shared by the groups that build applications on the public
cloud. In the latter case, you would identify shared services through values in the account
column.

## Identifying shared services

Identifying shared services is largely based upon the Tablematch function, which allows you to
look up values in a separately created lookup table using values in your cloud provider bill. CBM
comes with pre-existing Tablematch files for AWS and Azure. CBM uses Tablematch to determine whether
a billing line item is considered a shared service based on the columns and values that you provide
in the Tablematch files. For more information, see the function definition in[TableMatch function](../../studio/formulas-and-functions/functions/tablematch.htm "(Opens in a new tab or window)").

## Allocate AWS costs in the Shared Services Tablematch

To identify and allocate shared service costs for AWS:

1. In the TBM Studio Project Explorer, expand the Tables section.
2. Click AWS Cost AllocationShared Services Tablematch.
3. Click Check Out.
4. In the Source area, click Enter Manually.

   ![](../../resources/images/ct_images/7877_1.png)
5. Click Blank Table.
6. In the Editable Table step, identify the shared service, then set IsSelfService to Yes. You can use the existing columns, or you can add and remove columns as necessary. For example, to identify Enterprise Support as a shared service and allocate the costs to all directly consumed services, do one of the following methods:
   - In Product Code, enter "AWS Support Business" (or the term you see for support in your AWS Cost Allocation bill), then set IsSharedService to Yes.
   - If a specific linked account is responsible for building shared infrastructure tooling, right-click that account and add a new column called "LinkedAccountId" to the table, then add a new row, and enter the ID of that linked account to the new row where the IsSelfService column value is set to Yes.
7. Save your changes.
8. Check in your changes.

## Allocate Azure costs in the Shared Services Tablematch

To identify and allocate shared service costs for Azure:

1. In the TBM Studio Project Explorer, expand the Tables section.
2. Click AzureShared Services Tablematch.
3. Click Check Out.
4. In the Source area, click Enter Manually.
5. Click Blank Table.
6. In the Editable Table step, identify the shared service, then set IsSelfService to Yes. You can use the existing columns, or you can add and remove columns as necessary. For example, to identify a specific line item for a specific account owner as shared service and allocate those costs directly to consumed services, enter that account owner’s ID in the AccountOwnerId field and set IsSharedService to Yes.
7. Save your changes.
8. Check in your changes.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
