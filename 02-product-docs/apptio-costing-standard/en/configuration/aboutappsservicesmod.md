---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "About the Applications and Services Module configuration"
breadcrumb: []
source_path: "configuration/aboutappsservicesmod.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# About the Applications and Services Module configuration

The Applications and Services Module is used to allocate the IT Resource Towers costs
into the associated infrastructure and ultimately into the Applications and Services table. The
resulting reports can be used to gain insights into the Application and Service Portfolio spend. The
Applications and Services Module is a prerequisite for the Business Units module. To configure the
Applications and Services Module, install the CT Apps components.

Applies to: Costing Standard on TBM Studio 12.0 and later

## Customized

Unlike the Costing Standard Foundation module, the Applications and Services module often is
customized to match the data available in an organization. The descriptions of the Applications and
Services module data and configuration should be taken as one way to configure the components. How
you end up configuring the components may be different.

## Configuration Requirements for the Applications and Services Module

The Costing Standard Foundation (CTF) Module is a prerequisite for the Applications and Services
Module. Once the CTF Module installation is complete and validated, you can choose to get started
with the Applications and Services Module by simply allocating portions of the IT Resource Tower
spend directly to the Applications Master Data table based on basic rules. However, as you obtain
more infrastructure data and relationships are available to defensively allocate spend from
infrastructure into the supporting applications, you likely will choose to begin bringing the data
into the application and slowly providing a more defensible cost model.

## Components in the module

The Applications and Services components are not installed automatically when you create a
Costing Standard project. You must install each component separately. You can install any
combination of the components. They are not depended on each other.

The CT Applications and Services Module includes the following components:

- CT Apps - Applications
- CT Apps - Communication
- CT Apps - Date Centers
- CT Apps - End User Devices
- CT Apps - Mainframes
- CT Apps - Network
- CT Apps - Servers
- CT Apps - Services component
- CT Apps - Service Desk component
- CT Apps - Storage component

| If you modified this non-master file: | You must append the data to this master file: |
| --- | --- |
| IT Resource Tower List | IT Resource Tower Master Data |
| Servers Utilization Targets | Servers Master Data |
| Storage Utilization Targets | Storage Master Data |
| Storage Devises Utilization Targets | Storage Devices Master Data |

## Install the components

You install the Applications and Services Module components following the same steps used for
installing the CTF Module components. The order in which you install the components does not
matter.

1. Click the Project tab.
2. Click Components in the Ribbon.
3. Click one of the CT components.
4. Click Install.
5. Click View All Components.
6. Repeat Steps 4-6 for the remaining CT components.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
