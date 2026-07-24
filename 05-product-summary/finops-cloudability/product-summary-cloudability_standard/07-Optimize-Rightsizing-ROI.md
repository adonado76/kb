---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "07-Optimize-Rightsizing-ROI"
source_files_count: 1
last_updated: "2026-07-13"
---

# 07-Optimize-Rightsizing-ROI

## Rightsizing ROI

<!-- sub-header -->
- **breadcrumb:** Optimize > Rightsizing ROI
- **source_path:** SSVCLNQ/product/jira-for-rightsizing.html
- **original_file:** optimize-rightsizing-roi.md
- **images:**
  - 03-media/apptio-cloudability-standard/rightsizing_roi_1.png
  - 03-media/apptio-cloudability-standard/rightsizing_roi_2.png
  - 03-media/apptio-cloudability-standard/rightsizing_roi_3.png

Rightsizing ROI lets you track rightsizing recommendations from opportunity to completion and report on the impact of your rightsizing efforts. You can create tickets manually or via automated policies which allow you to track those recommendations, review open and closed opportunities, comment on those opportunities, and report on savings delivered as a result.

Rightsizing ROI lets you can configure policies to automatically create issues and requests while tracking recommendations. You can also use it to visualize actual savings from actioning these resource optimization recommendations.

Rightsizing ROI has three ticket options:

- A Jira Cloud integration using the Jira Service Management extension to create Jira issues and requests, and use bi-directional synchronization of Jira ticket status to keep your projects in sync.

- A ServiceNow integration using a Cloudability generated script for ServiceNow incidents and requests, also using bi-directional synchronization of ServiceNow ticket status to keep your projects in sync.

- Stand-alone ticket tracking functionality contained within Cloudability itself.

### Before you Begin

If you want to use the ServiceNow or Jira cloud ticketing functionality, you’ll need to set up those integrations first. See the set-up guides below for more information

Jira integration

- Learn about Jira Integration - Setup

ServiceNow integration

- Learn about ServiceNow Integration - Setup

Using Rightsizing ROI: Creating Tickets

Tickets can be created in Rightsizing ROI one of two ways.

Manual Ticket Creation – When Viewing any recommendation from the Rightsizing recommendation pages, you can create a ticket directly via the UI by clicking on the more options button on the right side of the recommendation.

From there, you can select the ticket system you want to leverage and a rightsizing ROI ticket is created and linked to the system of your choice with the relevant details.

Ticket Creation via Automated Policy – Automated policies provide a scalable way to create tickets against opportunities surfaced by Cloudability Rightsizing engine. Policies can be run at set intervals and create tickets for the opportunities up to the selected number of results so your teams are only focusing on the largest opportunities.

### How to Configure a policy

1. Navigate to Settings > Rightsizing Policies .

1. Select the Add a Policy button. The Create a Policy drawer opens.

1. Enter your policy criteria:

- Name : Enter a name for your policy.

- 30 Day Savings Threshold : Enter the minimum cost savings your require across 30 days.

- Cloud Service : Select the Cloud resource you want to include.

- Cost Basis : Choose the cost basis to use when calculating the threshold.

- Actions : Check the boxes to include rightsizing actions.

- Maximum Results : Enter the maximum results added from each scheduled run.

- View : Select the filter for your resources.

- Integration Type : Select the type of ROI integration for this policy.

- Project : For Jira, select the project where the created tickets are displayed.

- Task : For ServiceNow, select the task type where created tickets are displayed.

- Request Type: For Jira, select the issue type (Jira) or request type (Jira Service Management).

- Schedule : Select the recurrence.

- Days of the week: If the policy runs weekly, select the day you want it to run.

- End After : Choose the policy end date.

1. Select the Create button to create the policy, or select the Create and Run button to create a policy and run it.

To enable the automatic creation of tickets, you must create and configure a policy.

### Rightsizing ROI: Understanding and Triaging your issues and tickets

The issues, requests, or incident tickets created by the policy are all visible in the Rightsizing Dashboard table view in Rightisizing ROI as well as directly in the configured JIRA project or ServiceNow queue .

Each ticket contains:

- An overview of the recommendation.

- A link to the details of the recommendation in Cloudability.

- Labels from the key resource attributes.

### View recommendations on the Rightsizing dashboard

In Cloudability, tickets created by the policy are displayed in the Rightsizing ROI dashboard. It displays the following aggregated key performance indicators (KPIs):

- Potential Savings: Potential saving opportunities from all unresolved tickets.

- Realized Savings : Realized savings for all resolved tickets, normalized to a 30 days savings rate.

- Realized Savings Chart : The chart shows a breakout of the actioned tickets and the associated realized savings by date on which it was actioned. Rightsizing ROI does not attempt to accumulate savings over time, but shows the 30 day savings rate for the actions on the dates so you can see the rate at which teams are implementing changes/resolutions.

Individual tickets

The Rightsizing dashboard also displays the details of each ticket created by your policy:

- Cloud Service : The Cloud provider and service.

- Resource Name : The name of the Cloud resource.

- Resource ID : A unique identifier for a specific AWS resource.

- Ticket : The ticket associated with this resource.

- Type : Either Jira, ServiceNow, or Cloudability.

- Status : The current status of the ticket.

- Assigned To: The ticket owner.

- Created : The date the ticket was created.

- Closed : The date the ticket was resolved or "N/A" if the ticket is still active.

- Resolution : The resolution status of the ticket.

- Potential Savings: Potential savings for the ticket identified by the recommendation.

- Realized Savings: Realized savings based on the new instance type.

- Details : The details of the recommendation.

Note : Review the Rightsizing recommendations for each service using the 30 day view. From here, look at the Cost Savings opportunities to get insights into establishing the threshold amount.

Note : Resource change detection is currently supported for Compute, Storage, and Database resource types.

### Deleting Rightsizing ROI tickets

To delete a ticket in Rightsizing ROI, click into the details pane of the ticket you want to delete. Select the more options button in the top right and select delete. Confirm your intent to delete the ticket. Deleting Rightsizing ROI tickets cannot be undone.

### Rightsizing ROI FAQ

Is there a way to see who assigned you a Rightsizing ticket?

No, if the ticket is allocated via the Cloudability interface.

How long will the realized savings appear in the rightsizing ROI? Does it disappear or stay there forever?

Realized savings data in the Rightsizing ROI feature doesn't get deleted; it remains in Cloudability forever. It is a historical record of the change that was made and the money that was saved.

How are realized savings calculated?

At the time the recommendation is first tracked, Cloudability stores information about the resource in its current state. When a change to the resource occurs, the amount of savings realized is calculated based on the 30-day costs from the original resource state minus the 30-day costs from the new resource state. Since future use is unknown, the realized savings value is calculated as (current-resource-type * rate * 24 hrs * 30 days) - (previous-resource-type * rate * 24 hrs * 30 days) as an estimation of usage. The value for realized savings reflects the change that was actually made and is not directly influenced by what may have been recommended.

What is the maximum number of polices that can be created?

Up to 30 policies. However, if you use a third-party integration (like Jira Cloud or Service Now), you may be able to circumvent this limit by using those services to triage the tickets and requests based on the resource information provided. For example, resource tags are included in the tickets created.

What is the maximum number of tickets that can be created per policy run?

Up to 100 tickets per run. However the limit is constrained by the number of open tickets. An "open" ticket is currently defined as any ticket that does not have a "realized savings" value.

Does Cloudability support views with filters based on Business Mapping in the ROI ?

No, Rightsizing does not support filtering by Business Mapping.

---
