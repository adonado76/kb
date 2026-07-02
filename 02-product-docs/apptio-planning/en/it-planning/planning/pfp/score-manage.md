---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Manage Score Configuration"
breadcrumb: []
source_path: "it-planning/planning/pfp/score-manage.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Manage Score Configuration

◆ Applies to: Apptio Planning applications with [Project Financial Planning](gs-project-financial.html "◆ Applies to: Planning with Project Financial Planning."). The tasks below require you to
license Project Financial Planning. To enable Project Financial Planning features, see [Edit the Company
Profile](../edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning.").

The tasks below can only be performed by users assigned to the Admin or Budget Process Owner
roles. For additional information on roles, see Frontdoor permissions and roles.

|  |  |
| --- | --- |
| camera icon | Watch this video from Apptio Education Services: [Configuring Reference Data: Project Financial Planning Dimensions](https://community.apptio.com/videos/1995 "(Opens in a new tab or window)").  Or see all [Apptio Planning video and training resources](https://community.apptio.com/viewdocument/apptio-products-video-catalog?CommunityKey=1bdb1f0b-9524-43d4-b987-5d2b8595eebf "(Opens in a new tab or window)"). |

## Manage Score

The Score data table defines the Score value applied to projects when the **Enable Project
Auto-Scoring** option has been enabled. See [Edit the Company Profile](../edit-company-profile.html "The Company Profile allows Admin and Budget Process Owner users to configure application-wide settings that customize the display, enable or disable features, and define workflow behavior across Apptio Planning."). The Score value is calculated using the Score data
dimensions you specify. Each row of the Score data table constitutes a clause of the formula. The
formula uses the following values that you set per attribute:

- Normalization Factor - A number used to adjust large-attribute values to a usable
  range.
- Weighting - The relative contribution of the attribute. A weighting of less than 1
  reduces the attribute's contribution. 1 has no effect on weighting, and greater than 1 amplifies the
  relative contribution.

For example, the following Score data:

| Attribute | Normalization factor | Weighting |
| --- | --- | --- |
| Risk | 2 | 2 |
| Priority | 1 | 3 |

Results in this Score formula:

> ```
> Score = 4/5 + 3/5
>           = 7/5 = 1.4
> ```

To manage Score:

1. In the left-hand navigation pane, select Configuration > Score
2. Update the dimension values as required. You can specify each clause of your Score formula per row:
   - Attribute - Select the Project dimension for which you want to define the Score clause.
     Supported dimension types include: Boolean (True value equals 1 and a false value 0), Number,
     Integer, Enum (the ordinal equals the value where first item equals 1, second 2 and so
     on).

     Note: Memo, String, and Date dimensions are not allowed for attribute dimensions in
     Score.
   - Type - This is the data type of the selected attribute.
   - Normalization Factor - Enter a numeric value.
   - Weighting - Enter a numeric value.
3. Click Publish to make the data available in planning and spend management.

Tip: When viewing the Score in project data tables, (in the Summary view, for example)
you can do the following:

- Replace a calculated Score with a manually entered numeric value.
- Replace a manually entered value with the calculated score. To do so, click the Revert Project
  Score icon next to the Score value.
