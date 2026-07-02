---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Essential TBM Studio concepts"
breadcrumb: []
source_path: "studio/admin/essential-tbmstudio-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Essential TBM Studio concepts

Applies to: TBM Studio 12.0 and later. In TBM Studio, you organize your work in projects.
Within a project, you collect and transform data into data sets, create models, add objects to the
models, assign data sets to the objects, allocate costs from one object to another, and summarize
the results in one or more reports. Instances, domains, and projects organize your work:

- **Instance** — An Apptio SaaS (Software as a Service) that houses customer domains and
  projects. Within an instance, there may be multiple domains. Within a domain, there may be multiple
  projects.
- **Domain** — The Apptio environment established for a specific organization. Your
  organization has been assigned a domain that contains all your projects.
- **Project** — The calculation area within an Apptio domain in which models and reports are
  created. A project contains data sets, metrics, and reports that are interlinked and
  interdependent.

The basic workflow for building a project includes:

- Create tables from imported data.
- Create a model to show the flow of data through the organization. The most frequently used data
  is cost. A model calculates the cost for the services offered by your organization.
- Create model metrics to calculate different values. For example: cost, budget, forecast.
- Build the model by allocating cost from one table to another. Source tables might be a general
  ledger or a web services bill. Target tables might be applications and business units.
- Define calculated metrics based on the modeled metrics and data tables. A common calculated
  metric subtracts actual costs from planned costs.
- Create reports to present the data calculated in the models.

Your Apptio environment contains one or more projects that organize your modeling and reporting
work. Projects consist of the following elements:

- **Data tables** — Data tables contain your project data. You can upload data
  from several sources, including Excel files and flat files delimited by commas, tabs, pipes, or
  other separators. Common data sources include a general ledger file and a web services bill. For
  more information, see [About Data Studio](../data_studio/data-transform-chapter-title-page.html "Applies to: TBM Studio 12.0 and later").
- **Data model** — A data model is a logical and graphical representation of
  cost, utilization, service levels, or other data relevant to your IT services. The structure of the
  data model in a project determines the type of information that can be displayed in the reports for
  that project. For more information, see [About Data Studio](../data_studio/data-transform-chapter-title-page.html "Applies to: TBM Studio 12.0 and later").
- **Metrics** — Metrics are calculations that define value. There are two types of metrics:
  - **Modeled metrics** — A data model is itself a metric. A model calculates a single
    measurement such as cost or budget. Data models are sometimes referred to as modeled metrics.
  - **Calculated metrics** — A calculated metric uses a formula to derive a value
    from modeled metrics. For example, you could create a calculated metric called Budget\_Variance that
    subtracts the Cost model metric from the Budget model metric. For more information, see [Create and manage metrics](../model_studio/introduction-to-metrics.html "Applies to: TBM Studio 12.0 and later").
- **Reports** — A properly structured data model will enable you to create a
  variety of useful reports at a granularity that meets your reporting requirements. For more
  information, see [TBM Studio About Report Studio](../reports/report_studio_title_topic.html).

- **[TBM Studio About Report Studio](../../studio/reports/report_studio_title_topic.html)**
- **[Report layout](../../studio/reports/report-layout.html)**  
  **Applies to**: TBM Studio 12.0 and later
