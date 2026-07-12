---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Design Master Reports (Templates)"
breadcrumb:
  - "TBM Studio"
  - "How-To Guides (Task-Based)"
  - "Create Reports"
  - "Report Customization"
source_path: "studio/new-uc/howtoguides/create-reports/design-master-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Design Master Reports (Templates)

**Objective:** Create and apply master reports that provide consistent layout and
branding across multiple reports.

**When to use:** Use master reports when you want to:

- Ensure consistent headers, footers, and navigation across reports
- Apply standard branding elements (colors, logos, group boxes) to multiple reports
- Create reusable layouts that other report creators can adopt
- Maintain visual consistency across your organization's reports

**Prerequisites:**

- Power User or Admin role
- A clear vision of your desired report layout
- Understanding of group boxes and tabbed components

**Time estimate:** 30-60 minutes to design a master report; 5 minutes to apply it

## Understanding Master Reports

Master reports function like master slides in presentation software—they provide a template
layer that sits behind your report content. When you apply a master report to a custom
report, the master's components appear as a background "wallpaper."

**Key characteristics:**

- Master report components cannot be edited from within reports that use the master
- Components you add to custom reports sit on top of the master's elements
- Changes to the master automatically update all reports using that master
- Master reports are always top-level reports by default
- You can apply masters to other masters (not recommended)

## Step-by-Step: Create a Master Report

1. Create a new report or check out an existing report you want to use as your
   template.
2. Design the layout with elements you want to appear on all reports using this master:
   group boxes to define content areas, navigation buttons for common destinations, headers
   with company branding, and standard slicer placements.
3. On the **Report** tab, in the **Advanced** group, click **Master Report** to
   designate this report as a master.
4. Save and check in the report.

Your master report now appears in the **Masters** drop-down menu on the **Report**
tab.

## Step-by-Step: Apply a Master Report

1. Check out the report you want to apply the master to.
2. On the **Report** tab, open the **Masters** drop-down list.
3. Click the master report you want to apply.

The master's elements now appear behind your report's content. Position your components to
align with the master's layout.

**Step-by-Step: Remove a Master Report**

1. Check out the report.
2. On the **Report** tab, open the **Masters** drop-down list.
3. Select **None** at the bottom of the list.

## Best Practices for Master Reports

1. **Use masters as layout aids:** Create containers (group boxes) within which report
   creators place tables and charts. Don't add data-driven components to masters.
2. **Be careful with tabbed components:** If you add a tabbed component to a master, add
   placeholder content to each tab. Users cannot add components to individual tabs from the
   custom report.
3. **Understand group box limitations:** Group boxes in a master lose their grouping
   functionality when applied. Use them as visual borders only.
4. **Think about wallpaper placement:** Position your master's elements knowing that
   custom report components will sit on top. Leave appropriate space for content areas.

## Common Pitfalls

- **Adding data components to masters:** Tables and charts in masters don't update
  dynamically in child reports. Use masters for layout elements only.
- **Overlapping components with tabs:** Components placed over tabbed areas in a master
  appear on ALL tabs when viewed.
- **Forgetting master updates affect all reports:** Changes to a master immediately
  affect every report using it. Test changes carefully.

**Parent topic:** [Report Customization](../../../../studio/new-uc/howtoguides/create-reports/report-cust.html)
