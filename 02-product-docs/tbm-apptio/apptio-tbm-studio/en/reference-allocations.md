---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Allocations"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Allocations"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/allocations.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Allocations

Allocations are the core mechanism for distributing value between model objects. They determine how costs, budgets, and other metrics flow from source objects to target objects based on configurable rules.

## Allocation Types

TBM Studio provides five allocation types to support different distribution requirements.

Weighted Value Allocation

Description: Distributes value based on the ratio (relative size) of values in a selected column from the target table. This is the most common allocation type.

Configuration Parameters

| Parameter | Required | Values | Description |
| --- | --- | --- | --- |
| Parameter | Required | Values | Description |
| Allocate (Metrics) | Yes | Cost, Budget, Forecast | Which metrics to allocate |
| To (Target) | Yes | Model object | Target model object |
| Distribution | Yes | Even, Weight By, Data Relationship | How value is distributed |
| Weight By | Conditional | Table, Metric, Other Driver | Weighting source (if Weight By selected) |
| Data Relationship | Conditional | Column pairs | Matching columns (if selected) |

Distribution Options

| Option | Behavior | Example |
| --- | --- | --- |
| Option | Behavior | Example |
| Even | Distributes equally across all target rows | $100K / 5 apps = $20K each |
| Weight By – Table | Distributes based on column ratios in target | Weight by User Count column |
| Weight By – Metric | Distributes based on another metric’s values | Weight Budget by Cost distribution |
| Weight By – Other Driver | Distributes based on another driver’s pattern | Match Labor allocation pattern |
| Data Relationship | Distributes to rows where columns match | Match Vendor ID between tables |

Note: Weight By – Metric and Weight By – Other Driver options are available in TBM Studio 12.5 and later.

Example: Weighted Value Allocation

Allocate $100,000 to five applications weighted by user count:

| Application | User Count | Allocation |
| --- | --- | --- |
| Application | User Count | Allocation |
| App A | 50 | $25,000 (50/200 × $100,000) |
| App B | 80 | $40,000 (80/200 × $100,000) |
| App C | 30 | $15,000 (30/200 × $100,000) |
| App D | 25 | $12,500 (25/200 × $100,000) |
| App E | 15 | $7,500 (15/200 × $100,000) |

Common Gotchas

See Create weighted allocations for step-by-step procedure

Consumption Allocation

Description: Allocates based on actual units consumed versus total capacity available. Used when you have specific consumption data showing how much of a service or resource each target consumes.

Configuration Parameters

| Parameter | Required | Values | Description |
| --- | --- | --- | --- |
| Parameter | Required | Values | Description |
| Consumption Column | Yes | Column from target | Number of units consumed |
| Capacity Column | Yes | Column from source | Total capacity available |
| Distribution | Yes | Even, Weight By, Data Relationship | Additional distribution logic |

Use Cases

- Cloud service consumption (GB storage consumed vs. total provisioned)
- VM allocation (VMs used by each business unit vs. total available)
- Service seats (licenses consumed vs. total purchased)

Standard Value Allocation

Description: Distributes value equal to the value already in the target table, regardless of the source amount. This creates a direct pass-through of the target’s existing value.

Key Behavior

- If target has $10,000 and source has $15,000: $10,000 allocated, $5,000 remains in source
- If target has $10,000 and source has $5,000: Over-allocated at 200%
- Source value does not limit allocation; target value determines amount

Formula Allocation

Description: Uses a custom formula to control allocation distribution. Provides maximum flexibility for complex allocation scenarios that standard methods cannot address.

Special Keywords

| Keyword | Description |
| --- | --- |
| Keyword | Description |
| SOURCE | Represents the amount of money being allocated from the source object |
| ~ (tilde operator) | Gets total value of a column across all matching rows (like SUM but respects data relationships) |

Example Formulas

| Purpose | Formula |
| --- | --- |
| Purpose | Formula |
| Weighted allocation (equivalent to Weight By) | =SOURCE*Ratio({Servers.Size},~{Servers.Size}) |
| Direct column value (like Standard Value) | =Servers.Size |
| Percentage-based allocation | =SOURCE*({Table.Percent}/100) |

Note: Formula allocations cannot replicate Consumption or Recursive allocation behaviors.

See 5.4: Formulas & Functions for complete formula syntax

Recursion Allocation

Description: Handles circular allocation patterns where services allocate costs to each other. Iteratively processes allocations until a precision threshold or maximum iterations is reached.

Configuration Parameters

| Parameter | Required | Default | Description |
| --- | --- | --- | --- |
| Parameter | Required | Default | Description |
| Precision | Yes | Varies | Minimum value to continue iterating |
| Maximum Iterations | Yes | Varies | Maximum number of allocation cycles |
| Use Incremental Mode | No | Unchecked | Adds iteration value to source |

Requirements

- Source and target tables must have identical units
- Some value must remain in target units after each iteration
- Multiple recursion allocations must not overlap

→ See Configure recursive allocations for detailed setup
