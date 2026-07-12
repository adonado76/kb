---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Common Dimension Keys"
breadcrumb:
  - "Cloudability API"
  - "Business Mappings End Point"
  - "Common Dimension Keys"
source_path: "SSVCLNQ/api-v3/appendix.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Common Dimension Keys

This is a list of the most popular DIMENSION keys currently available to use in the expression language. The attribute names are the standard names you use when interacting with these dimensions through all of Cloudability 's API end points. It's worth drawing special attention to how account IDs and account names are handled. For the account/subscription where the expense occurred make sure you include the 'vendor_' prefix. If you don't it will be referring to the associated master payer.

To manage rule changes between dates use the date API attribute. Note that even though we will accept date strings which include a time component we will always resolve these back to the day itself. i.e statements are evaluated at the day level and no-intra day logic applies.

| API Attribute | Description | UI Path* | Example Values | Comments |
| --- | --- | --- | --- | --- |
| container_namespace | Container Namespace cost was associated with | Containers/Namespace | "Team A" |  |
| container_cluster_name | Container Cluster resource cost belongs to | Containers/Cluster Name | "Production Cluster" |  |
| date | The date the expense was incurred | Time/Date | "2018-02-09","2018-02-09T09:00:00Z" | You can provide a date or date-time string. We resolve back to date. |
| day_of_week | what day of the week the cost was incurred | Time/Day of Week | "Thursday" |  |
| enhanced_service_name | The Cloudability name for the vendor service | Vendor/Service Name | "AWS EC2", "Azure Compute", "AWS EBS" | A synthetic and predictable dimension provided by Cloudability |
| engine | Database, data warehouse or cache engine | Usage/Engine | "MySQL", "PostgreSQL", "Memcached", "SQL SERVER" |  |
| instance_category | The category for the instance's family is within | Usage/Instance Category | Compute Optimized, General Purpose, Memory Optimized |  |
| instance_family | The family the instance falls within | Usage/Instance Family | "c5", "r5", "t2", "m3" |  |
| instance_size | The size of the instance | Usage/Instance Size | "large", "nano", "10xlarge" |  |
| instance_type | The full instance type string for the instance. A user friendly representation across vendors and services | Usage/Instance Type | "c5.large", "Standard_E4_v3", "t2.nano" | For RDS we remove the 'db.' prefix to achieve consistency |
| item_description | The detailed description provided by the vendor for the line item | Vendor/Item Description | $0.80 per On Demand Linux m4.4xlarge Instance Hour |  |
| lease_type | Lease type for the instance | Usage/Lease Type | "On Demand", "Reserved", "Spot" |  |
| offering_class | The offering class of the RI applied | Reservation Class | "Standard", "Convertible" | Only applicable to instance hours covered by RIs |
| operating_system | The Operating System for Instance | Usage/Operating System | "Linux", "Windows" |  |
| operation | Descriptive dimension provided by AWS | Usage/Operation | "RunInstances", "GetMetricData" |  |
| reservation_identifier | The unique ID for the reservation | Usage/Reservation ID | "93d06157-7eaa-419a-8a54-0a85bb0864f3" | Applies to Sign Up charges, recurring items and instance hours that consume RIs. |
| region | The official vendor region | Vendor/Region | "ap-southeast-2", "us-eas-2", "australiasoutheast" | Region names are specific to vendor |
| region_zone | The AZ provided by the vendor | Vendor/Availability Zone | "ap-southeast-2a", "us-east-1b" |  |
| resource_identifier | The unique ID for the resource provided by the vendor | Usage/Resource ID | "i-a37ef5dcf51cd8c1a", "vol-0o873bca0f2d0c898" |  |
| seller | Who sold the service | Vendor/Seller | "AWS Marketplace", "Amazon", "Azure" | A synthetic dimension to describe who actually sold the service, special focus on marketplace |
| service_name | The name of the service as provided by the vendor. For a easier and normalised version use enhanced_service_name instead | Vendor/Product Name | "Amazon Elastic Compute Cloud", "Microsoft.Compute", "Microsoft.Storage" |  |
| tenancy | The tenancy for EC2 instances | Tenancy | "shared", "host", "dedicated" | see AWS docs |
| transaction_type | The high level type of transaction | Usage/Transaction Type | "usage", "recurring", "one-time" |  |
| usage_family | The family of usage | Usage/Usage Family | "Instance Usage", "Data Transfer", "Storage", "Load Balancer Usage", "Support" | A synthetic dimension that describes the type of usage across cloud services |
| usage_type | Detailed descriptive dimension as provided by vendor | Usage/Usage Type | "APS2-EBS:VolumeUsage.gp2", "APS2-BoxUsage:m4.2xlarge" |  |
| vendor | The cloud vendor name | Vendor/Vendor | "Amazon", "Azure" |  |
| vendor_account_identifier | The unique identifier the vendor provides for the account or subscription where the cost occurred. | Vendor/Account ID | "111122223333" for AWS "0d3d81f1-41f9-4f1a-8b3c-856b6822ff4f" for Azure | No dashes '-' between digits for AWS, however they are required for Azure. |
| vendor_account_name | The name of the account or subscription that you have set in the cloud vendor. | Vendor/Account Name | Production Account, Cyril Rioli's Account, Client Services | A simple string as you entered with the vendor |
