---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Theme Engine"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Working with Reports"
source_path: "studio/report-studio/theme-engine.html"
images:
  - "resources/images/studio_images/apply-them-eng.png"
  - "resources/images/studio_images/def-theme-eng.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Theme Engine

## Overview

The Theme Engine in the New Report Studio enables consistent styling and formatting across
reports by applying a predefined set of visual configurations such as colors, typography, spacing,
and component styles.

Themes help standardize report appearance, reduce manual formatting effort, and accelerate
migration from the Classic Report Studio to the New Report Studio.

## What is a theme?

A theme is a reusable collection of formatting settings that controls the visual appearance of
reports.

A theme can include:

- Color palettes
- Typography (font family, font size)
- Component styling
- Spacing
- Borders

Themes ensure visual consistency across reports while allowing users to make report-specific
customizations when needed.

## Default Theme Behaviour

![default theme engine](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/def-theme-eng.png)

**Project-Level Theme** - In the Classic Report Studio, under **Project Settings**, a
**Report Theme** can be configured.

- The default theme is set to **Core**
- In addition to Core, four other out-of-the-box themes are available
- Users can select one of these themes as the project-level default

**Automatic Theme Application** - The project-level default theme is automatically applied to:

- Newly created reports in the New Report Studio
- Reports migrated from the Classic Report Studio

This ensures a consistent starting point for report formatting.

## Applying or Changing a Theme for a Report

Within the New Report Studio, users can apply or change a theme at the report level.

![applying theme in engine](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/apply-them-eng.png)

Navigate to File Menu -> Apply Theme

**Report-level override** - When a theme is changed from the File Menu:

- The selected theme applies only to the current report
- It overrides the project-level default theme for that report

This allows flexibility for reports that require different visual styling.

## Component – Level Formatting

Even after a theme is applied, users can continue to customize individual report components.

Examples:

- Changing chart colors
- Adjusting font size for a visualization
- Modifying spacing or borders for specific components

These component-level formatting changes override the corresponding theme settings for that
specific component only.

## Best Practices

- Use project-level themes to maintain consistency across reports
- Use report-level overrides only when a report requires unique branding or styling
- Minimize excessive component-level overrides to preserve consistency
- Apply themes before large-scale migration activities to reduce manual effort
