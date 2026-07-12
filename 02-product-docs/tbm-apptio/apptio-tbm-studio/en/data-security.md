---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Data Security"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Work with Data"
  - "Data Security"
source_path: "SSWRJM/studio/new-uc/howtoguides/work-with-data/data-security.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Data Security

Content Type: How-To Guide

Target Audience: Administrators, Business Analysts

Prerequisites: Understanding of transform tables, user management basics

Related Sections: Section 4.4 (Security Model), Section 6.3 (Security & Compliance)

## Introduction

Row-level security (RLS) enables you to control which rows of data each user can see in tables and reports. Rather than restricting access to entire tables, RLS allows you to filter data at a granular level based on the user viewing the information. For example, a regional manager might only see cost data for their business unit, while a finance director sees data across all units.

This section provides practical, step-by-step guidance for implementing RLS at the data layer. For conceptual understanding of how security works across TBM Studio, see Section 4.4: Security Model . For administrator-level security configuration and compliance considerations, see Section 6.3: Security & Compliance .

Key Concepts

- Row-Level Security (RLS): A data filtering mechanism that restricts visible rows based on the current user. Previously called "View Filters" in TBM Studio 11.
- Mapping Table: A table that defines which users can access which data items. Contains user IDs and the items they are permitted to view.
- Row-Level Security Project: A dedicated system project where mapping tables are stored. This project is automatically created when a new Apptio instance is installed and serves all projects in the domain.
- RLS Step: A pipeline step added to transform tables that references mapping tables to apply security filters.

## Understanding the RLS Architecture

Before implementing RLS, it helps to understand how the components work together:

1. Mapping Tables define user-to-data relationships. They live in the dedicated Row-Level Security project and map user IDs to the specific data values (like business units, cost centers, or regions) each user can access.
1. RLS Steps are added to transform pipelines. Each step references a mapping table and specifies which column in your data table should be filtered based on the mapping.
1. At runtime , when a user views a table or report, the system compares their user ID against the mapping table to determine which rows to display.
