---
source_system: "apptio-costing-essentials"
practice: "tbm"
language: "en"
doc_type: "acm-workbench.html"
title: "Costing Essentials Workbench"
breadcrumb: []
source_path: "acm-workbench.html"
images: []
capability_ids: []
last_updated: "2026-02-27"
summary: ""
---
# Costing Essentials Workbench

Apptio provides the ability to perform a variety of reference and transactional data
updates which are common across most organizations and provide increased value & visibility from
the solution. In many cases, source system data may not contain all necessary information to drive
the allocations and reporting in your Costing Essentials solution.

The Workbench in the Costing Essentials solution offers an intuitive interface, empowering
designated users to enrich and maintain their data effectively. It features editable tables,
enabling users to address data gaps and refine allocation mappings.

The access to the Workbench is governed by your organization’s permissions, and not all users may
have the requisite access.

## Detailed Mapping of Reports

Each specific mapping report, such as Vendor Mapping or Labor Mapping, is structured into two
main tabs:

## Data Enrichment

This section permits users to update information or enter missing information. For example, in
Labor Mapping, users can edit fields like Team, Role, and Employee Type for each Labor ID. However,
adding new rows is not permitted in the Data Enrichment tables and the missing information should
come from the source system (e.g., HR system of record).

## Data Mapping

This section allows users to allocate or apportion costs to one or more solutions, products, or
business units. For instance, in Vendor Mapping, a user can allocate a vendor’s cost, such as that
of SAP, to multiple offerings like SAP Financial Accounting and SAP Production Planning. This is
achieved using the Weighting column.

Example:

- To apportion 60% of SAP Vendor cost to SAP Financial Accounting and 40% to SAP Production
  Planning
- Right-click on the SAP Vendor row and select 'Duplicate Row'.
- Enter the Solution Type, Solution Category, and Offering IDs for both rows. The Offering names
  should auto-populate.
- Input '0.6' in the Weighting column for the SAP Financial Accounting offering and '0.4' for the
  SAP Production Planning offering.

**Parent topic:** [Costing Essentials](home.html)
