---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "What is TBM Studio?"
breadcrumb:
  - "TBM Studio"
  - "Getting Started"
source_path: "studio/new-uc/getting-started/what-istbm.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# What is TBM Studio?

|  |  |
| --- | --- |
| **Content Type** | Conceptual |
| **Target Audience** | New Users |
| **Time to Complete** | 3-5 minutes |
| **Prerequisites** | None |

## Introduction

TBM Studio is a comprehensive platform that helps organizations understand, manage, and
optimize their technology business spend. Whether you’re tracking IT costs, allocating
expenses to business units, or creating executive dashboards, TBM Studio provides the tools
you need to turn raw financial and operational data into actionable insights.

## What TBM Studio Does

TBM Studio solves a critical challenge that most IT and finance teams face: how to
accurately track technology costs and demonstrate the value IT delivers to the business.
Without the right tools, cost data lives in disconnected spreadsheets; allocations are
manual and error-prone, and leadership lacks visibility into where technology dollars are
going.

TBM Studio addresses these challenges by providing:

- **Unified data management**: Bring together cost data from general ledgers, vendor
  invoices, cloud bills, and other sources into a single platform
- **Flexible cost modeling**: Allocate technology costs from their source through
  infrastructure layers to the applications and services that consume them
- **Interactive reporting**: Create dashboards and reports that let stakeholders
  explore costs, identify trends, and make data-driven decisions

The result is a clear, defensible view of technology costs that support budgeting,
chargeback, cost optimization, and strategic planning.

## The Three Core Components

TBM Studio consists of three integrated studios that work together to support the complete
data-to-insights workflow:

## Data Studio: Prepare Your Data

**Purpose**: Collect, transform, and enhance your data so it’s ready for analysis.

Data Studio is where you bring raw data into TBM Studio and shape it to meet your needs.
You can:

- Upload data from Excel files, CSV files, or other sources
- Transform data through a visual pipeline of operations (filter, join, pivot, etc.)
- Enrich data with formulas and calculated columns
- Manage monthly data versions to track changes over time
- Partition data by date to automatically distribute information across time periods

**When you use it**: When you need to prepare cost data from your general ledger, map
vendor names to a standard taxonomy, or combine multiple data sources into a single
view.

**Example**: Your organization receives separate monthly invoices from three cloud
providers. In Data Studio, you upload each invoice, standardize the vendor names and service
categories, and combine them into a single “Cloud Services” table that shows all cloud
spending in a consistent format.

## Model Studio: Flow Costs Through Your Organization

**Purpose**: Visualize how costs flow from their source to the services and business
units that consume them.

Model Studio is where you build allocation models that trace technology costs through your
organization. You can:

- Add data tables as objects in your cost model
- Define drivers (like server count, FTE headcount, or transaction volume) that determine
  how costs are allocated
- Create allocations that distribute costs from one object to another based on those
  drivers
- Visualize cost flows using interactive Sankey diagrams
- Track multiple metrics (cost, budget, forecast) through the same model structure

**When you use it**: When you need to allocate shared costs, perform cost transparency
analysis, or support chargeback and showback initiatives.

**Example**: Your IT operations costs start with “Cost Source” object representing your
general ledger. You allocate these costs to “Tech Services” (like cloud hosting, database
services, email) based on resource consumption. Then you allocate from tech services to
“Applications” based on which apps use which services. Finally, you allocate from
applications to “Business Units” based on application usage, giving each business unit
visibility into their share of IT costs.

## Report Studio: Communicate Insights

**Purpose**: Create interactive reports and dashboards that make your data accessible to
stakeholders.

Report Studio is where you design the reports that end users interact with. You can:

- Build tables, charts, and KPIs from your modeled data
- Add slicers and filters so users can explore data interactively
- Create drill-through capabilities to navigate from summary to detail
- Design role-specific dashboards for different audiences
- Schedule reports for automated distribution

**When you use it**: When you need to present cost analysis to executives, provide
self-service reporting to business unit managers, or create monthly financial packages.

