---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Model Diagrams"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Model Studio Reference"
source_path: "studio/new-uc/reference/model-studio-reference/model-diagram.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Model Diagrams

Model diagrams provide visual representations of the cost model structure, showing how value
flows between model objects.

## Diagram Types and Views

TBM Studio provides three ways to view the model, each serving different purposes.

**Single-Table View (Model Edit Workspace)**

**Description:** Shows one model object with its drivers and allocations in a Sankey diagram.
Used for configuring individual objects.

**Layout**

- Left column: Drivers (unit drivers and incoming allocations)
- Center: The model object being edited
- Right column: Outbound allocations (target objects)

**How to Access**

1. Click a table in Project Explorer
2. Click the Model step in the transform pipeline

**Modeled Metric View (Diagram View)**

**Description:** High-level visualization showing all model objects and their connections.
Similar to a Visio diagram. Used for understanding overall model structure.

**Features**

- Displays all model objects and connections
- Supports zooming and panning
- Clicking a node opens the Single-Table view for that object
- Cost traceability for specific allocation lines
- Reflects currently deployed model

**Note:** The diagram view cannot be used to modify allocations directly. Changes must be made
in the Single-Table view.

**Model Report View (Tier/Sankey View)**

**Description:** End-user view showing selected tables organized in tiers with Sankey-style
flow visualization. Used for reporting and analysis.

**Features**

- Customizable tier structure
- Shows proportional flow widths
- Drill-down to column detail
- Click-through to transaction-level data
- Can be added to report collections (v12.2.2+)

*See [Model Reports for detailed
configuration](model-reports.html)*

- **[Sankey Diagram Concepts](../../../../studio/new-uc/reference/model-studio-reference/sankey-diagram.html)**
- **[Diagram Navigation](../../../../studio/new-uc/reference/model-studio-reference/diagram-navigation.html)**
- **[Diagram Customization Options](../../../../studio/new-uc/reference/model-studio-reference/diagram-customization.html)**
- **[Export and Sharing](../../../../studio/new-uc/reference/model-studio-reference/export-sharing.html)**
