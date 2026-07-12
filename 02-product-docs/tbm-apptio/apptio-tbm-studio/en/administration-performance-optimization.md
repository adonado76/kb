---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Performance & Optimization"
breadcrumb:
  - "Administration"
  - "Performance & Optimization"
source_path: "SSWRJM/studio/new-uc/admin/performance-optimize.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Performance & Optimization

Content Type: How-To / Troubleshooting

Target Audience: Administrators, Power Users

Prerequisites: Admin or Power User role, understanding of model structure

Performance optimization is critical for maintaining responsive reports and efficient calculations. This section covers tools and best practices for monitoring and improving TBM Studio performance.

## Calc Explorer

Calc Explorer provides detailed insights into calculation processes and helps identify performance bottlenecks. It displays calculation effort for reports, transforms, drills, and metrics.

To access Calc Explorer:

- Navigate to Build > Calc Explorer
- Select a build to analyze its calculation details
- View reports, transforms, drills, and metrics that took more than 10 seconds to calculate

Note: Calc Explorer only captures items that take longer than 10 seconds to calculate. Components that complete quickly will not appear in the analysis.

## Build Anomaly Detection

The anomaly detection feature identifies unusual changes in calculation effort, helping you spot potential performance problems early. It compares each build to previous builds and alerts you to significant changes.

Types of anomalies detected:

- Calculation Anomaly - Unexpected increase in calculation time
- Entity-Based Anomaly - Unusual patterns in data shape (e.g., unexpected row counts)
- Combined - Both calculation and entity-based anomalies detected together

To enable anomaly detection:

- Navigate to Project > Enable Features
- Select Show Anomalies Panel
- View anomalies under Project > Anomalies

## Recommendations Engine

The Recommendations engine identifies configuration issues that may impact performance or data quality. It provides guided workflows to resolve common problems.

Common recommendation types:

- Zero Unit Allocations - Allocations with zero units that consume processing time without adding value
- Unused Allocations - Allocation steps that are no longer needed
- Unused Reports - Reports that have not been accessed recently
- Base Data Columns Unused - Columns in base tables not used by transforms or reports
- ALL_ROWS Issues - Time-based queries that may need ALL_ROWS handling

To resolve recommendations:

- Navigate to TBM Studio > Recommendations
- Select a recommendation and click Troubleshoot All Identified Problems
- Follow the guided workflow to review and fix issues
- Check in changes when complete

## Performance Review Component

The Performance Review component provides reports that help administrators understand the impact of project configuration on performance. It includes analysis of allocation relationships, identifier health, and model granularity.

Key reports in the Performance Review component:

- Allocation Information - Shows allocation relationship table sizes for quick identification of large allocations
- Drill and Identifier Information - Analyzes table granularity and allocation efficiency
- Model Granularity - Identifies areas where low-dollar allocations may impact calculation time
- Identifier Health Score - Measures identifier variation over time (scale of 1-100)

## Performance Optimization Best Practices

- Reduce unnecessary granularity - Remove columns and detail not needed for allocations or reporting
- Group rows - Aggregate transaction-level data to reduce row counts where detail is not needed
- Deactivate unused reports - Reports contribute to calculation time even if not frequently viewed
- Replace Eval() with DynamicColumn() - Enables precision calculation performance improvements
- Limit project time span - Calculate only the periods necessary for reporting requirements
- Resolve recommendations regularly - Address zero-unit allocations and unused configurations proactively
