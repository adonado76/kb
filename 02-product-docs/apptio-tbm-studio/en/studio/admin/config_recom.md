---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configuration recommendations"
breadcrumb: []
source_path: "studio/admin/config_recom.html"
images:
  - "resources/images/studio_images/config-recom.png"
  - "resources/images/studio_images/config_rec_pane.png"
  - "resources/images/studio_images/fixit-button.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuration recommendations

TBM Studio provides configuration recommendations to let you know if there is a potential problem
with the data tables.

To view recommendations, go to **Home** > **Recommendations**.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/config-recom.png)

The Configuration Recommendations pane is displayed. If there are a large number of
recommendations, you can use the filter options to restrict which recommendations are displayed. The
Configuration Recommendations pane displays the number of detected instances of each problem beside
the recommendations. In the example below, there are 2 instances of a table where a legacy model
join operation has been used, so the Configuration Recommendations pane displays Legacy model join
operation used. (2) followed by the locations where the problem is detected.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/config_rec_pane.png)

Tip: See the list of recommendations and actions to [Resolve
identified issues](../troubleshooting/studio-troubleshooting-about.htm "(Opens in a new tab or window)").

The Fix All Identified Problems button is now renamed to **Troubleshoot All Identified
Problems**. Clicking on the button will initiate a multi-step workflow which engages the
administrator in the troubleshooting and automated “fix it” process.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/fixit-button.png)
