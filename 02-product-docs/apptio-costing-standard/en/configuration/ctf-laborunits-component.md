---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "CTF - Labor Units component: install and configure"
breadcrumb: []
source_path: "configuration/ctf-laborunits-component.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Labor Units component: install and configure

Use the CTF - Labor Units component to integrate the Agile Insight Headcount model into
Costing Standard.

Applies to: TBM Studio 12.8 and later, with Template v107 and late

## Introduction

The Labor Units model is installed with the CTF – Labor Units component, and integrates with the
Agile Insights Headcount model to allocate labor in a Project, Agile, or Hybrid IT operating model.
The existing Labor Headcount dimension uses the Labor Units model, if it is installed. If the Labor
Units model is not installed, the Labor Headcount from Labor Master Data is used.

For fully Agile organizations, the Labor Units model does the following:

- Properly allocates the Application and Product TCO labor spend of the Costing Standard model
- Replaces the Agile Labor object
- Requires the alteration of certain allocations (such as Labor to Applications)
- Allows you to model Labor up to Applications and Products in both waterfall and Agile development environments

The Labor Units component allows you to allocate Labor Headcount between both Internal and
External Labor, and up to Projects and Applications to provide a better reporting experience when
viewing labor headcounts. As a result, total headcount is correctly reported per project and
application. In addition, this new layer of allocation creates a more accurate reporting of
employees who perform work across multiple IT Resource Sub-Towers.

NOTICE

Without the installation of this component, customized labor reports might fail to update the
Labor Headcount dimensions, resulting in unexpected behavior.

## About the component

The base of the model is the Labor object. The drivers for this object are Internal Headcount and
External Headcount, which get data from Labor Master Data. The Labor object drives the Time Tracking
and Other Labor Allocations objects. The allocation between these objects is weighted by the Other
Labor Allocations master data.

![](../../resources/images/ct_images/laborunitsmodel.png)

## Metrics

The following metrics are installed:

- Internal Headcount and External Headcount drivers
- Labor Units

## Master data set

The Other Labor Allocations Master Data set is installed.

![](../../resources/images/ct_images/laborunits_other_labor_allocation.png)

## Columns

The following columns are included in the master data set:

- Labor ID
- OID Metadata
- IT Resource Tower
- IT Resource Sub-Tower
- Weighting Factor

## Sample backing data

Labor to IT resource tower mapping:

![](../../resources/images/ct_images/laborunits_sample_data.png)

## New field

A new field is added to the Labor Master Data to break out Internal versus External Headcount: Is
Internal Labor

## Configuration

The following instructions assume that Costing Standard is already installed.

1. In TBM Studio, go to Projects > Components, then click CTF - Labor Units
   to install the Labor Units component. The following drivers are installed:
   - Internal Headcount
   - External Headcount

   These drivers automatically pull in headcount values from the Labor Master Data to populate both
   the Internal Headcount and Labor Units models

   .![](../../resources/images/ct_images/laborunits_internal_headcount.png)

   When the unit drivers
   are populated, the Labor Units model looks like this:

   ![](../../resources/images/ct_images/laborunits_labor_allocation.png)
2. Go to Steps 
   Model
   Labor Units.
3. To leverage Labor ID and allocate Other Labor Allocations to Labor, set the From to Labor
   where Check for TT = '0'.

   ![](../../resources/images/ct_images/laborunits_configure_labor_from_luke.png)

   Note: Installing
   the Labor Units component into an existing project might result in an allocation between Labor and
   IT Resource Towers. If this occurs, delete the allocation on the Labor Units model, and instead,
   create an allocation from Labor to Other Labor Allocations and then from Other Labor Allocations to
   IT Resource Towers.
4. Select Weight By, then Table Column, then
   Weighting Factor.
5. For Data Relationship, enter Labor ID for both the Source
   Column and Destination Column.
6. For the remaining model, leverage the existing allocations from the Cost Model. If custom
   allocations exist, select the following metrics to apply to that allocation to track headcount:
   - Internal Headcount
   - External Headcount
   - Labor Unitsp

     ![](../../resources/images/ct_images/laborunits_time_tracking.png)

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
