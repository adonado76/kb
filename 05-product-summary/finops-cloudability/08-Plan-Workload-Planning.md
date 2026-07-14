---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "08-Plan-Workload-Planning"
source_files_count: 2
last_updated: "2026-07-13"
---

# 08-Plan-Workload-Planning

## Get Recommendations for Workload Planning

<!-- sub-header -->
- **breadcrumb:** Plan > Workload Planning > Get Recommendations for Workload Planning
- **source_path:** SSVCLNQ/product/get-recommendations-for-workload-planning.html
- **original_file:** planning-get-recommendations-workload.md
- **images:**
  - 03-media/apptio-cloudability-standard/drop-down.jpg
  - 03-media/apptio-cloudability-standard/3-dots.jpg
  - 03-media/apptio-cloudability-standard/modify-delete.jpg
  - 03-media/apptio-cloudability-standard/edit-icon.jpg

Workload Planning helps you optimize your workload architecture and improve your financial planning accuracy across cloud vendors.

You can:

1. Model your workloads.
1. Get a resource recommendation and cost estimate for a set of service types (virtual machine, managed database, object and block storage, load balancer) based on your requirements.
1. Get estimates for one cloud vendor or compare resources between cloud vendors to pick the optimal cloud destination.

### Use Cases for Workload Planning

1. Pre-Deployment Cost Estimation and Comparison Comparing Cloud Providers: Customers can model the cost of a planned workload across different cloud providers (AWS, Azure, GCP, OCI etc.) to determine the most cost-effective option for their specific requirements. This is crucial for multi-cloud strategies. Evaluating Region and Resource Types: Before launching, users can compare the cost implications of deploying a workload in various regions and using different resource types (e.g., different VM families, storage options) to find the optimal configuration. Scenario Planning for New Projects: Engineers and product managers can quickly estimate the cloud infrastructure costs for new applications, services, or features, allowing finance teams to understand the budget impact and make data-driven investment decisions.
1. Optimizing Existing Workloads (Rightsizing and Replatforming) Rightsizing Analysis: By inputting existing workload requirements, customers can see recommendations for more cost-efficient instances or services that meet performance needs without over-provisioning. This helps eliminate waste from idle or underutilized resources. Leasing Option Analysis (Reserved Instances, Savings Plans, Spot): Workload Planning helps customers understand the cost savings associated with different leasing models (On-Demand, Reserved Instances, Savings Plans, Spot Instances) and guides them in choosing the most appropriate option for predictable or interruptible workloads. Migration Planning: When planning to migrate an application from on-premises to the cloud, or between cloud providers, Workload Planning can simulate the costs in the new environment, ensuring a financially sound migration strategy.
1. Collaborative Budgeting and Forecasting Shared Understanding of Cloud Costs: The ability to save, share, and comment on workload plans fosters collaboration between engineering, FinOps, and finance teams, creating a shared understanding of upcoming cloud spend. Accurate Forecasts: By using Workload Planning to estimate future deployments, customers can build more accurate and defensible cloud forecasts, reducing variance between planned and actual spend. Accountability and Ownership: When teams are involved in the planning process and can see the cost implications of their architectural decisions, it promotes a greater sense of accountability for cloud spend.
1. Strategic Cloud Resource Procurement Informed Purchasing Decisions: Workload Planning provides the data needed to make intelligent decisions about purchasing commitments like Reserved Instances or Savings Plans, ensuring they align with actual workload needs and maximize discounts. Identifying Opportunities for Cost Reduction: By modeling various scenarios, customers can proactively identify opportunities to consolidate resources, leverage different pricing models, or make architectural changes to reduce overall cloud spend.
1. Compliance and Governance Standardizing Resource Provisioning: Workload Planning can help establish best practices for resource provisioning by providing a clear, cost-optimized path for new deployments, contributing to better cloud governance. Tracking and Reporting Planned vs. Actual Costs: While not a direct reporting feature, the plans created in Workload Planning serve as a baseline against which actual cloud spend can be measured, aiding in performance monitoring and identifying deviations.

### Before you begin

Update your Workload Planning preferences

