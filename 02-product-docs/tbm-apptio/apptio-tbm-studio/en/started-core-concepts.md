---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Core Concepts"
breadcrumb:
  - "Getting Started"
  - "Core Concepts"
source_path: "SSWRJM/studio/new-uc/getting-started/core-concepts.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Core Concepts

| Content Type | Conceptual |
| --- | --- |
| Content Type | Conceptual |
| Target Audience | New Users |
| Reading Time | 5 minutes |
| Prerequisites | None |

Before you dive into TBM Studio, understanding six core concepts will help you work more effectively. These building blocks work together to transform raw IT cost data into actionable insights for your organization.

## Projects

A project is your dedicated workspace in TBM Studio where you organize all your TBM work. Think of it as a self-contained calculation area within your organization's domain that houses everything you need for cost modeling and reporting.

Within a project, you'll find:

- Data tables with your imported and transformed information
- Cost models that show how money flows through your organization
- Metrics that calculate values like cost, budget, and forecast
- Reports that present insights to stakeholders

Your organization may have multiple projects—perhaps one for IT cost transparency, another for application costing, or separate projects for different business units. Each project keeps its data, models, and reports interlinked and interdependent.

## Tables & Data

Tables are where your data lives in TBM Studio. They contain the raw information about your IT operations and finances that will feed into your cost models.

Tables come from two sources:

Source tables are created by uploading files (like CSV or Excel) containing data from your systems—general ledger entries, cloud bills, asset inventories, or employee headcounts.

Transform tables are created from existing tables by applying operations like filtering, joining, mapping, or calculations. These transformations let you clean, enrich, and reshape your data to match the structure your models need.

Tables are organized by time period, allowing you to track changes month over month. Each table consists of columns (dimensions like "Department" or "Application") and may include numeric values that will be used in calculations.

## Models

A model shows how costs and other metrics flow through your organization. It's the engine that calculates the true cost of IT services by distributing expenses from their source to the things that consume them.

At the heart of a model are model objects —each representing a distinct layer in your cost structure, such as:

- Cost Source (where money originates, like your general ledger)
- Vendors (external providers)
- Technology Services (infrastructure components)
- Applications (the systems your business uses)
- Business Units (who ultimately consumes IT services)

Models work by creating allocations that define how costs move from one object to another. For example, you might allocate data center costs to servers based on rack space, then allocate server costs to applications based on CPU consumption and finally allocate application costs to business units based on user counts.

Drivers determine the logic for these allocations. A driver might be a simple column value (like headcount), another metric (like prior-month cost), or a formula. The model automatically calculates how costs cascade through each layer based on these rules.

## Metrics

Metrics are the measurements that matter to your organization. They define what gets calculated and tracked through your models.

1. Model metrics represent values that flow through allocations. The most common are: Cost : Actual expenses incurred Budget : Planned spending Forecast : Projected future costs You can create multiple model metrics to track different aspects simultaneously. For example, you might allocate both actual costs and budgeted amounts through the same model structure, allowing for variance analysis.
1. Calculated metrics are formulas that derive new values from model metrics or data tables. Common examples include variance (Budget minus Cost), year-to-date totals, unit costs (Total Cost divided by Transaction Count), and growth rates.

Metrics maintain formatting rules (currency symbols, decimal places) and understand whether they can be summed across time periods or organizational dimensions.

## Reports

Reports present your modeled data and calculated metrics to stakeholders in meaningful ways. They're the primary interface for consuming TBM insights.

Reports can display data as:

- Tables with rows, columns, and calculated values
- Charts and visualizations
- Model flow diagrams (Sankey diagrams) showing cost allocation paths
- Custom dashboards combining multiple views

Reports are interactive—users can filter data, drill down into details, change time periods, and export results. You control who sees what through report-level permissions and row-level security filters.

Reports can pull from both transform tables (raw or shaped data) and model objects (allocated costs), allowing you to show both source data and fully allocated results in the same view.

## Environments

TBM Studio uses three environments to manage the development lifecycle and ensure quality before changes reach end users:

Development is your personal workspace. When you check out a document to edit it—whether a data table, model, or report—you're working in your Development environment. Changes you make are local to your workspace and don't affect others until you're ready to share them.

Staging is where all team members' changes come together. When you check in a document, it moves to Staging and triggers a calculation. This is where you test and validate changes before releasing them to report consumers. All team members can see Staging to review work in progress.

Production is the live environment that end users see. Only administrators can promote projects from Staging to Production. This environment should contain only validated, tested changes. Production typically updates on a controlled schedule—daily, weekly, or monthly depending on your organization's needs.

This three-tier approach prevents errors from reaching users and provides a safe space for experimentation and development.

## How These Concepts Work Together

Here's the typical workflow showing how these concepts connect:

1. Upload data → Create source tables in your project
1. Transform data → Build transform tables to clean and structure the data
1. Build the model → Create model objects and define allocations using drivers
1. Define metrics → Set up Cost, Budget, and calculated metrics
1. Generate reports → Present allocated costs and metrics to stakeholders
1. Manage changes → Work in Development, validate in Staging, release to Production

Each step builds on the previous one, creating a complete cost transparency system.

## What's Next

Now that you understand the core concepts, you're ready to:

- Try the Quick Start Guide for hands-on practice creating your first cost model
- Explore the UI Overview to familiarize yourself with where everything lives
- Dive deeper into specific concepts in Section 4 (Concepts & Architecture): 4.2 Data Architecture for details on tables and transformations 4.3 Model Architecture for comprehensive modeling guidance 4.5 Build & Deployment Lifecycle for environment management best practices
