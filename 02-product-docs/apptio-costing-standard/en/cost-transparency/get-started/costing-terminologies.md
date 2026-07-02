---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "cost-transparency"
title: "Key Concepts & Terminology"
breadcrumb:
  - "Costing Standard"
  - "Getting started"
source_path: "cost-transparency/get-started/costing-terminologies.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Key Concepts & Terminology

Understanding the foundational concepts in IBM Apptio Costing will help you navigate
the application. Below are definitions of key terms frequently used in Costing.

**AVF (Apptio Value Framework)** - AVF introduces the core IT Financial Management (ITFM)
use cases supported by IBM Apptio. It organizes each use case around a clear problem
statement, the Costing Standard capabilities that solve it, and the key personas involved. AVF
helps teams understand where to focus, how value is delivered, and how different stakeholders
benefit from IBM Apptio Costing Standard.

**ATUM (Apptio TBM Unified Model)** - ATUM is IBM Apptio’s standardized cost model that
aligns financial, operational, and consumption data to the TBM taxonomy. It provides a
consistent framework for allocating technology costs and producing defensible, comparable
insights across organizations.

**TBM (Technology Business Management)**

TBM is an industry framework that standardizes how organizations manage, measure, and
communicate the cost, quality, and value of technology. TBM principles underpin the structure
of Apptio Costing Standard and its cost allocation methodology.

**Environment (Client / Server)** - Refers to the infrastructure hosting your Costing
Standard project. Client and Server upgrades ensure compatibility, performance, and access to
new features.

**Project** - A Project is the working environment where your Costing Standard data,
components, model, allocations, and reports are configured and maintained. When an instance of
Costing Standard has been provisioned, one of the 1st actions to take is to create the
project.

**Template**  - A Template is a gateway into pre-created content from IBM Apptio. By
selecting and setting the Template in your project, access will be obtained to out-of-the-box
content such as Components. Templates streamline implementation, promote consistency, and
maintain alignment with future upgrades.

**Component** - A Component is a modular, installable package such as Labor, Vendors,
Servers, Storage, Applications, Services, Mainframe etc. that contains master datasets
(inclusive of in-built formula logic), reference tables (sometimes editable tables),
allocation logic and pre-built reports.

**Master Data Set (MDS)** - Master Data Sets are curated datasets that serve as the
authoritative source for key documents such as Cost Source, Resource Towers, Labor, Vendors,
Assets, Applications, and Services. MDS tables normalize inputs from multiple systems to
ensure consistent allocation and reporting.

**Model** - A Model defines how technology costs are structured, transformed, and
allocated within a project. It integrates various sources of data, exposed via master data
sets, while leveraging allocation rules to calculate the total cost of ownership and unit
costs of technology. It leverages model metrics, such as OpEx Actuals, CapEx Actuals, Budget,
Forecast and others to represent distinct cost flows or analysis perspectives.

**Metric** - A Metric is a quantitative value used to measure cost, consumption, or
performance, within the Costing Standard model. Metrics such as OpEx, CapEx, CPU hours,
storage GBs, labor hours, ticket volumes, or user counts, often serve as drivers in
allocations and provide the basis for calculating unit costs and comparing technology
performance over time. Model metrics are foundational to driving the actual models; while
calculated metrics are predominantly used for reporting purposes and to set weighted values on
the allocations across the model.

**Allocation** - An Allocation is a modeling rule that defines how costs flow through
ATUM, e.g. from Labor to Resource Towers or from Servers to Applications. It makes use of
allocation keys defined at both the sending and receiving object to establish connectivity
between the objects and allows for setting a certain weighted value to drive managed and
consumptive allocations. Allocations distribute cost based on drivers such as labor hours,
consumption, units, or configuration values.

**Customization** - A Customization is any change made to the stock Costing Standard
model, datasets, or reports. Customizations allow organizations to tailor Costing Standard to
their environment but may require attention during upgrades.

**Upgrade** - An Upgrade brings your project or components up to the latest Costing
Standard version. This may include updated allocations, revised reports, bug fixes, new
component features, or TBM taxonomy updates.
