---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "User Management"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "Manage Users and Permissions"
  - "User Management"
source_path: "SSWRJM/studio/new-uc/howtoguides/manage-users-permission/manage-up-intro.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# User Management

| Content Type: | How-To Guide |
| --- | --- |
| Content Type: | How-To Guide |
| Target Audience: | Administrators |
| Prerequisites: | Admin or Power User role, access to Enhanced Access Administration |
| Related Sections: | Section 3.4.2 (Access Control), Section 6.2 (User Management Reference) |

## Introduction

User management is fundamental to controlling who can access TBM Studio and what actions they can perform. This section covers the day-to-day tasks administrators need to set up and maintain user access, including creating users, assigning roles, and configuring custom roles for specialized needs.

TBM Studio uses Enhanced Access Administration (also known as Frontdoor) as the central interface for managing users and roles across all Apptio applications. Users are defined at the domain level, and their access to specific projects and features is controlled through role assignments.

## Understanding Default Roles

TBM Studio provides several default roles that cover common access patterns. Understanding these roles helps you assign appropriate access levels and determine when custom roles are needed.

| Role | Description | Typical Use |
| --- | --- | --- |
| Role | Description | Typical Use |
| Admin | Full administrative access to all features including user management, project configuration, and all data. | TBM Administrators, system owners, security administrators. |
| Power User | Can configure models, create reports, upload data, and access development environments. Cannot manage users or domain settings. | TBM Architects, IT Finance analysts building models and reports. |
| Business User | View access to production reports and data. Can interact with editable tables if granted. No configuration access. | Business stakeholders, executives, department managers consuming reports. |
| Analyst | View access plus ability to create personal reports. Has Edit Personal Reports permission. | Business analysts who need to create ad-hoc reports for personal use. |