Admins define the options that appear in Workload Planning. Visit Workload Planning Preferences for more information.

Understand custom pricing:

- For AWS, Azure, and OCI, all prices in Workload Planning are inclusive of custom pricing by default. No configuration is needed for these vendors.
- For GCP, you must enable the export of custom pricing data from your GCP billing account. Visit Setting up Custom Pricing Support for GCP for more information.

Set your default currency (non-US customers):

- Set up a default currency in Cloudability so prices display with the correct currency.
- Load an exchange rate table in Cloudability to display the correct conversion rate.

Review existing workloads

You can visualize all your workloads in the List tab. Select a workload to see the details.

- Select to modify the status of any workload.
- Select to see your other options. You can delete, duplicate, or export a workload, or save that workload as a template.

### Create a workload

1. Log in to Cloudability.
1. From the main menu, select Plan > Workload Planning .
1. Select the New Workload button or Builder tab.
1. Record the common information for your workload.
1. Add your resources. Note: You can only add 30 resources per plan.
1. Visualize your recommendations.
1. Review your recommendation summary.

### Record the common information for your workload

1. Enter a Name and Description for your workload.
1. Review the Allowed Service Providers . (If you don't see a service provider you're looking for, ask your admin to add it in Workload Planning Preferences.)
1. For any service provider for which you want recommendations, check the Include in Estimate checkbox.
1. From the Preferred Region dropdown menu, select the region where you want to deploy your workload. You can select up to five regions for each cloud vendor. You can also change the region later when you add resources.
1. Select your Preferred Lease Type . Your selection helps choose the correct lease type and price type when you reach the recommendation step. Note: The On-Demand price corresponds to the custom on-demand price, inclusive of custom pricing.
1. If appropriate, select your Commitment Type , Commitment Term , and Payment Option . Note: These fields only apply for committed price for AWS, Azure and GCP compute. They do not apply for OCI. If you later select On-Demand or Spot Price, these fields will no longer take effect.
1. Select the Next button to add resources.

By default, the Workload status is set to “In Progress” (You can change this status later in the List tab, after you create the workload).

### Add your resources

Provide your resource requirements for the workload. Workload Planning uses the data you enter to look for resources that have requirements equal to or more than the amount you requested.

You can either enter the resource details manually or import them.

To import your resources details:

1. To add multiple resources at once, select the Import button. Note: Importing resources overwrites existing resources.
1. From the dropdown menu, choose whether you want to import a JSON file or an Excel file.
1. The Import drawer opens. Use the links in the drawer to download a template with examples of resource requirements or a list of the existing resources. Note: In JSON files, the names of all services must be present in the file. If there is no resource or requirement need for a given service type, enter it with empty brackets. For example, for load balancer, the format is “loadbalancer”: [].
1. Select the Next button.
1. Drag your file into the upload area or use the browse for a file link to search for it.
1. Select the Next button.
1. Workload Planning displays a summary of your file. Select the Done button when you're ready to move on.

You can also add resources manually. To do that:

1. On the Add Resources workflow step, select the Add Resource button.
1. Select the Service Type and provide a Resource Name . Note: The “Managed Database” service type is not available for OCI.
1. If you selected Service Type Virtual Machine , Managed Database , Object Storage , or Additional Storage : Enter generic requirements if you are not looking at a specific resource type, OR Enable the Search resource type toggle to select the desired resource. If Workload Planning finds cheaper resources with similar requirements, it will recommend them first. For multi-cloud comparison, Workload Planning uses the requirements associated with the selected resource to generate recommendations for other cloud vendors. This option also lets you to select up to five different regions for your resource.
1. Enter all your Custom requirements .
1. Once you have entered all the requirements, select the Add button. The resource requirements display. To modify or delete them, select , then choose .
1. Select the Next button.

### Visualize your recommendations

Once you move to the Recommendation workflow step, a pop-up window appears to show the tool is generating the recommendation. While it is generating, you can go to the List tab to define a new workload. The Cloudability will continue to generate the recommendation behind the scenes.

Once Cloudability has finished generated the recommendation, the pop-up will close and you will be taken to the Recommendation workflow step.

