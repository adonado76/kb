---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Environments"
breadcrumb:
  - "TBM Studio"
  - "Getting Started"
  - "UI Overview"
source_path: "studio/new-uc/getting-started/environments.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Environments

TBM Studio uses three environments to support your development workflow.

## Development Environment

**Purpose:** Your personal workspace for editing and testing

**Key points:**

- Active when you have documents checked out
- Changes are local to your workspace
- Other users’ Development environments are listed if they have documents checked out
- You can view other users’ Development environments if you have appropriate
  permissions

**When to use:** Making changes to tables, models, or reports

## Staging Environment

**Purpose:** Shared environment where all user changes are aggregated

**Key points:**

- Active when you have no documents checked out
- Contains all checked-in changes from all users
- Used for testing and validation before production
- Default view for most development work

**When to use:** Reviewing integrated changes from multiple users

## Production Environment

**Purpose:** Live environment for end users and reporting

**Key points:**

- Only accessible to administrators for promotion
- View-only access for end users
- Contains stable, tested configurations
- Promoted from Staging by administrators

**When to use:** Viewing the current live version available to end users

**To switch environments:** Use the **Environment** dropdown in the toolbar and
select Development, Staging, or Production.

**Parent topic:** [UI Overview](../../../studio/new-uc/getting-started/tbm-navigation.html)
