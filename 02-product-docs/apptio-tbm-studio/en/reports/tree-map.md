---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "en"
doc_type: "reports"
title: "Tree maps"
breadcrumb: []
source_path: "reports/tree-map.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tree maps

Applies to: TBM Studio 12.0 and later

One of the best ways to portray the relative proportions of values is to use a tree map. Tree
maps display nested rectangles that represent hierarchical (tree-structured) data. A sample tree map
is shown in the following image:

![](../../resources/images/studio_images/studioimages/reports/rep334.png)

## Display values in a tree map

A tree map can display a single value such as cost, or you can compare two values such as budget
plan and actuals. When you compare values, color is used to indicate the variance between the
values. A scale is displayed to help you judge the degree of the variance.

The variance percentage is calculated by subtracting the second value from first value and
dividing the result by the second value. For example, assume you have the following data:

| Business Unit | Cost | Budget | Variance |
| --- | --- | --- | --- |
| Sales | 1,000 | 800 | -20% |
| Marketing | 2,000 | 2,100 | 5% |
| R&D | 3,000 | 2,700 | -11% |
| Support | 2,500 | 2,800 | 11% |
| Engineering | 1,500 | 1,500 | 0% |

You create the chart using the settings shown in the following image:

![](../../resources/images/studio_images/studioimages/studio/stu559.png)

## Create a tree map

To create a tree map:

1. Create a table.
2. Select Tree Map from the Ad Hoc tab.
3. Use the options on the Tree Map tab to configure the map.

Note: The Tree Map visualization supports up to 4 columns in the legend.