**Example**: You create an executive dashboard showing total IT costs by quarter with
year-over-year trends. The dashboard includes slicers for business units and cost
categories. When an executive clicks on a cost spike, they can drill down to see which
specific services drove the increase and which vendors were involved.

## Who Uses TBM Studio and Why

Different roles leverage TBM Studio to accomplish different goals:

**IT Finance Teams** use TBM Studio to:

- Track and report IT spending across the organization
- Build allocation models for chargeback and showback
- Support budgeting and forecasting processes
- Demonstrate IT value to the business

**Business Analysts** use TBM Studio to:

- Analyze cost trends and identify optimization opportunities
- Create ad-hoc reports to answer specific business questions
- Maintain data quality and resolve discrepancies
- Provide self-service analytics to stakeholders

**Administrators** use TBM Studio to:

- Manage user access and security
- Monitor data freshness and quality
- Oversee the build and deployment lifecycle
- Maintain reference data and project settings

**Developers** use TBM Studio to:

- Extend functionality through APIs and scripting
- Automate data integration workflows
- Build custom calculations and transformations
- Integrate TBM Studio with other enterprise systems

## How It All Works Together

Here’s a typical workflow that illustrates how the three studios work together:

***Month-End Close Process***:

1. **Data Studio**: Finance uploads the current month’s general ledger file. The
   transform pipeline automatically categorizes expenses, maps vendor names, and distributes
   costs across the fiscal month.
2. **Model Studio**: The monthly build runs automatically, flowing the new cost data
   through the allocation model. Server costs allocate to applications based on CPU usage;
   application costs allocate to business units based on transaction volume.
3. **Report Studio**: End users open their monthly dashboards and immediately see
   updated cost figures. Business unit managers review their allocated costs, identify
   variances from budget, and drill down to investigate unusual charges.

This automated flow saves hours of manual work each month while ensuring stakeholders
always have access to current, accurate cost information.

## Real-World Example: Cloud Cost Management

**The Challenge**: A mid-sized financial services company spends $2M annually on cloud
infrastructure across AWS, Azure, and Google Cloud. Costs are growing 20% year-over-year,
but the IT team can’t explain which business initiatives are driving the increase. Business
units complain that cloud costs are a “black box.”

**The Solution with TBM Studio**:

1. **Data Studio**: Upload monthly cloud bills from all three providers. Transform the
   data to standardize service names (e.g., “EC2,” “Virtual Machines,” “Compute Engine” all
   maps to “Cloud Compute”). Join with internal metadata to tag resources by application and
   business unit.
2. **Model Studio**: Create a cost flow from cloud providers → cloud service types →
   applications → business units. Use resource tags as allocation drivers. The model shows
   exactly how much each business unit spends on compute, storage, and network across all
   cloud providers.
3. **Report Studio**: Build dashboards for three audiences:
   - **Executives**: High-level KPIs showing total cloud spend, growth trends, and
     cost per business unit
   - **Business Unit Managers**: Detailed view of their cloud costs by application and
     service type with month-over-month comparisons
   - **IT Operations**: Technical view showing costs by resource, region, and
     optimization opportunities

**The Outcome**: The company gains complete visibility into cloud spending. They
identify that 40% of storage costs come from old development snapshots that can be safely
deleted. Business units can now see their cloud consumption and are incentivized to
optimize. IT can demonstrate the value they’re delivering and justify budget requests with
data.

## What to Learn Next

Now that you understand what TBM Studio is and how it works, here are your next steps:

- [Core Concepts](core-concepts.html): Learn the fundamental concepts that underpin TBM
  Studio—like projects, tables, metrics, and allocations—so you can navigate the platform
  confidently.
- [Quick Start Guide](qsg.html): Follow a hands-on tutorial that walks you through uploading data,
  building a simple model, and creating your first report in about 10 minutes.
- [UI Overview](tbm-navigation.html): Get familiar with the TBM Studio interface, navigation,
  and common workflows so you can work efficiently.

For role-specific learning paths, see [Learning
Paths](../learning-path/lp-admin.html "Objective: Configure, secure, optimize, and maintain TBM Studio for your organization"). If you’re ready to dive into specific tasks, Section 3 (How-To Guides)
provides step-by-step instructions organized by topic.
