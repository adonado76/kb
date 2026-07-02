---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "About the Costing Standard Foundation Module configuration"
breadcrumb: []
source_path: "configuration/aboutmoduleconfig.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# About the Costing Standard Foundation Module configuration

When you create a Costing Standard project, the Costing Standard Foundation module is
installed.

## Introduction

The module is based on the cost model shown in Figure A below. In general, value is brought into
the model at the Cost Source object level. To facilitate reporting on labor and fixed assets, the
value is allocated to the Labor, Fixed Asset Ledger, and Other Cost Pools objects. To facilitate
reporting based on IT resource towers, the value is aggregated into the IT Resource Towers object.
This model serves as the foundation for the other two modules in the Costing Standard application:
Applications and Services, and Business Units.

![](../../resources/images/ct_images/6834_1.png)

## Configuration steps

To provide the foundation metrics, calculation models, and reports for Costing Standard, you will
perform the following steps:

- Create the Costing Standard project
- Configure time for the project
- Load data tables into the application
- Add columns to the tables to prepare them for mapping to the master data tables
- Append and map the tables to the master data tables

## Roles

Users that will be accessing the Costing Standard home page for the purpose of viewing the
reports should be assigned to the View Only role. They cannot be assigned to the Project Manager or
Business Unit Owner roles.

Users that will be configuring the application will need to be assigned to the Admin role.

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
