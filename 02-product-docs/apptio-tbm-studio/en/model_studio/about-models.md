---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "model_studio"
title: "About models"
breadcrumb: []
source_path: "model_studio/about-models.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# About models

Applies to: TBM Studio 12.0 and later

A data model is a logical and graphical representation of the flow of data relevant to the cost,
budget, utilization, service levels, consumption, or other metrics of your IT services. A sample
model is shown in the following image.

![](../../resources/images/studio_images/studioimages/studio/stu577.png)

In TBM Studio, a model usually is assigned several metrics, where a metric is a value. Metrics
show how a wide range of financial or operational data relate to the cost and performance of the
products and services that IT provides to the business.

For example:

- A model could represent total monthly IT costs, with other metrics representing various cost
  centers within the IT organization such as hardware, software licenses, and labor. The preceding
  image represents the Cost metric.
- An availability metric could contain relevant data and relationships that represent the up-time
  of services or the underlying infrastructure that supports them.
- A utilization metric could represent the CPU, network, I/O, or disk utilization across a server
  farm or set of data centers.
- A volume or consumption metric could represent the use of various IT services or underlying
  infrastructure by services or business units.

## Steps to build a model

Before you can build a model, you must upload data tables into the application. For information
on uploading data, see [Data acquisition and transformation](../data%20studio/about-data-transforms.htm "(Opens in a new tab or window)").

After you have uploaded the data, there are four key steps to build a model.

1. Add a Model step to the transform pipeline of each table that will be part of the model.
2. Add drivers to the source tables at the bottom of the model.
3. Allocate value from the source tables to the target tables higher up in the model.
4. Build model reports to help analyze the data.

## Model views

There are three ways to view a model:

- When building a model, you will work with an individual table and its drivers and allocations.
  The view uses a Sankey diagram like the one shown in the following image. You display the model by
  clicking the model step in a table transform pipeline.

  ![](../../resources/images/studio_images/studioimages/studio/stu573.png)
- When you want to trace the flow of a metric through a model, you can use the **Modeled
  Metric** view like the one shown in the following image:

  ![](../../resources/images/studio_images/studioimages/studio/stu575.png)
- When you want to see a selected set of tables displayed in tiers, you can use a model report
  like the one shown in the following image. In the example below, the tiers are Financials, Cost
  Pools, Infrastructure, and Services.

  ![](../../resources/images/studio_images/studioimages/studio/stu576.png)

## Sankey diagram

The individual and tier views of the model use a Sankey diagram. In the diagram, value flows from
left to right. The width of the allocation lines is proportional to the value. The Sankey diagram
ensures a consistent layout for all models.

Watch this demo video from Apptio Education Services: [Model Studio: Sankey
Layout](https://community.apptio.com/videos/1484 "(Opens in a new tab or window)"). Or, browse [all Apptio videos](https://community.apptio.com/docs/DOC-7714 "(Opens in a new tab or window)").

## Tables and allocations: building blocks of a model

Tables include data about operations, finances, or organizational entities in an organization.
Tables can be added to a model by adding a Model step to the table transform. Typical tables include
data for servers, networks, applications, GL (general ledger), facilities, data centers, email, and
business units.

Allocations determine the flow of value between tables. In models, allocations are represented by
lines drawn between the tables. In the preceding image, there are allocations from the Cost Source
Actuals table to the Labor Actuals, Facilities Actuals, and Fixed Assets Actuals tables.

## One model, multiple metrics

There is one model per project, but a model can have more than one model metric. Metrics are
calculations that define an aspect such as cost, budget, or quantity. When viewing a model, you can
switch the metric displayed using the field at the top of the model pane as shown in the following
image. For information on defining metrics, see [Metrics](introduction-to-metrics.htm "(Opens in a new tab or window)").

![](../../resources/images/studio_images/studioimages/studio/stu574.png)
