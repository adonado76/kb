---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "View Considerations"
breadcrumb:
  - "Configuring Cloudability Financial Planning"
  - "View Considerations"
source_path: "SSVWBC/cloud-financial-planning/admin/view-considerations.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# View Considerations

*Plans in Cloud Financial Planning are closely associated with Views. The filter condition within a view determines the data used during the creation of a plan and when comparing actuals to the plan.*

It is important to understand that plans differ from reports because they capture a static snapshot of summarized data at a specific point in time.

When you create a plan, Cloud Financial Planning generates an initial forecast by summarizing actuals based on the specified dimensions and saves the results within the plan for further editing. Any modifications to the forecast entail changes to these forecast line items. Unlike reports, where changing views triggers a re-query and re-summarization of actuals using new filter conditions, changing the view for a plan essentially invalidates all the previously saved amounts and edits.

For this reason, plans are intrinsically linked to the view they were created in, similar to the current Cloudability budgets. This underscores the importance of creating a plan within a view that encompasses all the spending you intend to forecast and plan for. Cloud Financial Planning offers an alternative approach to segment and filter costs within a plan by utilizing the its cost ownership dimension, thus obviating the need to depend solely on views for this purpose.
