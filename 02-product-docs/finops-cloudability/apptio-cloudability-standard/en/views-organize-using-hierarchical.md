---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Organize Views using Hierarchical Views"
breadcrumb:
  - "Administration"
  - "Create and Manage Views"
  - "Organize Views using Hierarchical Views"
source_path: "SSVCLNQ/admin/hierarchical-views.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Organize Views using Hierarchical Views

## Overview

What are Hierarchical Views?

Hierarchical Views (HV) organize Views into a parent-child structure. In this hierarchy, a View can contain other Views — called child Views — which can themselves have additional children, forming a nested structure.

A View that contains child Views is called a View Group. Its filter condition is automatically inherited from its children, representing the union of all their filter statements. This means you can manage a View Group’s logic simply by adding or removing child Views—no manual editing of filter criteria required.

Example:

- Marketing View → Filter: Tag = “Marketing”
- Engineering View → Filter: Tag = “Engineering”
- All Departments (parent) → Filter automatically becomes “Marketing OR Engineering”.

| Level | Example Name | Filter |
| --- | --- | --- |
| View Group | All Departments | (inherits all below) |
| Child View 1 | Marketing | Tag = “Marketing” |
| Child View 2 | Engineering | Tag = “Engineering” |

Benefits of Hierarchical Views

1. Simplified Filtering: Child filters automatically roll up to parent views, eliminating duplicate filter management.
1. Streamlines User Access Management: Assigning a user to a parent View (View Group) automatically grants access to all its child Views — and any descendants further down the hierarchy.
1. Organizational Clarity: View your cloud spend in a structure that mirrors your real-world organization.
1. Automatic Create and Sync with Hierarchical Business Mapping (HBM): Hierarchical Views are automatically generated from a Hierarchical Business Mapping (HBM), saving time and reducing manual setup. Each value in the mapping file becomes a View, and the file defines how Views roll up into View Groups. Once created, the HV structure stays in sync and is automatically updated whenever the HBM changes.

## Setting up Hierarchical Views

Create a Hierarchical View

1. Navigate to Organize > Views.
1. Select New Hierarchical View . The New Hierarchical View dialog opens.
1. Select a Hierarchical Business Mapping to be used for defining the views in the hierarchy.
1. Click Add to create the view hierarchy.

This will automatically create views matching the HBM definition. This may take a few minutes to complete.

Manage Hierarchical Views

You can edit and share views within the hierarchy, or delete the entire hierarchy.

You cannot edit the filter conditions of views within a Hierarchical View (HV), nor can you delete individual Views. Both the views and their filter conditions are controlled by the Hierarchical Business Mapping (HBM) associated with the HV.

Changing the privacy permissions of the entire Hierarchical View

Views authors can change the permissions (increase or decrease) of the view hierarchy. Here's how:

1. Navigate to Organize > Views.
1. Click the ellipsis (…) icon on the row of the HV root node and select Edit . The Edit Hierarchical View Group panel is displayed.
1. Change the permission between ‘Entire Organization’ and ‘Users & Groups’. Note: Changing the privacy mode to Entire Organization, when Saved, will remove all existing user sharing assignments for all nodes in the hierarchy. Proceed with caution.

Editing a Hierarchical View

Users with view access can edit the sharing for a Hierarchical View. Follow the steps below:

1. Navigate to Organize > Views.
1. Click the ellipsis (…) icon on the row of the view you want to edit and select Edit . The Edit Hierarchical View Group panel is displayed.
1. Select the Users & Groups to share your view with specific users. Use the Shared With dropdown to select specific Users, User Groups or Entrap ID Groups to share the View with. Note: When users are assigned a view, they automatically inherit access to all child views as well. You can see users who have inherited access to the current view in the Inherited View Permission section. When assigned, users can not see any data until they have the ViewsFeatureFullAccess permission. For more information, visit Managing user permissions and roles =

Deleting a Hierarchical View

To delete a hierarchical view, follow the steps below:

1. Navigate to Organize > Views.
1. Click the ellipsis next to the root node and select Delete
1. Confirm that you wish to delete the imported View Group. Note: You cannot delete individual Views within a Hierarchical View (HV); only the root node can be deleted, and only by a user who has access to the root node. However, the root node cannot be deleted if any of its child Views are shared with other users. To proceed with deletion, you must first remove all user access to the entire HV. To remove all sharing access: Edit the root node and set its sharing mode to Entire Organization, then click Save. Re-edit the root node and change the sharing mode back to Users & Groups, then Save again. This process should clear all existing user access, allowing you to delete the root node.
