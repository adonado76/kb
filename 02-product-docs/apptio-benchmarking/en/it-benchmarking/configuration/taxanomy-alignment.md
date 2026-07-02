---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Taxonomy and version alignment"
breadcrumb:
  - "Benchmarking"
  - "Configuration Guide"
source_path: "it-benchmarking/configuration/taxanomy-alignment.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Taxonomy and version alignment

Benchmarking uses TBM structures to interpret your data. If your Costing project’s model does not
align with your Interactive Benchmarking’s ATUM version, the metrics will be inaccurate and
incomplete.

**Select the ATUM (aka TBM) version**   
In Interactive Benchmarking’s
Configuration, there is a choice of ATUM (aka TBM) version.

![Interactive Benchmarking’s Configuration – ATUM version selection](../../resources/images/it%20benchmarking_images/benchmarking-atum.png)

  
Guidelines

- Match the version used in your Costing project.
- If you are mid-migration, pick the target version and finish the Costing side first
- Avoid switching versions casually. Treat it as a structural change with a clear effective year.

  
The selected version controls:

- Which Cost Pools, Resource Towers, and Sub-Towers exist.
- How infra metrics are grouped and labeled
- Which benchmark definitions are available.

**Validate your TBM model alignment**   
Once a version is selected in Interactive
Benchmarking:

- Confirm your Costing model uses the same version with same Cost Pools and Resource Towers.
- Identify custom or merged structures, for example:
  - Local “Data Center” category that mixes multiple standard Resource Towers.
  - Custom Cost Pools that mix Labor and Outside Services.
  - Extra Sub-towers not present in the standard TBM taxonomy.

  
Document how you will map those local structures into standard benchmark ones.
  
Typical approaches:

- Create mapping tables in Costing that map local codes to standard Cost Pools and Resource
  Towers.
- Where you cannot map 1-to-1, decide whether to:
  - Map to the closest standard tower and annotate.
  - Exclude from benchmarking scope.  
  If you skip this step, you will spend months arguing about why your structure does
  not look like peers.
