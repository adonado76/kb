---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "technology-integration"
title: "Installing Components"
breadcrumb: []
source_path: "technology-integration/install-_component.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Installing Components

To enable the integration of IBM Turbonomic Action data with IBM Apptio, three new components have been developed. These components are currently behind the Beta Flag in TBM Studio, located under the Project Tab within Enable Features. As a result, only users with Apptio Admin access can make them visible in the Available section of the Components Tab at this stage.

![](../../resources/images/ct_images/trb-comp.jpg)

![](../../resources/images/ct_images/trb-comp-1.jpg)

Note: Ensure that the Components Version in Project Settings is set to Version 120. After the
components are installed, you can revert the Component Version to the desired or previous template.

## Hybrid IT Optimization component

The first component to install is the NEW  *Hybrid IT Optimization*  component. This
component introduces a set of new Master Datasets, metrics (both modeled and calculated), and model
allocations. These elements are designed to support an architecture that enables modeling and
reporting on Hybrid IT Infrastructure optimizations.

As this component is intended for existing customers, it may require customization of certain
table lookups, metrics, and allocations to align with the existing Apptio model within the new
Hybrid IT Optimization framework.

For more detailed information about the component, refer to the description provided when
navigating to the component in the system.

## Turbonomic – Actions component

While the first component,  *Hybrid IT Optimization*  , establishes the framework, the
second component, Turbonomic – Actions, installs the necessary Tables and Master Datasets to enable
seamless integration of  *IBM Turbonomic Action*  data—via Datadrop—into IBM Apptio’s TBM
Studio.

Note: The  *Hybrid IT Optimization*  component must be installed first, as the Turbo Actions
Master table relies on lookup dependencies to three editable tables included with the  *Hybrid IT
Optimization*  component.

For more details on the content of this component, refer to the description provided when
navigating to the component.

## Hybrid IT Optimization - Reporting component

The third and final component is the  *Hybrid IT Optimization - Reporting*  component. This
component installs two reports that visualize actionable insights from the integration. It provides:

- IT Finance and the Technical Service Owner (IT Provider) with a Potential and Realized Savings
  view from a cost perspective.
- Solution/Application Owner (IT Consumer) with a Potential and Realized Savings view from a
  charge perspective.

For more details on the content of this component, refer to the description provided when
navigating to the component.

**Parent topic:** [Costing Standard](../home.html)
