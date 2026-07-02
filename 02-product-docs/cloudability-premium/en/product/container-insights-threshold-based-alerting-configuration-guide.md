---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Container Insights: Threshold-based Alerting Configuration Guide"
breadcrumb:
  - "Cloudability Premium"
  - "Insights"
  - "Container Cost Allocation"
source_path: "product/container-insights-threshold-based-alerting-configuration-guide.html"
images:
  - "images/threshold-based_alerting1.jpg"
  - "images/threshold-based_alerting2.jpg"
  - "images/threshold-based_alerting3.jpg"
  - "images/threshold-based_alerting4.jpg"
  - "images/threshold-based_alerting5.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Container Insights: Threshold-based Alerting Configuration Guide

Overview

Container Insights now supports threshold-based alerting that can be configured in two ways:

1. Directly through Dashboard Widgets

   ![Notes Icon](../../../../03-media/cloudability-premium/images/threshold-based_alerting1.jpg)
2. Through the dedicated Alerts tab

   ![Notes Icon](../../../../03-media/cloudability-premium/images/threshold-based_alerting2.jpg)

Configuration Methods

Method 1: Configure Through Dashboard Widgets

1. Navigate to the Container Insights dashboard
2. Click the horizontal ellipsis (⋯) on any widget
3. Select  Create Alert  from the dropdown menu
4. In the Alert Configuration template:
   - Enter Alert name and description
   - Set Query values
   - Define Trigger and filter conditions
   - Assign users for notifications
   - Save the configuration

     ![Notes Icon](../../../../03-media/cloudability-premium/images/threshold-based_alerting3.jpg)

Method 2: Configure Through Alerts Page

1. Navigate to the Container Insights page
2. Click  Alerts  tab (located next to "Dashboard" and "Treemap" views)
3. Select  Configuration  sub-tab and then  New Alert
    at the right end
4. In the Alert Configuration template:
   - Enter Alert name and description
   - Set Query values
   - Define Trigger and filter conditions
   - Assign users for notifications
   - Save the configuration

Managing Alerts

- View all configured alerts under  Alerts  tab
- Access  Configured Alerts  sub-page to see the complete list
- Edit or delete existing alerts as needed
- Monitor alert status and history

  ![Notes Icon](../../../../03-media/cloudability-premium/images/threshold-based_alerting4.jpg)

Important Notes

- The maximum number of alerts per organization is 100
- Email is currently the only supported notification channel
- All users can create alerts for themselves
- Cloudability Admins can assign alerts to other users

For additional support or questions, contact our support team.

![Notes Icon](../../../../03-media/cloudability-premium/images/threshold-based_alerting5.jpg)p

**Parent topic:** [Container Cost Allocation](../product/k8s-cost-allocation.html)
