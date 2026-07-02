---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Making the most of popular dimensions and metrics within Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Data reference"
source_path: "product/frequently-used-dimensions-and-metrics.html"
images:
  - "images/making_the_most_2016-11-03_09-18-07.jpg"
  - "images/making_the_most_8_image04.jpg"
  - "images/making_the_most__2016-11-03_09-12-37.jpg"
  - "images/making_the_most__cursor_and_account_copyg.jpg"
  - "images/making_the_most__image00.jpg"
  - "images/making_the_most_image01.jpg"
  - "images/making_the_most_image06.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Making the most of popular dimensions and metrics within Cloudability

There are a vast number of dimensions and metrics available in Cloudability reporting. We've
listed some of the most popular and useful below. For a full list, check out our  [Glossary of Dimensions and Metrics](glossary-of-cost-dimensions-and-metrics.html)  .

Service Name (vs. Product Name)

![service vs product screenshot](../../../../03-media/cloudability-premium/images/making_the_most__2016-11-03_09-12-37.jpg)

Cloudability created  Service Name  to standardize mixed naming
conventions for AWS and Azure's  Product Name  field:

- AWS EBS becomes its own top-level product.
- Unified data that was mixed across multiple products:
- AWS tracks Cloudwatch partially as a product and as EC2; this separates Cloudwatch into its own
  service.
- AWS tracks Glacier partially as a product and in S3; this consolidates all Glacier and S3.
- AWS has an import and export service, as well as a Snowball service; Service Name consolidates
  these.
- In some cases, AWS and Azure data shows multiple products for the same services:
  - AWS has multiple names for Support, this consolidates them all into a single AWS Support line
    item.
  - AWS has many administrative charges listed as top-level products like: Amazon Partner Network,
    re:Invent Tickets, etc. These are consolidated into a single AWS Administrative item.
  - Azure has Compute, Microsoft.Compute, and Virtual Machines; these are all the same and
    consolidated under Azure Compute.
- AWS billing files have inconsistent naming schemes for products, sometimes Amazon vs AWS;
  acronyms vs spelled out names. Service Name follows a single pattern of a prefix of AWS followed by
  the name that is seen in the AWS Console menu: EC2, S3, RDS, Kinesis, Lambda, etc. Similarly, Azure
  is the prefix for all Microsoft Azure services.

Any saved reports should use  Service Name  .

Usage Family (vs Usage Type)

![usag family vs product screenshot](../../../../03-media/cloudability-premium/images/making_the_most_2016-11-03_09-18-07.jpg)

Usage Type  is a very granular dimension that exposes specific operational
details of each line item. This dimension can provide a great amount of utility when combined with
 contains  and  does not contain  filter parameters.

Typical values to see returned are  BoxUsage:c3.xlarge  to signify
on-demand usage, or  HeavyUsage:m2.4xlarge  to signify 
Heavy/Reserved  usage, or  EBS:VolumeP-IOPS.piops  to signify
 Provisioned IOPS  usage.

A usage type of  Unknown  is representative of things like the sign-up
charge from an RI purchase.

Usage Family  , in turn, is a standardized dimension created by Cloudability
to consolidate similar values of  Usage Type  into a single high-level
family, for example, Instance Usage, Data Transfer, Storage, or API Request. It's a great place to
start breaking down your spend beyond Accounts and Services.

Item Description

![item description screenshot](../../../../03-media/cloudability-premium/images/making_the_most_8_image04.jpg)

Item Description  is an even more granular dimension that can expose still
further operational detail of each line item. This dimension can also provide a great amount of
utility when combined with  contains  and  does not contain
 filter parameters.

Typical values to see returned are  $0.105 per On Demand Linux c3.large Instance Hour
 to signify on-demand usage, or  $0.070 per GB - next 100 TB/month data
