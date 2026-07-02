---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Cost Allocation Methodologies"
breadcrumb:
  - "TBM Studio"
  - "Concepts and Architecture"
  - "TBM Fundementals"
source_path: "studio/new-uc/concepts-architecture/cost-allocation-method.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Cost Allocation Methodologies

Cost allocation is the process of distributing costs from where they originate to the services
and consumers that benefit from them. Choosing the right allocation methodology is one of the most
important decisions in your TBM implementation—it determines how accurately your cost model reflects
reality.

## Direct Allocation

**Definition**

Direct allocation assigns costs that are clearly and exclusively attributable to a single target.
No sharing or splitting is required because the relationship between cost and consumer is
one-to-one.

**When to Use** 

- A cost is dedicated to a single application, service, or business unit
- A vendor invoice is specific to one consumer
- A resource is exclusively used by one entity

**Advantages and Disadvantages**

|  |  |
| --- | --- |
| **Advantages** | **Disadvantages** |
| Highest accuracy—no estimation involved | Only applies to dedicated resources |
| Easy to explain and defend | Most IT costs are shared, limiting applicability |
| No driver data required | Cannot handle shared infrastructure |

**Example**

A dedicated database server running only the CRM application costs $5,000/month in hosting. This
cost is directly allocated to the CRM service with no splitting required.

Note:

**Why This Matters in TBM Studio**

In TBM Studio, direct allocation is implemented through one-to-one matching in the allocation
configuration. When the source record has a unique identifier that maps directly to a single
destination, costs flow without splitting. This is configured in Model Studio’s Single Object
Modeler using exact-match conditions on fields like Application ID or Vendor ID.

## Indirect Allocation

**Definition**

Indirect allocation distributes costs that are shared across multiple targets. Because the cost
benefits more than one consumer, you need a method to determine each consumer’s fair share.

**When to Use** 

- Infrastructure is shared across multiple applications or business units
- Costs cannot be traced to a single consumer (for example, shared network, data center
  facilities)
- A team supports multiple services simultaneously

**The Need for Allocation Drivers**

Indirect allocation requires a driver—a measurable metric that determines how to split costs
among consumers. The quality of your indirect allocation is directly tied to how well your driver
reflects actual consumption patterns. Choosing the right driver is both an art and a science.

**Example**

A shared data center costs $500,000/month in facilities (power, cooling, physical space). This
cost is allocated to the server farms housed in the data center based on rack space consumed. If the
CRM farm uses 30% of rack space, it receives $150,000 of the facilities cost.

## Driver-Based Allocation

**What Is a Driver?**

A driver is a measurable metric that determines how shared costs are distributed among targets.
Drivers represent the causal relationship between a cost and its consumers—they answer the question:
“Why does this consumer receive this share of the cost?”

**Common Driver Types** 

|  |  |  |
| --- | --- | --- |
| **Driver Type** | **Description** | **Best For** |
| Headcount / FTE | Number of employees or full-time equivalents | End-user computing, help desk, SaaS licenses |
| Transaction Volume | Number of transactions processed | Application hosting, middleware, processing services |
| Storage Consumption | GB or TB of storage used | Storage infrastructure, backup services |
| CPU / Compute Usage | CPU cores, vCPUs, or compute hours consumed | Server infrastructure, cloud compute |
| User Counts | Number of active users of a service | Application licensing, per-seat services |
| Revenue / Budget | Financial metrics of the consuming entity | General overhead allocation (least precise) |

**Choosing Appropriate Drivers**

  

The best driver has three qualities:

- **Causal relevance:** The driver should reflect what actually causes the cost. Server count
  is a better driver for compute costs than employee headcount.
- **Data availability:** The driver data must be reliably available each period. A perfect
  driver that you cannot collect is useless.
- **Proportionality:** The driver should reflect relative consumption. If Application A uses
  three times the compute of Application B, its driver value should be approximately three times
  larger.

**Driver Data Quality Considerations**

- Drivers must be numeric. Non-numeric values in a weighting column cause allocation failures in
  TBM Studio.
- Negative driver values are not supported and will cause the allocation to fail.
- Missing driver data for a target entity results in unallocated costs—those costs remain in the
  source until addressed.
- Driver data should be refreshed each period to reflect current consumption patterns.

Note:

Why This Matters in TBM Studio

In TBM Studio, drivers are configured in Model Studio’s Single Object Modeler. Each allocation
specifies a source metric, a weighting column (the driver), and matching conditions that link source
rows to destination rows. Three weighting options are available: Table (values from the destination
data set), Metric (proportional to another metric’s allocation), and Other Driver (values from a
separate driver table). Always verify driver data quality before running allocations.

## Activity-Based Costing (ABC)

**Concept Overview**

Activity-Based Costing allocates costs based on the specific activities performed to deliver a
service. Rather than using a simple ratio (like headcount), ABC identifies the discrete activities
involved in service delivery and assigns costs based on the volume of each activity consumed.

**When ABC Is Appropriate**

- You have highly diverse services with different cost structures
- Simple drivers do not accurately reflect cost causation
- You need very precise service-level costing for pricing decisions

## Complexity vs. Accuracy Trade-offs

ABC delivers the highest allocation accuracy but requires significantly more data collection and
maintenance effort. For most organizations, driver-based allocation provides sufficient accuracy
with much less overhead. Consider ABC for your highest-cost or most critical services, and use
simpler methods elsewhere.

Tip:

Start with simpler allocation methods and increase sophistication over time. Many organizations
begin with headcount or even revenue-based drivers and progressively move to more precise
consumption-based drivers as their TBM practice matures. TBM Studio supports this progression—you
can change drivers without restructuring your model.
