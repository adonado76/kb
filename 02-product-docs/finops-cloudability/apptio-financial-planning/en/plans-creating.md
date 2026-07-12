---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Creating Plans"
breadcrumb:
  - "Working with Plans"
  - "Creating Plans"
source_path: "SSVWBC/cloud-financial-planning/creating-and-using-plans/create-plan.html"
images:
  - "03-media/apptio-financial-planning/cfp-creating-plans.png"
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Creating Plans

*At its core, a plan is essentially a forecast. The plan is initially populated with a forecast generated using the parameters and dimensions specified. You can then fine-tune and expand upon this forecast, effectively transforming it into a comprehensive plan that more accurately reflects the impact of a well-planned business activity and investment.*

From the navigation pane, select Plan > New Plan .

In the New Plan dialog, enter the following information:

1. Plan name - Within a View, a plan name must be unique.
1. Fiscal year and Plan Duration - Plans can start either in the current fiscal year or next, and can be 1 to 3 years in duration.
1. Cost Ownership - This is a dimension used to segment forecast and budget line items by cost ownership. For example, there will be separate budget line items for every unique value of the cost ownership dimension. Budgets only use the cost ownership dimension. Note: Budgets only use the cost ownership dimension
1. Forecast Options - Forecast Options consist of 3 drop-down boxes. a. Cost Metric - Can be any available cost metric, including custom metrics (must be cost-based only). b. Excluded Spend - You can choose from: none, credits only, 1-time charges only, or both. c. Forecast Model - This is how far back the forecast algorithm should look when evaluating past spending.
1. Dimensions - Dimensions are used to provide additional forecast granularity and detail. Where the cost ownership dimension defines the "who" in every forecast line item, dimensions define the "what". Typically dimension choices are Workload , Application , Product , Service , etc. Can be either Cloudability or Plan-only
1. Dimensions Picker - You can select from the list of Recommended or All Available Cloudability dimensions.
