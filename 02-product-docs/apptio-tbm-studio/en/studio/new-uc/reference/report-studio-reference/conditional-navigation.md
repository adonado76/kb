---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Conditional Navigation"
breadcrumb:
  - "TBM Studio"
  - "Reference"
  - "Report Studio Reference"
  - "Report Components: Navigation"
source_path: "studio/new-uc/reference/report-studio-reference/conditional-navigation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conditional Navigation

Control navigation component visibility and behavior based on data values, user roles, or other
conditions. Conditional navigation ensures users see only relevant navigation options.

**Button State Conditions**

Use formulas in the Enabled field of button properties to control button availability:

**Enable button when cost exceeds threshold:**

`<%=IF(Cost>5000,"enabled","disabled")%>`

**Hide button when no data exists:**

`<%=IF(RowCount()=0,"hidden","enabled")%>`

**Component Visibility by Role**

Control which navigation components appear based on the user's assigned role:

1. Select the navigation component (button, group box containing navigation, etc.)
2. In the Advanced group of the Report tab, click Visibility
3. Select User's current role is and choose the roles that should see this component
4. Users not in selected roles will not see the component

**Dynamic Text Visibility**

Use the Dynamic text does not evaluate to "hidden" visibility option to conditionally show or
hide navigation based on calculated values. If your formula returns "hidden", the component
disappears.

**Parent topic:** [Report Components: Navigation](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
