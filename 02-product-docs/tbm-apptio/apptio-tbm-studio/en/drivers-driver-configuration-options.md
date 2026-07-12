---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "tbm-studio"
title: "Driver Configuration Options"
breadcrumb:
  - "Reference"
  - "Model Studio Reference"
  - "Drivers"
  - "Driver Configuration Options"
source_path: "SSWRJM/studio/new-uc/reference/model-studio-reference/driver-config-option.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Driver Configuration Options

Complete Driver Parameters

| Parameter | Required | Values | Description |
| --- | --- | --- | --- |
| Parameter | Required | Values | Description |
| Add To (Metrics) | Yes | Cost, Budget, Forecast, Custom | Which metrics receive this driver’s value |
| Using (Type) | Yes | Column, Metric, Formula | How the value is determined |
| Column | Conditional | Column names from table | Required when Using = Column |
| Metric | Conditional | Available metrics | Required when Using = Metric |
| Formula | Conditional | Valid formula expression | Required when Using = Formula |
| Notes | No | Free text | Documentation for maintainability |
