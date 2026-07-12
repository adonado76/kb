---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "RLS Architecture"
breadcrumb:
  - "Concepts and Architecture"
  - "Security Model"
  - "Row-Level Security (RLS)"
  - "RLS Architecture"
source_path: "SSWRJM/studio/new-uc/concepts-architecture/security-model/rls-arch.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# RLS Architecture

Implementing RLS requires two key components: mapping tables that define user-to-data relationships, and filter rules that apply those relationships to data tables.

The Row-Level Security Project

RLS is managed through a dedicated project called Row-Level Security. This project is installed automatically when a new Apptio instance is created and applies to all projects in a domain. You access it from the Settings menu by clicking Configure Row-Level Security.

Mapping Tables

Mapping tables define which data each user can see. A mapping table must have at least two columns:

- User ID: The user’s email address, which must match their User ID in the Users table.
- Item: The value that the user is permitted to see, as it appears in the data table being secured (such as a business unit name, cost center code, or data center name).

| User ID | Business Unit |
| --- | --- |
| User ID | Business Unit |
| bob@acme.com | BU 2 |
| rachel@acme.com | BU 1 |
| rachel@acme.com | BU 3 |
| tom@acme.com | BU 1 |

In this example, Bob can see only BU 2 data. Rachel can see BU 1 and BU 3. Tom can see only BU 1. Notice that Rachel has two rows—one for each business unit she is permitted to access.

Full Access Pattern

For users who need to see all data (such as executives or analysts responsible for the entire organization), you can create a separate mapping table with a flag column instead of listing every possible value.

| User ID | Is Admin |
| --- | --- |
| User ID | Is Admin |
| sally@acme.com | Yes |
| cfo@acme.com | Yes |

You then add a formula column to the secured table that always evaluates to “Yes,” and create an RLS filter rule using OR logic: the user either appears in the standard mapping table for their specific business units, OR appears in the full-access table. This approach scales automatically when new business units are added—you do not need to update the full-access users’ entries.

Filter Logic

RLS filter rules connect the mapping tables to data tables. Each filter rule has four components:

1. Table Column: The column in the data table that contains the items to be filtered (such as the BU column in Cost Source).
1. Mapping Table: The mapping table that contains the RLS definitions (such as BU Access).
1. Mapping Column: The column in the mapping table that contains the permitted values (such as the Business Unit column in BU Access).
1. User Column: The column in the mapping table that contains user IDs (such as the User ID column in BU Access).

When multiple filter entries are defined, they use OR logic by default—if any one of the entries is true, the user can see the row. This is how the full-access pattern works: the user either matches in the standard mapping table OR matches in the full-access table.
