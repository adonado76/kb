---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "AI TCO Getting Started"
breadcrumb:
  - "Costing Standard"
  - "Other Solutions"
  - "AI TCO"
source_path: "cost-transparency/reports/aitcosol-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# AI TCO Getting Started

The AI TCO & Usage solution enables organizations to gain clear, defensible
visibility into the total cost of ownership and usage of AI across models, solutions, and
business units. It is designed to support responsible AI adoption by combining financial,
operational, and usage data into a single analytical framework. Before implementation,
organizations should evaluate whether to deploy this solution within an existing project or
create a dedicated project specifically for AI TCO & Usage, depending on governance, data
separation, and reporting needs.

## Components Install

The AI TCO & Usage solution is introduced through four components, installed in a prioritized
sequence. Two components are purpose-built for AI TCO & Usage, and two are existing components
that must be upgraded (or changes to master data needs to be added) to enable AI-specific
functionality.

**AI TCO & Usage**

The **AI TCO & Usage** component should be installed
first, as it establishes the AI-specific master datasets, models, metrics, and workbenches required
to calculate AI cost and usage outcomes.

**AI TCO & Usage Reporting**

Install the **AI TCO & Usage Reporting**
component, which delivers the AI report collection, including the primary AI TCO & Usage report
and the AI Cost Model report used for allocation traceability.

Note: These components are available with templates v120 or above

**AI TCO & Usage NX Reports (Additional Component)**

Provides predefined NX
reports based on AI cost and usage data for analysis across services, workloads, and time
periods.

Use this component when:

- You need standard AI cost and usage reports
- You want to review cost and usage trends
- You require consistent AI reporting

## Prerequisite

**CTF– Cost Source**

If this component is already installed, it must either be updated (fields are auto added on
upgrade) or configured to support AI-specific enhancements. This includes adding **AI Cost
Percentage** and **AI Amount** fields to the Cost Source Master Data, enabling accurate
AI cost attribution and visibility of AI spend as a percentage of total IT spend.

**CT Apps– Services**

Similarly, if this component is already installed, it must either be updated (fields are auto
added on upgrade) or configured to support AI-specific enhancements. This includes **adding
AI Solution classification, AI solution type, and AI user counts**, which extends Business
Services with AI-specific attributes. These fields are essential, as AI reporting is driven
from Business Services marked as AI Solutions.

## Common Sources of Data

AI TCO & Usage data is typically sourced from a combination of cloud billing platforms,
AI service providers, and internal enterprise systems. Cloud providers supply AI
infrastructure and platform costs, including compute, storage, and managed AI services. AI
model and platform vendors contribute usage metrics such as token consumption, inference
requests, licenses, and subscription charges. Labor and vendor systems provide personnel and
external service costs associated with AI development, operations, and governance. Business
services metadata and organizational hierarchies are used to associate AI solutions with
applications, services, and consuming business units, enabling end-to-end AI cost and usage
analysis.

**Datasets**

The solution introduces AI-specific master datasets through the AI TCO & Usage component
and extends existing Cost Source and Business Services master data to support AI cost
attribution, usage tracking, and solution-level analysis. Configuration relies on populating
AI cost percentages, AI solution attributes, and usage-related fields to enable accurate
modeling and reporting.

**For more details on how to configure, go** [here](ai-tco-configguide.html)
