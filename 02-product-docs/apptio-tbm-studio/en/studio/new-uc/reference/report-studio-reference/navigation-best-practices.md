---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Navigation Best Practices"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Navigation"
source_path: "studio/new-uc/reference/report-studio-reference/navigation-best-practices.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Navigation Best Practices

**Consistent Navigation Patterns**

- Place navigation controls in consistent locations across reports (e.g., always at top-left)
- Use the same button styles and colors for similar navigation actions
- Provide back navigation options (Back button or breadcrumbs) for drill-through reports
- Include clear labels and tooltips that describe the navigation destination

**Navigation Hierarchy Design**

- Design drill-through paths that follow logical data hierarchies (summary to detail)
- Limit drill-through depth to 3-4 levels to prevent user disorientation
- Create all reports as top-level reports to simplify link management
- Document navigation paths for report maintainers

**Performance Considerations**

- Avoid navigation to reports with complex calculations that may cause delays
- Keep modal dialog reports simple without complex filters or pickers
- Consider using Deferred Refresh for reports with many navigation targets
- Test navigation paths with realistic data volumes

**Troubleshooting Navigation**

**Finding the correct report path:**

1. Navigate to the target report
2. Right-click on a table and select Show API URL
3. The path shown can be adapted for Wiki-style link syntax
4. Remove the .View: prefix and use the remaining path

**Parent topic:** [Report Components: Navigation](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
