---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Hierarchical Slicer"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
  - "Hierarchical Slicer"
source_path: "SSWRJM/studio/report-studio/components/hierarchical-slicer.html"
images:
  - "03-media/apptio-tbm-studio/hier-sl-1.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Hierarchical Slicer

*Hierarchical Slicers allow you to filter report data across multiple levels of a hierarchy using a single slicer. By configuring multiple dimensions in a parent-child sequence, users can progressively navigate and filter data without adding multiple independent slicers to the report.*

This simplifies report layouts and provides a more intuitive way to explore hierarchical datasets.

## Configure a Hierarchical Slicer

To create a Hierarchical Slicer:

1. Add a Hierarchical Slicer component to your report.
1. Open the Data panel.
1. Add one or more dimensions to the Slice By section.
1. Arrange the dimensions in the desired hierarchy order:
1. The first dimension becomes Level 1 .
1. The second dimension becomes Level 2 .
1. The third dimension becomes Level 3 , and so on.

For example:

- Category
- Service
- Instance Type

The order of dimensions defines how users navigate through the hierarchy.

## Using a Hierarchical Slicer

When a report consumer interacts with the slicer:

- Only the top-level (Level 1) values are displayed initially.
- Selecting a Level 1 value reveals its corresponding Level 2 values.
- Selecting a Level 2 value reveals its corresponding Level 3 values.
- Additional hierarchy levels continue to expand as selections are made.

This progressive navigation allows users to drill into increasingly specific subsets of data within a single filtering control.

Selecting Compute → EC2 → m5.large filters the report to display only data matching that hierarchy path.

Filtering behaviour

Selections made in the Hierarchical Slicer automatically filter all linked report visualizations.

- Selecting a Level 1 value filters all data within that category.
- Selecting a Level 2 value further narrows the results within the selected parent.
- Selecting deeper levels progressively refines the filtered dataset.

Tables and charts update automatically to reflect the current hierarchy selection.

## Search

The Hierarchical Slicer supports searching within hierarchy levels, making it easier to locate values in large datasets.

Benefits

Hierarchical Slicers help you:

- Filter complex hierarchical data using a single control.
- Reduce report clutter by eliminating the need for multiple related slicers.
- Navigate parent-child relationships more intuitively.
- Explore data progressively across multiple levels of detail.
- Simplify report authoring and improve the report consumer experience.
