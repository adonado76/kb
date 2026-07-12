---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Custom Formulas"
breadcrumb:
  - "How-To Guides (Task-Based)"
  - "IBM Apptio Report Studio (New)"
  - "Core Concepts"
  - "Custom Formulas"
source_path: "SSWRJM/studio/report-studio/create-first/custom-formula.html"
images:
  - "03-media/apptio-tbm-studio/cust-form.png"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Custom Formulas

*Custom formulas (also referred to as formula dimensions) allow you to define new calculated dimensions using existing fields in your data model. This enables deeper analysis and richer insights without requiring any changes to the underlying dataset or schema.*

## Why use Formula Dimensions?

- Derive new dimensions from existing data
- Perform calculations directly within the report experience
- Explore data more flexibly without depending on data model changes

## How Formula Dimensions Work

- Instead of selecting only predefined dimensions from the underlying schema, you can Define a custom formula using supported fields and functions You can now add descriptions to custom formulas to provide additional context about the formula logic or intended usage Save the formula as a reusable formula dimension
- Once created, formula dimensions behave like standard dimensions and can be used for grouping, slicing, filtering, and visualization

## Availability Across Components & Visualizations

Formula columns are supported across all components and visualizations.

Below is an example of a custom formula configured in a table.

## Enhanced Formula Editor with Intelligent Autocomplete

The formula editor now provides intelligent autocomplete and guided syntax assistance to make formula creation faster and easier. As you type, the editor suggests relevant functions, displays their signatures, and provides context-aware recommendations to help you build valid expressions with fewer syntax errors.

Function autocompletes

As you type in the formula editor, matching functions are suggested in real time.

- Function suggestions are filtered dynamically based on your input.
- Matching uses partial text (contains), so typing part of a function name displays relevant results.
- Function signatures are shown in the suggestion list to help you understand the required parameters.

For example, typing ro may suggest round() and other matching functions.

Function insertion

When you select a function from the suggestion list:

- The function is inserted into the editor with parentheses.
- The cursor is automatically placed inside the parentheses so you can immediately begin entering parameters.

For example, selecting round() inserts : round(|)

(where | represents the cursor position).

Guided syntax assistance

The editor provides guidance while you build expressions by indicating the expected parameters for each function.

- Suggestions appear as you type without interrupting your workflow.
- You can accept a suggestion by pressing Enter or by selecting it with the mouse.
- After a parameter is accepted, the editor automatically inserts a comma and positions the cursor for the next parameter when appropriate.

For example : round(metric, |)

The editor then continues to guide you toward the next expected input.

Context-aware suggestions

When a function expects a table, column, or metric reference, the editor surfaces relevant suggestions based on the current context.

- Suggestions are displayed as you type.
- You can navigate the list using the keyboard or mouse.
- Selecting a suggestion inserts it at the current cursor position.

Benefits

The enhanced formula editor helps you:

- Create formulas more quickly with intelligent autocomplete.
- Reduce syntax errors through guided parameter entry.
- Discover available functions and their signatures as you work.
- Build valid expressions with context-aware suggestions and real-time assistance.
