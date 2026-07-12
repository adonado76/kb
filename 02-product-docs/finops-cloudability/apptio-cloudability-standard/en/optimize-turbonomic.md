---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Turbonomic"
breadcrumb:
  - "Optimize"
  - "Turbonomic"
source_path: "SSVCLNQ/product/turbonomic.html"
images:
  - "03-media/apptio-cloudability-standard/turbonomic.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Turbonomic

## Overview

Turbonomic is an Application Resource Management (ARM) solution, with an application-driven approach that continuously analyzes applications' resource needs and generates fully automatable actions to ensure applications always get what they need to perform. It runs 24/7/365 and scales with any complex environments. To perform Application Resource Management, Turbonomic represents your environment holistically as a supply chain of resource buyers and sellers , all working together to meet application demand. By empowering buyers (such as VMs) with a budget to seek the resources that applications need to perform, and sellers (such as hosts) to price their available CPU, memory, storage, and other resources based on utilization in real time, Turbonomic keeps your applications in an optimal state.

Turbonomic discovers and monitors your application environment through targets across cloud and Kubernetes environments. It then performs analysis, anticipates risks to performance or efficiency, and recommends actions to avoid problems before they occur.

Combine Cloudability and Turbonomic to give your organization the most comprehensive FinOps solution enabling infrastructure and application teams to maximize business outcomes across cloud and Kubernetes. Integrating Turbonomic with Cloudability will allow for the surfacing of additional optimization information and recommendations from Turbonomic directly within Cloudability.

Before you start

To view the Turbonomic dashboard, make sure that Turbonomic is configured in Cloudability.

Turbonomic Integration - Setup

## How to access the dashboard

To access the Turbonomic dashboard, open the Cloudability home page, and from the left navigation menu, select Optimize > Turbonomic to view optimization information and recommendations from Turbonomic.

The Turbonomic dashboard displays following information for Cloud:

- Necessary Investment s : The total rolled-up cost of all the necessary investments from Turbonomic that are displayed in the Necessary Investments Chart.
- Necessary Investments Chart: This chart shows the cost of executing all the pending actions that Turbonomic identifies as a result of its analysis. For example, if some workloads risk losing performance, Turbonomic might recommend scaling up actions for the virtual machine to increase resources. The Necessary Investments chart shows how these actions translate to an increase in expenditure. The projected amounts include on-demand costs for VMs. Click “ Show all ” at the bottom of the chart to see a breakdown of cost by action/entity type and entity. By default, the actions are shown in order of largest amounts so you can easily identify which ones will incur the highest costs. For example, you can see the cost of executing all Scale actions on the virtual machines included in the chart's scope, and the cost for individual virtual machines. To display a filtered view of the actions list, click an action type (for example, Scale Volumes) in the ring chart or legend and click on "View in Turbonomic" . This opens up Turbonomic UI in a separate tab in your browser.
- Potential Savings: The total rolled-up cost of all the potential savings from Turbonomic that are displayed in the Potential Savings Chart.
- Potential Savings Chart: This chart shows potential savings in your cloud expenditure, assuming you execute all the pending actions that Turbonomic identifies as a result of its analysis. For example, if there are pending actions to scale a virtual machine, which result in reduced monthly costs, the Potential Savings chart shows the reduced cost that would result from those actions. This chart also tracks discount optimization actions. VM scaling actions may result in freed up capacity on a discounted instance type, which can now be applied to a different VM. Discount optimization actions reflect the potential savings resulting from reassigning the capacity to a different VM. These actions are not executed by Turbonomic users. They reflect capacity reassignment performed by your cloud provider. The projected amounts include on-demand costs for VMs. Click “ Show all ” at the bottom of the chart to see a breakdown of savings by action/entity type and entity. By default, the actions are shown in order of largest amounts so you can easily identify which ones will introduce the most savings. For example, you can see the savings you would realize if you execute all Scale actions on the virtual machines included in the chart's scope, and the savings for individual virtual machines. To display a filtered view of the actions list, click an action type (for example, Scale Volumes) in the ring chart or legend and click on “ View in Turbonomic" . This opens up Turbonomic UI in a separate tab in your browser.

## Frequently Asked Questions

Will views work on this page?

Cloudability Views are not supported on this page

How does "View in Turbonomic" work?

When you click on this option, it opens up Turbonomic instance configured with your Cloudability instance in a new tab. However, there is no single sign-on capability and the user will need to login to the Turbonomic instance using their credential