For cross-cloud comparison, choose from the Service drop-down to view recommendations for each service type (AWS, Azure, GCP, and OCI).

You can select any type of price. On-Demand, Committed, and Spot prices are calculated as monthly price per unit. Committed price is calculated based on the data displayed in the Common Information step.

To visualize the total cost of your workload and compare costs between the cloud providers side-by-side, select Next button.

To get a different recommendation:

- Select the icon to update your requirements; OR
- Select the Back button to go to the previous step. This option lets you to modify many requirements at once.

### Review your recommendation summary

In the Summary workflow step, Cloudability displays your recommendations in two tabs: Summary and Analysis .

Explore the Summary tab

The Summary tab displays a summary of the information associated with your workload. For cross-cloud comparisons, select the Chosen provider . Cloudability updates your Total Cost (monthly) accordingly.

While looking at the resources added to your workload, select Details to see additional information.

Explore the Analysis tab

The Analysis tab visualizes the breakdown of cost by service type and service provider in case of cross-cloud comparison.

Share your summary

Select from either the Summary or Analysis tab to export the workload summary as a CSV, duplicate the workload, or share it with others.

You can always go back to the previous steps from the Summary or Analysis tabs to make any change. Once you've finished defining your workload, select the Done button. Cloudability returns you to the List screen.

### Frequently Asked Questions

1. Why should I choose the cloud vendor and purchase preferences under Common Information > Service Providers ? You choose the cloud vendor and your preferred lease types and commitment types under Common Information > Service Providers so that you will get more refined recommendations based on these preferences set here.
1. How many regions can I select under Common Information > Service Providers ? Why should I select them here? You could select up to 5 regions for each cloud vendor, based on which you will get recommendations for pricing in each of these regions
1. Why am I not able to see my desired Lease Type or Commitment Type under Common Information > Service Providers ? This could be because you admin may have opted out those Lease Types or Commitment Types from the Work.Planning Preferences section.
1. Why am I seeing this message while editing an existing workload? This Workload Does Not Comply With Workload Planning Preferences The lease types and/or commitment preferences set by your administrator do not match with your workload. You can click 'Edit Workload' to update them. This could be because some of the constructs defined in your workload (eg: cloud vendor, lease type, commitment type etc.) have been updated by your admin from Work.Planning Preferences section
1. How does the feature recommend resources if I don’t choose the exact resource type (use the search by resource type option) while adding a new resource? If you haven’t chosen the exact resource type (use the search by resource type option) while adding a new resource, the feature would recommend the top cost efficient 30 resources across each selected cloud vendors based on the resource configuration you input.
1. How does the feature recommend resources if I choose the exact resource type (use the search by resource type option) while adding a new resource? If you have chosen the exact resource type (use the search by resource type option) while adding a new resource, the feature would pin that specific resource at the top as the first recommendation, followed by cost efficient 29 resources across each selected cloud vendors based on the resource configuration you input.
1. What should I do for the resource recommendations to account for my EDPs or other custom pricing? You need not do anything for the resource recommendations to account for your EDPs or other custom pricing. Cloudability already pulls your custom pricing information if exists and the discounts would be baked into Workload Planning recommendations by default.
1. Do I need to set my organization’s custom pricing in the Additional Discount / Uplift % field Work.Planning Preferences section? No. Cloudability already pulls your custom pricing information if exists and your discounts would be factored into Workload Planning recommendations by default. Additional Discount/Uplift % is for any other discounts that apply to the costs of all recommended resources, excluding Other costs. When set, this discount/uplift would be added on top of any existing custom pricing already surfaced by Cloudability
1. Why am I seeing a difference in the prices in Workload Planning recommendations from the cloud vendor’s pricing calculator? If you see a difference in the prices in Workload Planning recommendations from the cloud vendor’s pricing calculator: Check whether the resource type, region and other configurations are exactly matching between the pricing calculator and Workload Planning Check whether if you have Multi Currency enabled in Cloudability and if so verify whether the exchange rate that you had set for your preferred currency in Multi Currency module matches with the exchange rate considered by the cloud vendor Check whether you’ve logged into the cloud vendor’s pricing calculator using your organization’s account that has custom pricing enabled. If you’re checking without logging into the cloud vendor’s pricing calculator, you’re likely seeing retail prices in the calculator and custom prices in Workload Planning Check whether your admin has set any additional discounts that apply to the costs of all recommended resources from Work.Planning Preferences section
1. For bulk import of resources, what is the maximum number of resources I can add for a specific service? You could add up to 30 resources in your CSV file while doing a bulk import
1. How do I define the resource type in the CSV file while doing a bulk import? You will find that the CPU and RAM information are also appended in Workload Planning UI. While doing a bulk import, please skip the CPU and RAM information and use only the first part of the resource type name. For example, for the resource type displayed as D2s_v6 - 2 CPU/s, 8 RAM in Workload Planning UI, use D2s_v6 as the resource type name in the CSV import file. Alternatively you could also download all supported resource types from the Search Resource Type section under Add Resource and readily use those resource type names in your bulk import CSV file.
1. Do I need to define the CPU and RAM information in the bulk import CSV if I'm defining a resource type? No. If you are defining a specific resource type, you could leave all other resource configuration input fields as they would be auto filled as per the defined resource type. Even if you input your own resource configuration details, those would get overwritten by the configuration details defined by the cloud vendor
1. How can I edit a workload created by another user? The author of the workload should share the workload with edit permissions for you to be able to edit another user's workload. This applies even if you're an admin user - if you're an admin you can view all the workloads created in your org but can edit another user's workload only if they have shared it with you with edit access.

