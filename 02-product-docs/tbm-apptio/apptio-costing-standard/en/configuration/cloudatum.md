---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "en"
doc_type: "configuration"
title: "Cloud configuration and ATUM 2.0"
breadcrumb: []
source_path: "configuration/cloudatum.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Cloud configuration and ATUM 2.0

This article explains some configuration updates related to ATUM 2.0 and Public Cloud if
modifications are needed to the Master Data Sets (Cloud \ ITRT) in order to support the ATUM 2.0
taxonomy. The following changes set up ATUM 2.0, with an additional section that shows a servers
transform that appends the Server Master Data for Public Cloud with a filter that needs to be
removed to allow the data to show.

**NOTICE**

In the IT Resource Towers list that comes out-of-the-box,towers and subtowers are not identified
as being Public Cloud, so you will need to update that list to include subtowers with Public
Cloud.

Applies to: Cloud for Costing Standard on TBM Studio 12.4.1 and later.

## Configuration changes

Cloud Service Provider
:   1. Append the AWS Cost Allocation Bill Master, then change Product column to ProductCode.
    2. In the Formulas section, update Instance Type, Subtower, Tower, Type, Unit as follows:
       1. For Instance Type, map to =Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,Instance
          Type).
       2. For Subtower, map to=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,{SubTower 2.0}).
       3. For Tower, map to=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,{Tower 2.0}).
       4. For Type,map to=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,Type).
       5. For Unit, map to=Lookup(Lookup,Cloud Service Provider Lookup v2,Lookup,Unit).
       6. Change Lookupto =Product&&Item&&Procedure.
    3. Net new is Product.
    4. For ATUM 1.0 only, leverage Item&&Procedure.
:   ![](../../resources/images/ct_images/7988_2.png)

IT Resource Master Data
:   1. In the Formulas section, change Is Cloud to Public Cloud=Yes, since the public cloud report
       below has a filter for Is Cloud.

       By default, Is Cloud looks at the IT Resource Sub-Tower, then
       back to the Lookup file to determine the value, but changing it to look at the v2 file would
       over-inflate costs on the public cloud reports because it would flag non-cloud-related
       subtowers.

       ![](../../resources/images/ct_images/7988_3.png)
    2. Append in the Public Cloud flag to the metadata field in the IT Resource Tower Master Data. This
       separates non-cloud costs from cloud costs.![](../../resources/images/ct_images/7988_4.png)

    Cloud reports are set up to filter for the Is Cloud value, set above.

    ![](../../resources/images/ct_images/7988_5.png)

## Cloud servers transform for Public Cloud

For ATUM 2.0 and the cloud servers transform, change the filter for Cloud Compute Linux and
Windows to include Compute – Servers – Public Cloud, as shown.

![](../../resources/images/ct_images/7988_6.png)

For information about mapping AWS services, see [AWS Services
Mapping](awsservices.html "Apptio's CBM and AWS DataLink connectors allow you to map billing line items from your cloud provider billing line items to ATUM attributes, including IT Towers and Subtowers, the TBM Services hierarchy, as well as a normalized unit of measure.").

For information about mapping Azure services, see [Azure Services
Mapping.](azuremap.html "Apptio's CBM and AWS DataLink connectors allow you to map billing line items from your cloud provider billing line items to ATUM attributes, including IT Towers and Subtowers, the TBM Services hierarchy, as well as a normalized unit of measure.")

**Parent topic:** [Costing Standard](../home.html)

## Related information

- ![](../../../../03-media/apptio-costing-standard/sout.gif)[Send feedback about
  Help Center](productfeedback@apptio.com "(Opens in a new tab or window)")
