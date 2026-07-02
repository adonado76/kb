---
source_system: "apptio-planning"
practice: "tbm"
language: "en"
doc_type: "it-planning"
title: "Integrated Investment Planning"
breadcrumb: []
source_path: "it-planning/planning/iip/integrated-iip.html"
images:
  - "resources/images/it_planning_images/itp-project-column.jpg"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Integrated Investment Planning

Important: *Available with the* ***Apptio Planning Standard****subscription*

Integrated Investment Planning allows project budget owners to plan project-related costs with
operational costs in a single integrated plan. Integrated Investment Planning feature introduces an
optional Project attribute on all expense views. If the expense you are entering is non-project
related, you should leave it blank. If the expense is related to project cost, select a cost center
which is funding source for the project, and tag the expense with project identifier

To plan asset, labor, contract, and other financial expenses for project and non-project related
costs, you can follow the existing documentation to Manage direct costs. Integrated Investment Planning introduces below changes in the process.

- Cost Center is a required field on every expense type.
- Cost Object field is read only and is auto filled on selecting Cost Center, based on the Cost
  Object to Cost Center mapping defined in the reference data.
- Project is optional field on all expense types. You can assign Project identifier to only those
  expenses which are budgeted towards project.
- Selecting project identifier on the expense line automatically filters the Cost Center dropdown
  values to applicable cost centers for that project as defined in the Project reference data.
- Every expense type has Cost Type attribute which can be set to either Run or Build. If the
  expense line you are entering is related to maintenance, support, or services related to existing
  applications and / or infrastructure, such expenses should be categorized as Run cost and the
  expenses allocated towards new investments and initiatives should be categorized as Build
  cost.

  ![image](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/itp-project-column.jpg)

  For more details about Labor planning and allocation, see [Labor Resource Planning](labor-resource-planning.html).