transfer out  to signify data transfer, or  USD 0.5589 hourly fee per
Linux/UNIX, i2.4xlarge instance  to signify RI usage hours, or  $0.0290 per
GB - next 450 TB/month of storage used  to signify S3 costs, or  $0.850 per
Redshift Dense Storage Extra Large (DW1.XL) Compute Node-hour (or partial hour)  to
signify Redshift costs.

An Item Description of  Sign up charge for subscription: ####, planId: ###
 (where ### are actual numbers) is representative of sign-up charges from an RI
purchase. This allows you to create a filter for  item description\_does not contain\_sign
up  to see your compute costs without the upfront fee included.

Transaction Type

![trnsaction type screenshot](../../../../03-media/cloudability-premium/images/making_the_most__cursor_and_account_copyg.jpg)

This dimension was created by Cloudability to discretely break out Recurring Charges like AWS
Support and monthly RI fees, One-Time Charges like RI sign up payments, Credits, Taxes, and Usage
costs. It can be tremendously helpful in determining your RI efficiency and waste, and also helps to
show how Blended and Unblended cost can vary by line item, even when they reach the same month-end
total.

Compute Usage Type

![compute usage type screenshot](../../../../03-media/cloudability-premium/images/making_the_most_image06.jpg)

This dimension very clearly breaks out what instances are running on-demand, spot, reserved, an
RDS node, etc. Running a Cost Analytics report with Compute Usage Type and Item Description as the
only dimensions will surface a complete detailed view.

To see only your compute costs, add a filter for  compute usage type\_not equals\_other
 as the  other  usage type represents costs such as data
transfer, elastic IP mapping, alarm months, read/write hours, GB storage, LoadBalancer GB processed,
shard-hours, PIOPS, magnetic storage, and others.

- In order to see your  Redshift  costs, add a filter for 
  compute usage type\_equals\_node  .
- In order to see your  ElastiCache  costs, add a filter for 
  compute usage type\_equals\_node usage  .
- In order to see your  RDS  costs, add a filter for  compute
  usage type\_equals\_instance usage  .
- In order to see your  Heavy RI  costs, add a filter for 
  compute usage type\_equals\_heavy usage  .
- In order to see your  On-Demand  costs, add a filter for 
  compute usage type\_equals\_box usage  .

On-Demand Hours, Reserved Hours, Reserved Coverage Rate

![hours screenshot](../../../../03-media/cloudability-premium/images/making_the_most__image00.jpg)

These metrics are invaluable in determining exactly which accounts, services, tags, or resources
leveraged your Reserved Instances. The Detailed Billing Report is populated with hourly resolution
across all of these parameters, allowing our analytics platform to group by any Dimension and show
how it took advantage of RI hours over any reporting period chosen.

Adding a filter for  reserved coverage rate\_greater than\_X%  (where
 X%  is a number without the percent symbol) is a great way to see which
areas of your infrastructure could benefit from additional RI coverage.

Instance Type

![instance type screenshot](../../../../03-media/cloudability-premium/images/making_the_most_image01.jpg)

This dimension combines the Instance Family and Instance Size dimensions and presents the full
identifier of the instance, for example,  c3.large  .

In  Cost Analytics  , in order to see only your compute costs, add a
filter for  instance type\_not equals\_none  , as the  none
 instance type represents data transfer, elastic IP mapping, alarm months, read/write
hours, GB storage, LoadBalancer GB processed, shard-hours, PIOPS, magnetic storage,
GET/PUT/POST/COPY/LIST requests, and others.

In Usage Analytics this dimension will return only your EC2 instances.

�

Running Instances and Average Running Instances per Hour

![running instances screenshot](../../../../03-media/cloudability-premium/images/making_the_most_image01.jpg)

The Running Instances metric is a count of all unique instance IDs that were running at one
point during the reporting window. This is not necessarily a count of the instances that are live or
running at the time the report is run. Rather, it's the sum of unique instance IDs that were
running.

Average Running Instances per Hour is an average of the number of instances that were live each
hour of the reporting window.
