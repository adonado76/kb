---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "07-Optimize-Cloud-Cost-Optimization"
source_files_count: 10
last_updated: "2026-07-13"
---

# 07-Optimize-Cloud-Cost-Optimization

## Cloud Cost Optimization in Cloudability

<!-- sub-header -->
- **breadcrumb:** Optimize > Cloud Cost Optimization in Cloudability
- **source_path:** SSVCLNQ/product/cloud_cost_optimization.html
- **original_file:** optimize-cloud-cost-optimization-in-cloudability.md
- **images:** []

## Cloud Cost Optimization in Cloudability

Summary

Cloudability helps organizations take control of their cloud spend by introducing foundational FinOps concepts that drive smarter financial decisions. This section provides an overview of the two primary optimization concepts, workload and rate optimization. Specifically, it introduces the mental model behind rightsizing and commitment-based discounts, which allow teams to lower unit costs while maintaining flexibility and performance.

Cloudability offers the tools and insights needed to manage commitments effectively, automate savings, and build a resilient cloud financial plan. Explore the sections to learn how Cloudability supports commitment management across cloud providers and helps you unlock durable, scalable savings.

---

## Commitment Support Information Architecture

<!-- sub-header -->
- **breadcrumb:** Optimize > Cloud Cost Optimization in Cloudability > Commitment Support Information Architecture
- **source_path:** SSVCLNQ/product/intro_cloudability_support_commitments.html
- **original_file:** cloudability-commitment-support-information-architecture.md
- **images:** []

## Commitment Support Information Architecture

### Purpose

The purpose of this document is to introduce how Cloudability supports commitment management through a consistent approach to modeling, measuring, and acting on the different commitment types across CSPs.

Cloudability normalizes vendor-specific commitments (RIs, Reservations, Savings Plans, CUDs, etc.) into a single model and presents them through three primary areas.

Commitment Manager — Visually communicates the commitment lifecycle with a cross‑vendor, cross-type view. Portfolio and recommendations are layered on top of each other to give FinOps practitioners a landing page that provides a basic understanding of current performance and future opportunity.

Commitment Portfolio — Summary page to view your commitment inventory and understand to past performance. Data is represented at the vendor level with the ability to dig into each service and commitment type to understand performance and risk.

Commitment Recommendations — Leveraging a similar structure to the portfolio, the recommendation pages are organized by vendor and type and use our propriety model to provide recommendations for future savings opportunities. Recommendations are fundamentally driven off of past usage called the Usage Profile .

Each of these three pages are similarly structured. Five common KPIs across the top of the page with a table, chart, or mix of both to communicate the meta data required to deliver on the purpose of the page. We follow common header selections across the page toolbar and support table exports in a what-you-see-is-what-you-get manner. As mentioned in the page definition above, the portfolio and recommendations pages are structured by vendor.

In addition to these three pages, a fourth page, the commitment preferences, provide a centralized location for settings that capture your business preferences and strategy. These settings govern the target recommendation type and make purchasing assumptions consistent and digestible across vendors and commitment types.

Tips to use Cloudability Commitments

- Start in the Optimizations Dashboard to develop a general understanding of current performance and future opportunity. Establish materiality in the back of your mind if not already.
- Land on the Commitment Manager to visually gauge near-term portfolio health and immediate opportunity. Consider digging into vendor/service level views and use the reporting range to focus on past performance or future opportunity.
- Navigate to the Commitment Portfolio to validate current performance and trends through an understanding of PSR, utilization, coverage, and remaining exposure.
- Uncover opportunities via Commitment Recommendations by using our dynamic on-the-fly recommendation model.
- Leverage the commitment portfolio and native Cloudability reporting to build out chargeback/show back to recognize savings and build organization buy-in to achieve mature/aggressive optimization strategies.

---

## Commitment Types in Cloudability

<!-- sub-header -->
- **breadcrumb:** Optimize > Cloud Cost Optimization in Cloudability > Commitment Types in Cloudability
- **source_path:** SSVCLNQ/product/commitment-types-cldy.html
- **original_file:** cloudability-commitment-types-in.md
- **images:** []

## Commitment Types in Cloudability

The following commitments types are supported in Cloudability across the three major cloud vendors. The following tables display the details.

AWS Supported Commitment Types

