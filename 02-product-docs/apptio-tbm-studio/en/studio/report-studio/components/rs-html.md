---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "HTML"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Components"
source_path: "studio/report-studio/components/rs-html.html"
images:
  - "resources/images/studio_images/html.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# HTML

The HTML component lets you embed custom HTML content directly into a report. It is
useful for adding rich text, links, images, or custom layouts that are not available through
standard components.

## When to use HTML

Use the HTML component when you want to:

- Add formatted text such as headings, paragraphs, or lists
- Include hyperlinks to external or internal resources
- Display static images or icons
- Provide explanatory content, disclaimers, or annotations within a report

## Add a HTML component to the Report

1. Add a HTML from the Components pane on the toolbar
2. Click on the HTML to enable the Data and Format panels.
3. Data Panel
   1. Select the model object from the dropdown list
   2. Drag dimensions from the Dimension Explorer to the row, columns, values and filters
      sections in the data panel
4. Format Panel
   1. General Properties – See [Component
      Properties](components.html#abt-comp__comprop)
   2. HTML-specific Properties
      1. Click the maximize icon or enter the HTML **content** in the text box.

Example: HTML

![html](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/html.png)

HTML supports custom formulas and formula dimensions. For more details, see [Custom Formulas](../create-first/custom-formula.html "Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.")
