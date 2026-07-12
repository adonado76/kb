---
source_system: "apptio-financial-planning"
practice: "tbm"
language: "en"
doc_type: "financial-planning"
title: "Dimension Considerations"
breadcrumb:
  - "Configuring Cloudability Financial Planning"
  - "Dimension Considerations"
source_path: "SSVWBC/cloud-financial-planning/admin/dimension-considerations.html"
images: []
capability_ids: []
last_updated: "2026-07-10"
summary: ""
---
# Dimension Considerations

While selecting dimensions for your plan, it is essential to consider the level of detail to be included in your forecast. The number of dimensions you choose will directly impact the number of forecast line items within the plan. Each unique combination of dimension values corresponds to a line item. So the more dimensions you include, the more granular and detailed your forecast gets.

While having a very granular forecast can be beneficial for an in-depth analysis, it might not be practical if your goal is to support an annual budgeting process with engagement by individual cost owners. In that case, you should carefully consider how many line items you want to present to cost owners for their review and update.

Cloud Financial Planning was designed to accommodate multiple use cases, ranging from individual users analyzing a generated forecast of their costs to finance owners performing what-if analysis on a segment of cloud spend, to the creation of a consolidated annual forecast shared with multiple cost owners responsible for editing their respective portions to support the annual budgeting cycle. The choice of plan dimensions may differ depending on your specific use case.

In general, all forecast line items will include a "who" dimension, representing cost ownership or accountability. Cloud Financial Planning refers to this as the cost ownership dimension, and it is a required element when creating a plan. While a simple forecast may have just one dimension, it must be the cost ownership dimension. Examples of cost ownership dimensions include business unit, account/ subscription, or product / app team. Additionally, there are "what" dimensions, which specify what is being forecast, often related to items you want to track and control, such as an application, workload, project, cloud vendor or service. You may have multiple "what" dimensions, such as workload and service, or cloud vendor and initiative/ project.

Plans can include up to 4 Cloudability dimensions. Cloudability dimensions are linked directly to actuals and used to summarize actual spending into forecast line items when creating the plan and for comparing actual spending to the plan. Additionally, you can include up to 20 Plan-only dimensions, which exist solely within the plan. These are used to capture additional details - drivers or explanations - about the changes and additions made to the forecast. However, they cannot be compared to actuals since they exist only within the plan.
