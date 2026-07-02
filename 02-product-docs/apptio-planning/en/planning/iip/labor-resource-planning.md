---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "planning"
title: "Labor Resource Planning"
breadcrumb: []
source_path: "planning/iip/labor-resource-planning.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Labor Resource Planning

For managing Labor resource lines under Expenses > Labor, see [Create a Labor Plan](../create-labor-plan.htm "(Opens in a new tab or window)").

Integrated Investment Planning feature adds Project Labor Role and Project Labor Rate as optional
attributes to the Expenses > Labor view. Values for these two dropdowns are shown based on Project
Labor Role reference data.

Project Labor Role is the project specific role which is used when allocating Labor line to a
project. Project Labor Rate is the hourly rate at which project is charged for specific labor
role.

For example, John’s designation in an organization is Senior Software Engineer but he is working
as Technical Lead on a development project. In this case John’s Project Labor Role is Technical Lead
and project will be charged using Technical Lead’s hourly rate.

To set labor rate and role to labor resource:

1. When entering the Labor line, select the Project Labor Role dropdown.
2. Select applicable Project Labor Role value.

   Worth to remember about Project Labor:

   - Setting Project Labor Role automatically sets Project Labor Rate value.
   - You can override the Project Labor Rate value set by the reference data.
   - For external or vendor resourced labor lines, set Vendor value and vendor specific Project Labor
     Role value which automatically sets the Project Labor Rate for the selected vendor.
   - If there are labor resources which are not billed to a project, you can skip setting values for
     Project Labor Role and Project Labor Rate attributes.
   - Financials are generated in the Summary tab based on Labor Allocation Rules configured in the
     reference data. Labor Summarization can now be done by Project and Project Labor Role as well.

   To learn more, see [Labor Summarization](../labor-summarization.htm "(Opens in a new tab or window)")

![](../../../resources/images/it%20planning_images/itp-pep-labor-roles.png)

1. Vendor Business Analyst, with the Project Labor Role: Contract PM, and Project Labor Rate: 85
   USD.
2. Internal Software Engineer, with the Project Labor Role: Dev, and Project Labor Rate: 120
   USD.
3. Internal Labor, non-billable to Project with no Project Labor Role and Project Labor Rate.
4. Internal resource to be hired, with the Project Labor Role: QA, and Project Labor Rate: 85
   USD.

Assigning Project Labor Role, Project Labor Rate, and Project attributes to the Labor line on the
Labor tab doesn’t allocate the resource to a project. The resource allocation needs to be done from
the Labor Activity tab.
