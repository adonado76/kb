---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Commitment Types in Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Optimize"
  - "Cloud Cost Optimization in Cloudability"
source_path: "product/commitment-types-cldy.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Commitment Types in Cloudability

The following commitments types are supported in Cloudability across the three major cloud
vendors. The following tables display the details.

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
| Resource | Compute Engine CUDs | Hourly use-it-or-lose-it | vCPU\*, Memory\*, Local SSD Disk, GPU | Machine type, region |
| Spend | Compute Engine Flex-CUDs | Hourly use-it-or-lose-it | Hourly on-demand equivalent | Machine type |
| Cloud SQL CUDs | Hourly use-it-or-lose-it | Hourly on-demand equivalent | Instance family and region |

To request support for an additional type, please
[add](https://ideas.ibm.com/new-idea "(Opens in a new tab or window)")
or upvote an idea on our community (IBM Ideas) or contact your account representative. Choose
Rate Optimization
as the category for the idea.

**Parent topic:** [Cloud Cost Optimization in Cloudability](../product/cloud_cost_optimization.html)
