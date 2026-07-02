---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "costing-billing"
title: "My Landing Page"
breadcrumb: []
source_path: "costing-billing/modernization-home.html"
images:
  - "resources/images/studio_images/home-1.png"
  - "resources/images/studio_images/home-2.png"
  - "resources/images/studio_images/home-4.png"
  - "resources/images/studio_images/home-6.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# My Landing Page

This feature allows you to select a specific page or report to be your default landing
page. The Home option is enabled by default and will always show the Service Costing
report.

![img](../../../../03-media/apptio-tbm-studio/resources/images/studio_images/home-1.png)

## Adding the landing page

To configure your preferred landing page, navigate to Settings, and then select the
Configure landing page/Favorites option.

![img](../../../../03-media/apptio-tbm-studio/resources/images/studio_images/home-2.png)

Select appropriate values in Report collection and Report dropdown.

Note: The values
in the Configure Landing Page/Favorites panel will be sorted alphabetically. You can reset the
Landing page by selecting the value "none selected". If Configure Favorites option is not
selected in the Project features, the Favorites tab will be disabled in the Configure landing
page/Favorites popup.

The values in the Configure Landing Page/Favorites panel will be
sorted alphabetically. You can reset the Landing page by selecting the value "none selected". If
Configure Favorites option is not selected in the Project features, the Favorites tab will be
disabled in the Configure landing page/Favorites popup.

![img](../../../../03-media/apptio-tbm-studio/resources/images/studio_images/home-4.png)

Select Save. A confirmation message "*Home page configured successfully!*" appears.
If you refresh My Landing Page or open the application next time, it will show the your selected
page as default landing page.

![img](../../../../03-media/apptio-tbm-studio/resources/images/studio_images/home-6.png)

- Any OOTB or custom top-level report could be selected as the landing page.
- If an admin removes or revokes a report for a user, and if it was stored in the Preference service data, it will be automatically removed from the My Landing Page after it is first loaded in the CT view.
- If an Admin impersonates a user, then the user can see the changes made in Landing page by the Admin.
- Drill-to reports or other hidden reports (via Report Collection) cannot be selected as the default landing page.

Note: You cannot create any custom landing page. The selected landing page is saved across
sessions, browsers, and devices, but not in the browser cache.

**Parent topic:** [Costing and Billing](../costing-billing/home.html)
