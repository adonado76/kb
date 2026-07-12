---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Cloud Daily/Hourly Reports - Extending or Changing (12.5 and earlier)"
breadcrumb: []
source_path: "configuration/clouddailyhourlyreports.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cloud Daily/Hourly Reports - Extending or Changing (12.5 and earlier)

The Daily/Hourly reports are built on a data format that enables rapid and efficient
storage and queries on very high-volume data sets (such as very granular cloud bills like the AWS
Cost and Usage Report). As a result, extending the schema of the data sets involved and modifying
reports built on those data sets requires some configuration

Applies to: Cloud on Costing Standard on TBM Studio 12.3.3 and later; Cloud Business Management
on TBM Studio 12.5.x and earlier

The Daily/Hourly data is stored in a different format, separately from other Apptio data. The
object on which reports are built is called dbr\_daily, which can be found in the tables section of
TBM Studio, but, because of the extremely high volume of data and the new data format, certain
actions cannot be performed:

- You will not be able to see the data in TBM Studio.
- You cannot add items to the transform pipeline (with the exception explained in the "Adding new,
  custom attributes" section, below).
- You cannot add transforms to the data set.

**Parent topic:** [Costing Standard](../home.html)

## Extending the Daily/Hourly Schema

To use out-of-the-box attributes (the quickest way to see your organization’s specific
data):

### Procedure

1. Map from the columns in the provider bills, such as Accounts or Tags, to the out-of-the-box CBM
   attributes.

   For example, if you have a tag user called Owner, map that tag to the existing System Owner
   attribute.
2. For more information, see Map AWS tags to Apptio Schema or Tag values in Azure to Apptio Schema.
