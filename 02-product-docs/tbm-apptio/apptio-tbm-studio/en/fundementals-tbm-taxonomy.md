---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "The TBM Taxonomy"
breadcrumb:
  - "Concepts and Architecture"
  - "TBM Fundementals"
  - "The TBM Taxonomy"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/tbm-taxonomy.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# The TBM Taxonomy

The TBM taxonomy is a standardized framework for categorizing IT costs into a layered hierarchy. It provides a common language for mapping raw financial data to the services and consumers that drive IT spending. Think of it as a four-story building: costs enter at the ground floor and flow upward until they reach the business units that ultimately consume them.

## The Four Layers

The standard TBM taxonomy defines four primary layers. Each layer answers a different question about IT spending:

| Layer | Question | Common Examples | TBM Studio Mapping |
| --- | --- | --- | --- |
| Layer | Question | Common Examples | TBM Studio Mapping |
| Cost Pools | Where do costs originate? | Hardware, Software, Labor, Facilities, Cloud | Cost Source model object and general ledger tables |
| IT Towers | How are costs organized? | Compute, Storage, Network, End-User, Security | Intermediate model objects (Vendors, Technology Services) |
| IT Services / Apps | What does IT deliver? | Email, ERP, CRM, Data Analytics, DevOps Platform | Solutions model object |
| Business Units | Who uses IT services? | Sales, Marketing, Finance, Operations, R&D | Business Units model object |

## Layer 1: Cost Pools — Where Costs Originate

Cost pools represent the raw financial categories where IT spending originates. These typically correspond to general ledger accounts or vendor invoices. Cost pools answer the question: “What type of thing are we spending money on?”

- Hardware : Servers, storage devices, network equipment, end-user devices
- Software : Licensed software, SaaS subscriptions, maintenance agreements
- Labor : Internal IT staff, contractors, outsourced services
- Facilities : Data center space, power, cooling
- Cloud & Hosting : IaaS, PaaS, and SaaS consumption charges
- Telecom : Network services, internet connectivity, voice services

Why This Matters in TBM Studio

In TBM Studio, cost pools are typically represented by the Cost Source model object, which is fed by general ledger data imported through Data Studio. The Cost Source is usually the starting point of your model, sitting at the bottom of the allocation chain. TBM Studio also supports machine learning to automatically map GL accounts to standard cost pool categories.

## Layer 2: IT Towers — How Costs Are Organized

IT Towers group related costs into functional technology categories. They represent the infrastructure and services that IT operates, regardless of which business functions use them. Think of towers as the “building blocks” of IT delivery.

Standard IT Tower categories include Compute, Storage, Network, End-User Computing, Application Development, IT Management, and Security. Towers bridge the gap between raw cost inputs and the business-facing services they support.

Why This Matters in TBM Studio

In TBM Studio, IT Towers are represented as intermediate model objects between Cost Source and Solutions. Common implementations use Vendor and Technology Services objects as the tower layer. Allocations from cost pools to towers typically use driver-based allocation with metrics like server count, storage consumption, or FTE headcount.

## Layer 3: IT Services and Applications — What IT Delivers

IT Services represent the business-facing capabilities that IT provides. This is where costs become meaningful to non-technical stakeholders. A business leader may not care about server costs, but they care deeply about what their CRM system costs and whether it delivers adequate value.

This layer maps tower costs to specific services like email, enterprise resource planning (ERP), customer relationship management (CRM), data analytics platforms, and custom internal applications.

Why This Matters in TBM Studio

In TBM Studio, the Solutions model object typically represents this layer. Cost flows from Technology Services into Solutions through allocations driven by application-to-infrastructure mapping data. The model diagram view provides a visual trace of how costs flow from cost pools through towers into individual services.

## Layer 4: Business Units and Consumers — Who Uses IT Services

The final layer maps IT service costs to the business units or departments that consume them. This is the layer that enables showback and chargeback—showing each business unit what they are paying for IT services based on their actual consumption.

Business unit allocation is typically driven by consumption metrics such as user counts, transaction volumes, or application usage data. The goal is to create a fair and transparent distribution of IT costs that reflects actual resource usage.

Why This Matters in TBM Studio

In TBM Studio, Business Units is the terminal model object at the top of the allocation chain. The full cost flow typically follows: Cost Source → Vendors → Technology Services → Solutions → Business Units. Model reports (Sankey views) provide an intuitive visualization of this complete cost flow.

## How Data Flows Through the Layers

1. Cost Pool entry : $10M in server hardware costs enters from the general ledger
1. Tower allocation : $10M is allocated to Compute tower based on server purpose (production, development, testing)
1. Service allocation : Compute costs are allocated to services (CRM gets $3M, ERP gets $4M, Email gets $1.5M, Other gets $1.5M) based on server usage metrics
1. Consumer allocation : CRM’s $3M is allocated to Sales ($1.8M), Marketing ($0.9M), and Support ($0.3M) based on user counts

At each layer, the total cost remains the same—it is simply distributed with increasing granularity. This principle of cost conservation is fundamental to TBM and ensures that every dollar is accounted for.

## Flexibility and Customization

- Additional layers : Some organizations add layers (for example, sub-towers or service tiers) to capture more detail
- Custom categories : The specific categories within each layer can be customized to match your organization’s terminology and structure
- Simplified models : Smaller organizations may combine or skip layers for a simpler model
- Multiple allocation paths : Costs can flow through different paths depending on their nature (for example, labor costs might follow a different path than hardware costs)
