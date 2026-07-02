---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Configuration responsibilities"
breadcrumb:
  - "Benchmarking"
  - "Configuration Guide"
source_path: "it-benchmarking/configuration/configuration-responsibilities.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Configuration responsibilities

A simple split of who does what.

**TBM / ITFM Program Lead** 

- Owns how Interactive Benchmarking is used in the TBM / ITFM program.
- Approves major changes like peer group selection and taxonomy version.

**TBMA / Benchmarking owner** 

- Drives configuration and mapping work.
- Maintains organizational profile, cost, volumes, and FTEs.
- Runs validations and answers “why does this look like that”.

**Apptio platform admin** 

- Manages product access and environment-level settings.
- Coordinates with IBM Apptio support resources if something breaks.

**Resource Tower owners and Finance partners** 

- Provide source data and context.
- Sanity check infra and OpEx results for their area.

If you do not know who plays each role, define that before you start changing things.

**Initial configuration checklist**   
You should be able to tick all of these
before you call configuration “done”:

- You should be able to tick all of these before you call configuration “done”:
- A single Costing project, if Costing is integrated, is designated as source of cost data.
- TBM version is selected and, if Costing is integrated, matches the version used in your Costing
  project.
- Organizational profile is complete.
- Annual IT cost by Cost Pool and Resource Tower is available for that year.
- Infra cost and volumes are available if you plan to use infra benchmarks.
- Default peer group is defined.
- Industry and IT OpEx domains are enabled and returning sensible values.
- If infra is in scope, at least one Resource Tower infra metric is working.

You can treat this as the “admin version” of the Implementation Checklist.
