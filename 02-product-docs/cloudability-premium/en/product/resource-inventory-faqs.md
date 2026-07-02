---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Resource Inventory FAQs"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Resource Inventory"
source_path: "product/resource-inventory-faqs.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Resource Inventory FAQs

## Why can't I select the most recent 3 days in the Resource Inventory Date Range picker?

In Resource Inventory, we do not allow to select recent 3 days in the date range because some
measures may take up to 72 hours to reflect in the inventory report and the data completeness is not
guaranteed.

You will see a message in the date picker showing the available date range, with a reminder that
the most recent 3 days are excluded.

## Why do the numbers in my saved report change over time?

There could be couple of reasons by numbers look different:

- If you ran a saved report where the date has crossed 90 days look back, it’ll automatically
  reset the date to 7 days. This is to ensure that report loads successfully. In this case, you’ll
  also see a flash warning message.
- If your report had ‘Rolling Date’ turned on and criteria was last 90 days, then numbers can
  change everyday.

## Why some resources show the state as 'Not Available'

Resource Inventory may display the state as **“Not Available”** in the following
scenarios:

- Missing Permissions – If advanced credentialing is not configured, Resource Inventory will get
  the resource details from cost data which will not have all metadata, including the resource
  state.
- Short lived Resources – Resource Inventory collects data at defined intervals. If a resource is
  created and terminated between two collection cycles, its state and utilization details may not be
  captured and hence state will be absent.
- Snapshots – State information is not available for snapshot resources.
- Data transfer resources – Certain resources (for example, NAT Gateway data transfer) do not have
  an associated state, and will appear as “Not Available”.
- Azure terminated resources – In Azure, once a resource is terminated, even if its not a short
  lived resource, its state information is no longer available and is shown as “Not Available".

**Parent topic:** [Resource Inventory](../product/resource-inventory.html)
