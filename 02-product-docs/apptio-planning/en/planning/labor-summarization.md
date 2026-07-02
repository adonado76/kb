---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Labor Summarization"
breadcrumb: []
source_path: "planning/labor-summarization.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Summarization

Admin users can specify how they want their labor financial line items to be summarized
on the Summary tab. In other words, an admin user can specify which columns of data from the Labor
tab will show up on the Summary tab.

We provide three scenarios below on how this works. Each example contains settings in the
following views:

- Company Profile – Labor Summarization
- Expenses - Labor tab
- Expenses – Summary tab

## Scenario 1: Labor Summarization enabled – a single Summary Option chosen

Aside from the default Summary Options, we have checked My Example Column. On the Expenses -
Labor tab, this has been populated. Then you’ll see that the value in My Example Column shows
up.

You’ll also notice that the items that were not checked do not show up on the Expenses – Summary
tab, such as Vendor, Location, Description, and Comment.

![](../../resources/images/it%20planning_images/scenario%201%20labor%20summarization%20my%20example%20column%20checked.png)

## Scenario 2: Labor Summarization enabled – more Summary Options chosen

More Summary Options have been checked. These values (My Example Column, Vendor, and Description)
now appear on the Expenses – Summary tab.

Unchecked items such as Location and Comment do not show up on the Expenses – Summary tab.

![](../../resources/images/it%20planning_images/scenario%202%20labor%20summarization%20my%20example%20column%20and%20a%20couple%20other%20columns%20checked.png)

## Scenario 3: Labor Summarization disabled – most granular option

If you want all values to show up, you can check all of the boxes. However, the recommended
method is to disable Labor Summarization altogether. By disabling summarization, values from the
Expenses – Labor tab will flow through to the Expenses – Summary tab.

Note: Disabling the Labor Summarization checkbox may improve performance when viewing line-item
tables.

![](../../resources/images/it%20planning_images/scenario%203%20labor%20summarization%20disabled.png)
