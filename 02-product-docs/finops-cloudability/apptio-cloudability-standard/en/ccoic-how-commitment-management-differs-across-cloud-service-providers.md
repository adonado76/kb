---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "How Commitment Management Differs Across Cloud Service Providers"
breadcrumb:
  - "Optimize"
  - "Cloud Cost Optimization in Cloudability"
  - "How Commitment Management Differs Across Cloud Service Providers"
source_path: "SSVCLNQ/product/commitment_management_across_providers.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# How Commitment Management Differs Across Cloud Service Providers

## Purpose

The purpose of this document is to introduce how commitment-based discounts work across the different Cloud Service Providers (CSPs).

## Introduction to Commitment Types

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

## Introduction to Purchase Options

Next, there are a handful of different options that define how a commitment is structured and implemented.

Term (AWS, Azure, GCP) - A universal word used to describe the commitment’s duration, typically 1 or 3 years with special cases where they can be as little as 1 month, or up to 6 years.

Payment Option (AWS, GCP) - The term AWS uses to describe how a commitment is billed. AWS has three options for many of their commitments, no upfront (akin to Azure’s monthly), partial upfront (where half of the cost is billed upfront) and upfront. Like Azure, these payment options carry different discounts. As mentioned in Cloudability we use the vendor agnostic term, Payment Option. This term isn’t explicitly defined in GCP since their commitments are all no upfront. Nevertheless, to represent this information uniformly, we assign this parameter to GCP.

Billing Frequency (Azure) - The term Azure uses to describe how a commitment is billed. Azure has two options for many of their commitments, monthly and upfront. These billing frequencies carry different discounts. In Cloudability we use the vendor agnostic term, Payment Option, for Azure.

Region (AWS, Azure, GCP) - A universal term across vendor, this term defines where the physical resources live, thus impacting pooling, utilization potential, and flexibility. The region is relevant for most commitment types outside of AWS and Azure Savings Plans.

Availability Zone (AWS) - An Availability Zone (AZ) is one or more discrete data centers with independent power, cooling, and networking, linked within the region by low‑latency connectivity. Some AWS commitments can be purchased by AZ instead of region. In the case of an availability zone-based commitments, discounts are inherently less since the contract offers less predictability to the vendor.

## Introduction to Account Structure

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

## Introduction to Instance Size Flexibility

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

## Miscellaneous General Differences

There are several nuances that are also relevant to call out here.

- Across AWS and Azure, resource commitments purchased in terms of the # of units of a pre-determined size. This is contrast to GCP where GCE resource CUDs are purchased in discrete sub-quantities (vCPU, Memory, SSD, GPU).
- AWS and Azure’s spend commitments purchased in terms of cost of the commitment. GCP spend CUDs in contrast are purchased by the on-demand equivalent. Note that this is changing in January of 2026.
- AWS and Azure include a coverage metric, in terms of usage hours, in the billing file. GCP notably does not include this metric.

Next, we will begin to dive into how Cloudability helps optimize your cloud spend.
