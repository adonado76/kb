---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Edit Permissions"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Editable Tables in Reports"
source_path: "studio/new-uc/reference/report-studio-reference/edit-permissions.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Edit Permissions

Permissions control who can perform specific operations on the editable table component.

**Row-Level Permissions**

Configure operation permissions in the Permissions section of the Editable Tables ribbon:

|  |  |  |
| --- | --- | --- |
| **Permission** | **Controls** | **Default** |
| Add Row Permission | Who can add new rows | Everyone |
| Edit Row Permission | Who can modify existing rows | Everyone |
| Delete Row Permission | Who can remove individual rows | Everyone |
| Duplicate Row Permission | Who can duplicate rows | Everyone |
| Publish Row Permission | Who can publish changes | Everyone |
| Delete All Rows Permission | Who can delete all rows at once | Admin and Partner |
| Download Permission | Who can download the table | Everyone |
| Upload Permission | Who can upload data | Everyone |
| Show History Permission | Who can view change history | Everyone |

For each permission, select Everyone or Selected Roles and specify the allowed roles.

**Row-Level Security (RLS) Integration**

When RLS is enabled on the underlying editable table:

- Users only see rows matching their security dimension (e.g., their cost center)
- Write access is restricted to visible rows only
- Hidden rows are preserved during publish operations
- RLS applies in addition to report-level permissions

**Dynamic Edit Disabling**

Use the Disable Edits field to conditionally disable editing based on dynamic conditions:

Example: `{$CurrentUser:Users.ID}=ddavis@ABCCompany.com`

This expression disables editing for the specified user. You can use any dynamic text expression
that evaluates toevaluates true or false.

**Parent topic:** [Report Components: Editable Tables in Reports](../../../../studio/new-uc/reference/report-studio-reference/report-component-editable-components.html)
