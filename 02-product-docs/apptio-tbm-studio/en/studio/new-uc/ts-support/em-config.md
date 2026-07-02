---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "studio"
title: "Configuration Recommendations"
breadcrumb:
  - "TBM Studio"
  - "Troubleshooting and Support"
  - "Error Messages Explained"
source_path: "studio/new-uc/ts-support/em-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuration Recommendations

This section provides explanations and solutions for common error messages in TBM
Studio. Access recommendations via TBM Studio > Recommendations tab.

|  |  |  |
| --- | --- | --- |
| **Error Message** | **Meaning** | **Solution** |
| Assignment Ratio Table is Too Large | Assignment ratio table exceeds size limits, impacting performance | Add Data Relationship, add From/To filters, reduce identifier rows |
| No Identifier on Large Model Object | Large model object lacks identifier, causing performance issues | Set Use object identifier in Rows dropdown, select required columns |
| Legacy Model Join Operation Used | Allocation uses R11-era automatic relationship configuration | Clear Automatic relationship checkbox, set explicit columns |
| Limited Threshold: Row Expanding | LookupEx, SplitEx, or Unpivot exceeds row limits | Reduce one-to-many matches, limit data expansion, reduce columns |
| Allowable Metric Count Exceeded | Project has reached maximum number of metrics | Delete unused metrics via Project Explorer > Metrics |
| Transform Model Step Columns Exceeded | Table with model steps exceeds column limit | Add Hide and Rename step to hide unneeded columns |