| Category | Type | Billed | Purchased in | Scope |
| --- | --- | --- | --- | --- |
| Resource | EC2 Reserved Instance | Hourly use-it-or-lose-it | Units | Instance type, region, OS |
| RDS Reserved Instance | Hourly use-it-or-lose-it | Units | Region, database engine |
| Open Search Reserved Instance | Hourly use-it-or-lose-it | Units | Instance type, payment option, region |
| Redshift Reserved Nodes | Hourly use-it-or-lose-it | Nodes | Node type, region |
| Elasticache Reserved Nodes | Hourly use-it-or-lose-it | Nodes | Node type, region, OS |
| Spend | Compute Savings Plan | Hourly use-it-or-lose-it | Hourly cost | Apply to EC2 across instance family, size, AZ, Region, OS or tenancy, and also apply to Fargate or Lambda. |
| EC2 Savings Plan | Hourly use-it-or-lose-it | Hourly cost | Instance family and region |
| SageMaker Savings Plan | Hourly use-it-or-lose-it | Hourly cost | Apply regardless of instance family, size, AZ, AWS Region, or components. |

Azure Supported Commitment Types

| Category | Type | Billed | Purchased in | Scope |
| --- | --- | --- | --- | --- |
| Resource | Virtual Machine Reserved Instance | Hourly use-it-or-lose-it | Quantity | Instance type, region, OS |
| SQL Database and Managed Instanced Reserved Instance | Hourly use-it-or-lose-it | Quantity | Perf tier, region, deployment type |
| Database for MySQL Reserved Capacity | Hourly use-it-or-lose-it | Instance | Deployment Option, Instance, and Region |
| Database for PostgreSQL Reserved Capacity | Hourly use-it-or-lose-it | Instance | Deployment Option, Instance, and Region |
| Azure Blob Storage Reserved Capacity | Hourly use-it-or-lose-it | Size (100Tb, 1Pb) | Access Tier, Redundancy, Size, and Region |
| Cosmos DB Reserved Capacity | Hourly use-it-or-lose-it | Reserved Units (RU/s) | Tier |
| Synapse Analytics Dedicated SQL Pools | Hourly use-it-or-lose-it | Data Warehouse Units (DWUs) | Region |
| Cache for Redis Reservations | Hourly use-it-or-lose-it | Nodes (analogous to total cache capacity | Node type, region, OS |
| App Service Reserved Instances | Hourly use-it-or-lose-it | Quantity | Instance, tier, region |
| Spend | Compute Savings Plan | Hourly use-it-or-lose-it | Hourly cost | Scope Type |
| Databricks Prepurchase Plans | Fungible Credits across term | 1 DBU = $1 | Instance family and region |
| Synapse Analytics Prepurchase Plans | Fungible Credits across term | 1 SCU = $1 | Applicable across 7 products |
| Microsoft Foundry Provisioned Throughput | Hourly use-it-or-lose-it | PTU, a normalized throughput usage unit | Region, Deployment Type |

GCP Supported Commitment Types

| Category | Type | Billed | Purchased in | Scope |
| --- | --- | --- | --- | --- |
| Resource | Compute Engine CUDs | Hourly use-it-or-lose-it | vCPU*, Memory*, Local SSD Disk, GPU | Machine type, region |
| Spend | Compute Engine Flex-CUDs | Hourly use-it-or-lose-it | Hourly on-demand equivalent | Machine type |
| Cloud SQL CUDs | Hourly use-it-or-lose-it | Hourly on-demand equivalent | Instance family and region |

To request support for an additional type, please add or upvote an idea on our community (IBM Ideas) or contact your account representative. Choose Rate Optimization as the category for the idea.

---

## How Commitment Management Differs Across Cloud Service Providers

<!-- sub-header -->
- **breadcrumb:** Optimize > Cloud Cost Optimization in Cloudability > How Commitment Management Differs Across Cloud Service Providers
- **source_path:** SSVCLNQ/product/commitment_management_across_providers.html
- **original_file:** ccoic-how-commitment-management-differs-across-cloud-service-providers.md
- **images:** []

## How Commitment Management Differs Across Cloud Service Providers

### Purpose

The purpose of this document is to introduce how commitment-based discounts work across the different Cloud Service Providers (CSPs).

### Introduction to Commitment Types

All commitment-based discount pricing models pursue the same goal, exchange usage predictability and vendor lock in for a discounted price. Each provider offers a way to pay less than on-demand if you’re willing to commit, often to a specific resource footprint and level of spend. The details vary, but the practical questions are universal, What discount rate am I receiving? How much spend am I committed too and for how long? How is the discount applied and reported? How do I measure performance?

First, we will define some terminology to simplify this discussion.

Commitment - A commitment is our vendor agnostic, short-hand term used to describe these discounts across Cloudability.

Commitment Type - A commitment type is the Cloudability term chosen to describe the different versions of these contracts. (Type) is explicitly used to differentiate the pricing model from the underlying service name. As you will soon learn, some services, particularly compute, have multiple applicable commitment types. Notably, this definition is defined in FOCUS . We agree and accept this definition.

Resourced-based Commitments - Across clouds, two patterns emerge. First, resource-based commitments provide a discount in exchange for a commitment to a certain amount of usage on a product or service.

Spend-based Commitments - These commitments provide a discount in exchange for a commitment to a certain amount of spend on a product or service. Spend-based commitments differ from resource-based commitments in that they cover a wider set of usage but require careful attention to utilization so you don’t buy more commitment than your workload mix can consume. Resourced-based commitments have the benefit of a greater discount with clearer breakeven math, while the tradeoff is tighter alignment to usage attributes.

Commitment Category - We will refer to whether a commitment type can be categorized as resource or spend as the commitment category. Notably, this definition is also defined in FOCUS . We agree and accept this definition.

The CSPs have formal names for each commitment type. Here we will attempt to generally explain how the names of commitments vary across vendor -

Reserved Instance - RI (AWS, Azure) - Provides a discount in exchange for committing to a specific amount of usage on a defined product or service. Commonly used for services where the underlying usage is defined as a compute instance. For example, the terminology will shift to reserved node for AWS Redshift because the underlying usage is defined in nodes. Regardless, in these situations, this concept works similarly.

Note that Reserved Instances are commonly abbreviated as RIs.

Savings Plan - SP (AWS,Azure) - Provides a discount in exchange for committing to a specific amount of spend (often expressed as $/hour) on eligible services. This commitment type is specific to AWS and Azure and only applicable to compute spend. For Azure, the Savings Plans are explicitly broken out into a separate section from the other reservations in the purchasing pages in their console.

Note that Saving Plans are commonly abbreviated as SPs.

Reservations (Azure) - Azure’s generic term for commitments across multiple services.

Prepurchase Plan - PPP (Azure) - An Azure spend commitment option using fungible credits that do not expire hourly, applied across eligible services.

Note that Purchase Plans are commonly abbreviated as PPPs.

Committed Use Discount - CUD (GCP) - GCP’s generic term for commitments across multiple services.

Spend CUDs (GCP) - GCE’s spend‑based commitment variant. It is functionally similar to an AWS/Azure Savings Plan. Google Compute Engine (GCE)’s spend CUD variant is specifically referred to as a GCE Flex-CUD whereas the resource CUD is simply a GCE CUD. GCP is unique in contrast to AWS and Azure in that they prioritize commitments for services outside of compute.

### Introduction to Purchase Options

Next, there are a handful of different options that define how a commitment is structured and implemented.

Term (AWS, Azure, GCP) - A universal word used to describe the commitment’s duration, typically 1 or 3 years with special cases where they can be as little as 1 month, or up to 6 years.

Payment Option (AWS, GCP) - The term AWS uses to describe how a commitment is billed. AWS has three options for many of their commitments, no upfront (akin to Azure’s monthly), partial upfront (where half of the cost is billed upfront) and upfront. Like Azure, these payment options carry different discounts. As mentioned in Cloudability we use the vendor agnostic term, Payment Option. This term isn’t explicitly defined in GCP since their commitments are all no upfront. Nevertheless, to represent this information uniformly, we assign this parameter to GCP.

Billing Frequency (Azure) - The term Azure uses to describe how a commitment is billed. Azure has two options for many of their commitments, monthly and upfront. These billing frequencies carry different discounts. In Cloudability we use the vendor agnostic term, Payment Option, for Azure.

Region (AWS, Azure, GCP) - A universal term across vendor, this term defines where the physical resources live, thus impacting pooling, utilization potential, and flexibility. The region is relevant for most commitment types outside of AWS and Azure Savings Plans.

Availability Zone (AWS) - An Availability Zone (AZ) is one or more discrete data centers with independent power, cooling, and networking, linked within the region by low‑latency connectivity. Some AWS commitments can be purchased by AZ instead of region. In the case of an availability zone-based commitments, discounts are inherently less since the contract offers less predictability to the vendor.

### Introduction to Account Structure

Beyond these basic payment options, it is crucial to understand how the account structure will dictate how a commitment is realized.

Payer Account - Cloudability’s vendor agnostic term to describe the parent account experiencing charges.

Linked Account - Cloudability’s vendor agnostic term to describe the child account experiencing charges. Linked accounts have a many to one relationship with payer accounts.

Organization Units - OU (AWS) - A folder-like container you use inside AWS Organizations to group multiple AWS accounts under a common hierarchy (Root → OUs → Accounts). OUs don’t own resources or incur charges themselves—they exist to organize accounts and apply governance at scale. These units can be nested and operate above the level at which a commitment is purchased.

Management Account (AWS) - Akin to the Cloudability Payer, this AWS account represents where users can create policies and delegate member accounts. The management account does not have to be directly under the root, it can be placed anywhere in the organization.

Member Account (AWS) - Akin to a linked account, this AWS account is where resources live and costs are generated.

Billing Account (Azure) - The account that defines the billing model (EA, MCA, CSP/MPA). Like AWS OUs, this construct sits above the scope of relevance for a commitment.

Billing Profile (Azure) - A billing profile represents an invoice and the related billing information such as payment methods and billing address. It is akin to a payer account in Cloudability.

Subscription (Azure) - In Azure, a subscription is a container for resources that also acts as the unit of billing. Usage generated by resources in a subscription is invoiced through whatever billing account model you’re on (EA, MCA, CSP/MPA).

Billing Subscription (Azure) - Building on the definition of a subscription, an Azure billing subscription is the subscription through which usage rolls up to your invoice. It is akin to a linked account in Cloudability.

Scope (Azure) - At time of purchase, a commitments scope can cover one subscription or multiple subscriptions. When shared, the discount is applied to eligible subscriptions within your billing context.

- When single subscription, the reservation discount is applied to the matching resources in the subscription you select.
- When single resource group, the reservation discount is applied only to the matching resources in the resource group you select.
- For Enterprise Agreement customers, the billing context is all subscriptions in the EA enrollment.
- For Pay-As-You-Go customers, the billing context is all eligible subscriptions created by the account administrator.
- For Microsoft Customer Agreement, the billing context is the billing profile.

Billing Account (GCP) - GCP’s payer account where resources live and costs are generated.

Project (GCP) - GCP’s linked account where resources live and costs are generated.

### Introduction to Instance Size Flexibility

About Instance Size Flexibility for RDS Rls

Amazon RDS reserved instances (RIs) now benefit from Instance Size Flexibility (ISF) much in the same way that ISF applies for EC2 instances. We've updated the engine that powers our RI Planner to accommodate the change in our recommendations for RDS instances. Purchasing with the ISF benefit will reduce your administrative overhead and lead you to maximum savings.

What is ISF ?

ISF is a feature of RDS RIs that lets the savings of an RI apply to any size of instance within a family. You automatically get this benefit when you to purchase an RI within the same AWS Region (for both Single-AZ and Multi-AZ configurations), database engine, and instance family. ISF is available for the following database engines: Amazon Aurora, MariaDB, MySQL, PostgreSQL, Oracle (Bring Your Own License edition).

How does ISF work ?

ISF manages your reservations in a points-based system where a scale determines the units assigned to each size within a family. When you run an instance, db.m3.large for example, any ISF RI within the db.m3 family can apply to the instance and the number of points your RI has relative to the points for the instance size ran determines how much or how many of the RI is consumed by that instance hour. The numbers of normalized units per DB instance size are:

ISF in the RI Planner

In our RI Planner in the RDS tab, we take into consideration ISF when making recommendations. We still analyze your per-second instance usage and take into account your entire RI inventory, including ISF and non-ISF RIs, before making a recommendation. For ISF RIs, because any size RI can apply to an instance you run within a family, you’ll no longer need to purchase a variety of sizes and instead can purchase to the family, database, and region based on normalized units. Effectively, you can abstract away the concept of purchasing to your instance type profile and instead just purchase points.

There are a number of ways you could achieve this, but after much internal scenario testing and discussion with our biggest customers, we’ve established an effective pattern that we’ve built into the planner.

In the schematic below, sample usage over a time period helps illustrate how ISF works. For each time unit, imagine you are running a combination of instances. Targeting a waterline is still valid and in the case for 100% RI utilization, we'd recommend you purchase 10 Large RIs, since those are the smallest instance size available. You have one RI purchase and when your normalized usage stays the same or increases, your RIs will remain perfectly utilized.

The RI Planner Details page shows how we apply ISF to an RDS instance.

Our RDS ISF strategy

The philosophy we took with EC2 ISF focused on reducing your management overhead while maximizing your savings. For RDS ISF as well, we make recommendations for the smallest instance size possible and Single-AZ. This allows for maximum coverage with the smallest set of RI parcels. Note that the parcels themselves will be large and you may need to request an increase to your RI purchase limit from Amazon to accommodate the purchase of a large quantity of small instances sizes.

You’ll benefit from a more streamlined RI lifecycle with the purchase of the large quantity, rather than in the past where you would have multiple purchases of a variety of sizes per family. This strategy will also help you better manage your inventory if your usage decreases with the ability to sell off a much more granular number of RI units to fit the new usage patterns.

What is ISF ?

ISF is a feature of RDS RIs that lets the savings of an RI apply to any size of instance within a family. You automatically get this benefit when you to purchase an RI within the same AWS Region (for both Single-AZ and Multi-AZ configurations), database engine, and instance family. ISF is available for the following database engines: Amazon Aurora, MariaDB, MySQL, PostgreSQL, Oracle (Bring Your Own License edition).

How does ISF work ?

ISF manages your reservations in a points-based system where a scale determines the units assigned to each size within a family. When you run an instance, db.m3.large for example, any ISF RI within the db.m3 family can apply to the instance and the number of points your RI has relative to the points for the instance size ran determines how much or how many of the RI is consumed by that instance hour. The numbers of normalized units per DB instance size are:

ISF in the Commitment Recommendations

In our Commitment Recommendations, we take into consideration ISF when making recommendations. We still analyze your per-second instance usage and take into account your entire RI inventory, including ISF and non-ISF RIs, before making a recommendation. For ISF RIs, because any size RI can apply to an instance you run within a family, you’ll no longer need to purchase a variety of sizes and instead can purchase to the family, database, and region based on normalized units. Effectively, you can abstract away the concept of purchasing to your instance type profile and instead just purchase points.

There are a number of ways you could achieve this, but after much internal scenario testing and discussion with our biggest customers, we’ve established an effective pattern that we’ve built into the planner.

In the schematic below, sample usage over a time period helps illustrate how ISF works. For each time unit, imagine you are running a combination of instances. Targeting a waterline is still valid and in the case for 100% RI utilization, we'd recommend you purchase 10 Large RIs, since those are the smallest instance size available. You have one RI purchase and when your normalized usage stays the same or increases, your RIs will remain perfectly utilized.

Commitment Recommendations Details page shows how we apply ISF to an RDS instance.

Our RDS ISF strategy

The philosophy we took with EC2 ISF focused on reducing your management overhead while maximizing your savings. For RDS ISF as well, we make recommendations for the smallest instance size possible and Single-AZ. This allows for maximum coverage with the smallest set of RI parcels. Note that the parcels themselves will be large and you may need to request an increase to your RI purchase limit from Amazon to accommodate the purchase of a large quantity of small instances sizes.

You’ll benefit from a more streamlined RI lifecycle with the purchase of the large quantity, rather than in the past where you would have multiple purchases of a variety of sizes per family. This strategy will also help you better manage your inventory if your usage decreases with the ability to sell off a much more granular number of RI units to fit the new usage patterns.

### Miscellaneous General Differences

There are several nuances that are also relevant to call out here.

- Across AWS and Azure, resource commitments purchased in terms of the # of units of a pre-determined size. This is contrast to GCP where GCE resource CUDs are purchased in discrete sub-quantities (vCPU, Memory, SSD, GPU).
- AWS and Azure’s spend commitments purchased in terms of cost of the commitment. GCP spend CUDs in contrast are purchased by the on-demand equivalent. Note that this is changing in January of 2026.
- AWS and Azure include a coverage metric, in terms of usage hours, in the billing file. GCP notably does not include this metric.

Next, we will begin to dive into how Cloudability helps optimize your cloud spend.

---

## Introduction to Optimization FAQ

<!-- sub-header -->
- **breadcrumb:** Optimize > Cloud Cost Optimization in Cloudability > Introduction to Optimization FAQ
- **source_path:** SSVCLNQ/product/introduction_to_cloud_cost_faq.html
- **original_file:** cloudability-introduction-optimization-faq.md
- **images:** []

## Introduction to Optimization FAQ

---

## Introduction to Rate Optimization

<!-- sub-header -->
- **breadcrumb:** Optimize > Cloud Cost Optimization in Cloudability > Introduction to Rate Optimization
- **source_path:** SSVCLNQ/product/intro_rate_optimization.html
- **original_file:** cloudability-introduction-rate-optimization.md
- **images:** []

## Introduction to Rate Optimization

### Purpose

The purpose of this document is to introduce the second primary cloud cost optimization concept, Rate Optimization.

### What is Rate Optimization?

Rate optimization is the practice of lowering the effective price you pay for cloud service by selecting and combining pricing mechanisms that fit your usage profile, risk tolerance, and business constraints. In contrast to workload optimization, the objective of rate optimization is to materially reduce unit costs while maintaining performance, flexibility, and workload architecture. The concept of focus here will be Commitment-based Discounts, the pricing model where you commit to using a certain amount of cloud resources for a specified period in exchange for lower prices compared to pay-as-you-go rates.

### Core Levers

There are several considerations for a comprehensive rate optimization strategy.

Negotiated Pricing - Contracted discounts based on enterprise agreements, volume, or term. Typically, reduced-price contracts are negotiated for on-demand spend once an organization reaches a significant level of cloud spend.

Commitment ‑ Based Discounts - Typically, this pricing model requires customers' commitment to using a certain amount of cloud resources for a specified period in exchange for lower prices compared to the pay-as-you-go rates. These contracts can be purchased directly through cloud vendors' cost management portals and often are applied hourly on a use-it-or-lose-it basis. Examples include reserved instances, savings plans, prepurchase plans, reservations, and committed use discounts.

Other Price Mechanisms - Across the broad spectrum of cloud services, there are pricing models that support niche use cases such as spot, marketplace, promotional credits, and regional pricing discounts.

Importantly, reduced price contracts can be negotiated for both on-demand and commitment-based discounts. Depending on the vendor, service, and negotiated contract, these agreements can either supersede each other or stack. Understanding all the tools at your disposal is crucial for developing and implementing the optimal rate optimization strategy for your organization.

Cloudability's native reporting functionality can assist across these three pillars of rate optimization by surfacing insights. Cloudability Commitments takes this support a step further for Commitment‑Based Discounts by building bespoke functionality to ensure organizations have what they need to make the most of these contracts. Moving forward, we will refer to these contracts simply as Commitments, our vendor agnostic, short-hand term used to describe these discounts in Cloudability.

### Leveraging Commitments in Your Rate Optimization Strategy

Rate optimization at an introductory level can be an easy decision when workloads are either stable and predictable or significant growth is imminent. In this scenario, commitments are likely to be fully utilized with minimal risk to waste. Little analysis is required to ensure savings.

At an intermediate level, procurement managers, FinOps practitioners, and infrastructure stakeholders should coordinate closely to build confidence where current and future workloads will run. Clear ownership of accounts and usage is essential for commitments to be pooled and shared effectively, with governance in place to review performance and adjust purchase strategy over time. From here, commitments can be purchased into higher levels of coverage or even begin to cover unstable workloads.

Reaching maximum savings means treating commitments as a living financial portfolio. You cover all committable services, layer different terms, and ladder contracts, so no single month carries renewal risk, and you select payment options that fit cash constraints. You can enable sharing to pool commitment coverage across accounts and regions and leverage convertible/exchangeable contracts to manage risk when applicable. Finally, you close the loop with automation—continuously sizing, rebalancing, and validating contracts against forecast. The result is durable savings—often a 50% or more discount —without sacrificing flexibility.

Cloudability's commitment to our customers, is to provide visibility, generate recommendations, and offer automation to help organizations of all sizes reach expert status by implementing the optimal commitment strategy to realize maximum savings.

---

## Configure Optimization Functionality

<!-- sub-header -->
- **breadcrumb:** Optimize > Configure Optimization Functionality
- **source_path:** SSVCLNQ/product/configure_optimization_functionality.html
- **original_file:** optimize-configure-optimization-functionality.md
- **images:** []

## Configure Optimization Functionality

---

## Configuring Commitment Management

<!-- sub-header -->
- **breadcrumb:** Optimize > Configure Optimization Functionality > Configuring Commitment Management
- **source_path:** SSVCLNQ/product/configuring_commitment_management.html
- **original_file:** functionality-configuring-commitment-management.md
- **images:** []

## Configuring Commitment Management

---

## Supplementary Credentialing Help for Commitment Functionality

<!-- sub-header -->
- **breadcrumb:** Optimize > Configure Optimization Functionality > Supplementary Credentialing Help for Commitment Functionality
- **source_path:** SSVCLNQ/product/supplementary_credentialing_help_for_commitment_functionality.html
- **original_file:** functionality-supplementary-credentialing-help-commitment.md
- **images:**
  - 03-media/apptio-cloudability-standard/details.jpg

## Supplementary Credentialing Help for Commitment Functionality

You must have administrator rights in Cloudability to view or enable credentials. If you don't have administrator rights, contact your organization’s primary Cloudability administrator for assistance.

### Credentialing Commitment Management for AWS

Generate recommendations for AWS EC2

The Cloudability product suite enables optimizing the usage of AWS EC2 Convertible Reserved Instances (CRIs) including cost monitoring, reporting, and recommendations including CRI exchange recommendations. The following information is about enabling and utilizing convertible reserved instance exchange recommendations.

Verify permissions

Before you get started, you'll want to make sure that you have the appropriate ec2:GetReservedInstancesExchangeQuote permission enabled. This permission is required for Cloudability to generate convertible exchange recommendations for either partial or all upfront CRIs.

To check the status of the required permission:

1. Navigate to Settings > Vendor Credentials .
1. Within the AWS tab, select to view the permissions of any relevant accounts. Accounts that do not have the necessary permissions enabled are identified by anything other than a green checkmark next to the ec2:GetReservedInstancesExchangeQuote line item. If the required permission is not enabled, you can enable it by regenerating a Cloud Formation template and applying it to the applicable accounts. For more information, see Cloudability Manage AWS credentials . Note: After the CloudFormation template is applied and verified by the Cloudability Platform, it will take approximately 1 hour before recommendations appear.

Viewing the Owned Savings Plan Inventory

Getting started

Before you begin, you will want to ensure that the necessary permissions have been enabled, which provide access to Savings Plan functionality.

Credentialing must be viewed and performed by a user with admin rights for your Cloudability account. If you do not have admin access or you are not sure if you have admin rights, check with your organization’s primary Cloudability administrator.

To check the status of the necessary credentials:

1. Navigate to Settings > Vendor Credentials . In the primary accounts view for the AWS and Azure tabs, any master payer or linked account that owns Savings (or you are intending to use to purchase Savings) has a green box with a white check status indicator under Advanced Features
1. For an account with any status indicators other than the green box with a white checkmark, select to inspect the individual credentials. x
1. In the Credential Details window, if the savings plans:DescribeSavingsPlans permission in the Reservations tab shows a red x , it needs to be updated (by regenerating and applying CloudFormation templates) before you can see an inventory of your Savings Plans.

### Credentialing Commitment Management for Azure

Validate your account access

Commitment Recommendations generates Azure resource-based commitment recommendations by accessing the Azure Cloud API. Since Azure Cloud limits API access to enterprise accounts, you must ensure:

- Your account is covered by an Enterprise Agreement
- You have access to the Azure Enterprise Portal

If you don't have an enterprise account, access to the Azure Enterprise Portal, or if you aren't sure, contact your Azure account representative for assistance.

Enable your Azure credentials

1. To check the status of your Azure credentials, navigate to Settings > Vendor Credentials .
1. Select the AZURE tab.
1. Ensure Billing Reports and Advanced Features are enabled for the master (enrollment) account. You should see two green check boxes on the row for the master account.

- While it's best to have Billing Reports and Advanced Features enabled for both master (enrollment) and linked (subscription) accounts, you only need to enable these permissions for the master account to use the Commitment Recommendations for Azure.

- While it's best to have Billing Reports and Advanced Features enabled for both master (enrollment) and linked (subscription) accounts, you only need to enable these permissions for the master account to use the Commitment Recommendations for Azure.

---

## Using Commitment Preferences to Configure for Actionable Opportunities

<!-- sub-header -->
- **breadcrumb:** Optimize > Configure Optimization Functionality > Using Commitment Preferences to Configure for Actionable Opportunities
- **source_path:** SSVCLNQ/product/using_commitment_preferences_to_configure_for_actionable_opportunities.html
- **original_file:** functionality-using-commitment-preferences-configure-actionable-opportunities.md
- **images:** []

## Using Commitment Preferences to Configure for Actionable Opportunities

---
