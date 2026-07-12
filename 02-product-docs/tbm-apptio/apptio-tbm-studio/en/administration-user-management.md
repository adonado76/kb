---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "User Management"
breadcrumb:
  - "Administration"
  - "User Management"
source_path: "SSWRJM/studio/new-uc/admin/user-management.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# User Management

Content Type: How-To / Reference

Target Audience: Administrators

Prerequisites: Admin role, access to Access Administration

User management in TBM Studio involves creating and managing user accounts, assigning roles, and controlling access to projects and features. The primary tool for user management is Enhanced Access Administration (Frontdoor).

## Understanding Roles and Permissions

Roles determine what actions users can perform within TBM Studio. Each user is assigned to one or more roles, and the combined permissions from all assigned roles define their access level.

Default System Roles:

| Role | Capabilities |
| --- | --- |
| Role | Capabilities |
| Admin | Full access to all features including user management, project settings, domain settings, and all TBM Studio functions. Can create and close branches. |
| Power User | Access to TBM Studio mode for building models, creating reports, and configuring data pipelines. Cannot manage users or domain settings. |
| Business User | View-only access to reports and dashboards. Can interact with editable tables if configured. Cannot access TBM Studio mode. |

Note: Custom roles can be created to provide granular permission control. Contact your system administrator to set up custom roles tailored to your organization.

## Managing User Accounts

User account management is performed through Enhanced Access Administration (Frontdoor). This centralized interface allows administrators to create accounts, assign roles, and manage access across Apptio applications.

To access user management:

1. Click the Settings icon in the upper-right corner.
1. Select Access Administration .
1. Navigate to the Users tab to view and manage user accounts.

## User Properties

Each user account has properties that control their experience in TBM Studio. Users can modify some of these properties themselves through the My Account dialog.

| Property | Description |
| --- | --- |
| Property | Description |
| Email | The user's login identifier. Cannot be changed by the user. |
| Full Name | Display name shown in the user list and activity logs. |
| Current Role | Active role determining permissions. Users may switch between available roles. |
| Currency | Default currency for reports. User preference overrides project settings. |
| Locale | Number formatting preference (e.g., US: 12,345.67 vs Germany: 12.345,67). |

## Controlling Project Visibility

Project visibility controls which roles can see and access specific projects. This allows you to restrict access to sensitive or development projects.

To configure project visibility:

1. Navigate to Settings > Access Administration .
1. On the Applications tab, locate your project.
1. Click Edit Visibility to select which roles can access the project.
1. Click Save , then Show to make the project visible.
