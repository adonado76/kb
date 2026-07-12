---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Lineage"
breadcrumb: []
source_path: "studio/admin/lineage-in-tbm-studio.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Lineage

Data lineage is the process of tracking the flow of data over time, providing a clear
understanding of where the data originated, how it has changed, and its ultimate destination within
the data pipeline.

## Why do we require Lineage in TBM Studio

In Apptio, lineage shows a description of flow across a network of many complex relationships.
Example: A table flowing into other tables, a table moving into model objects with many metrics and
then to different reports. Different areas in TBM Studio where lineage is able to track and
understand the dependency are :

- Data Pipeline
- Modelling
- Reporting

In **data pipeline** first thing you do is ingest the data from different sources, you may
have one table being sourced from another table, or you might be appending tables. You can also have
table joins which can identify key relationships between different tables. And then finally within
any table there may also be formulas with definitions that are dependent on another table such as
lookup.

In **Modelling** you get to have One to one ,One to many, or Many to many relationships
between different allocation objects and we derive some complex weighting algorithms to those
objects.

With **Analytics Reports and Visualisations**, each report may have multiple tabs with
multiple components. Each component is comprised of multiple metrics. Now you can understand that
your Apptio project can become a complex environment.

Our goal is to visualise this massively interconnected web of connections between tables, models,
and reports and to show potentially obscure and unknown interdependencies. This will enable
administrators to understand the impact of changes made to the configuration. So lineage provide us
this super powerful analytics and insights that helps you answer basic questions like, "What would
happen if I delete this one column in this table?”

## Lineage Use Cases

Some of the use cases of Lineage are:

- Show immediately what is ‘used by’ a particular entity (downstream dependencies) or what is that
  entity depending upon (upstream dependencies).
- Identify the project impact, if you modify or change an entity such as a column or what if you
  remove a table.
- Clean up the project complexity that grows over time, by identifying and removing orphan tables
  or unused calculated metrics.
- Remediate data privacy information by identifying exactly where data exists and where it is
  exposed.

## How to access Lineage

One way to access lineage is in the Project Explorer left panel by opening the menu using a
<right click> and selecting **Trace Lineage for this document**. The other is to <right
click> on an entities tab on the bottom tab navigation. A Lineage window opens with a visual
representation of the data flow depending upon the initial entity selected. The initial view is
limited to a depth of 1 and will show either downstream dependencies if starting from a table,
column, or calculated metric; or upstream dependencies if starting from a report. Let’s begin by
defining the information shown on the lineage view. Each color represents a particular entity:

- Gray represents raw data.
- Green represents standard tables and columns.
- Brown represents editable tables and columns.
- Blue represents model objects and metrics.
- Tan represents reports and report components.

You can scroll the mouse roller or drag the touchpad on your laptop to zoom in or zoom out of the
diagram.

You can explore the Lineage graph by altering the following data:

|  |  |
| --- | --- |
| Depth | We always start with the depth of 1 which extends the scope of the relationships from the selected entity. As the project can get very complex, you will get more depth to drill down the relationships. Move the slider to increase the depth and deep dive into the level of dependencies. |
| Show documents that | You also have the ability to switch between downstream dependencies which is by default if you pick something like a table, or upstream dependencies which would be default if you pick a report. Select to see documents that Depend on the focused entity (downstream dependency)or for The focused entity depends on(upstream dependency). |
| Only cycles | Select this check box to view only cycle |
| Search Text box | Enter the keyword(s) that you want to exclude (-) or include (+)in the search results. For more info on Lineage Search. Click here. |
| Added keys | Displays all the entities that have the keywords added in the search text box |
| Excluded keys | Displays all the entities that the keyword removed in the search text box |
| Toggle sub types | Select this to toggle between check/uncheck all the subtypes in one go together. |
| Toggle bulk remove | Removes all entities included in the Added Keys or Hidden Keys |
| Apply | Select this button to apply changes made in this panel. |

Related Topics:

- [Lineage demonstration](lineage-demo.html "The Lineage feature is not active by default. An Administrator can enable it by navigating to Project tab > Enable Features, and then select Show Lineage. It can then be accessed from different entities, like Tables, Columns in Tables, Editable Tables and Metrics Reports.")
- [Related Filter](lineage-related-filter.html "Another way to utilize Lineage feature in a simplified user experience in Project explorer is that now you have the ability when you click at any table it will show you any related tables by bonding them further on their relationship.")
- [Find unused
  documents](lineage-unused-docs.html)
- [Lineage search](lineage-search.html)