---

## Workload Planning Preferences

<!-- sub-header -->
- **breadcrumb:** Plan > Workload Planning > Workload Planning Preferences
- **source_path:** SSVCLNQ/product/workload-planning-preferences.html
- **original_file:** planning-workload-preferences.md
- **images:** []

Workload Planning Preferences allow FinOps teams to centrally define, and restrict options in Workload Planning . Any update is optional, and not required to use Workload Planning .

By default, these preferences are only visible to Workload Planning Admin, who can modify them. “WorkloadPlanningPreferencesViewOnly” permission can be assigned to a custom role to allow non-admin users to view Workload Planning Preferences without editing rights.

1. Navigate to Settings > Work . Planning Preferences .
1. For each service provider, adjust parameters based on your organization preferences and policies, and click Save . Any change will take effect immediately.

Preference Details

| Field | Description |
| --- | --- |
| Allow Service Provider | It restricts the visibility of a specific service provider when users create a workload. If an existing workload leverages a service provider that has been disabled by admins, then it will be locked, and users won’t be able to edit it. |
| Preferred Lease Type | For AWS, Azure, and GCP, admins can decide to display “Committed Pricing” and “Spot Pricing” in Cloudability Workload Planning . "Committed Pricing" refers to the price associated with potential Savings Plans, Reservations, or Commitments, depending on the service provider’s offering, and user selection. For OCI, users can decide to display “Capacity Reservation Pricing”, which provides an additional 15% discount compared to On-Demand and is forfeited upon utilization. They can also decide to display “Spot Pricing”. |
| Commitment Default Options | These preferences will impact AWS, Azure and GCP “Committed Pricing”, when displayed in Cloudability Workload Planning . Admins have the authority to disable the option selection in the UI. |
| Discount /Uplift | For each service provider, admins can add an additional Discount or Uplift %. This percentage will be applied across all prices calculated by Cloudability Workload Planning for a given provider. It doesn’t apply to “Other” costs added to a workload. Any change would apply to the existing and new workloads. |
| Exclude recommendations where the recommended instance type contains the following values. | Using this option, you can specify those resource types that should not appear in the Workload Planning recommendations for your org. This can be done using either of these 2 options: by adding the keyword so that the recommendations would skip those resource types that contain the keyword. Eg: giving the value "xlarge" would exclude all those resources that has "xlarge" in their names. by adding asterix (*) along with the keyword so that the recommendations would skip those resource types that starts with that keyword. Eg: giving the value "t4*" would exclude all those resources that starts with "t4". |

---
