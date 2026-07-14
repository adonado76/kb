---
source_system: "apptio-cloudability-standard"
practice: "finops"
language: "en"
doc_type: "cloudability-standard"
consolidated_file: "10-Cloudability-Data-reference"
source_files_count: 4
last_updated: "2026-07-13"
---

# 10-Cloudability-Data-reference

## Comparing Data Between Report UI and CSV Exports

<!-- sub-header -->
- **breadcrumb:** Data reference > Comparing Data Between Report UI and CSV Exports
- **source_path:** SSVCLNQ/product/comparing-data-between-report.html
- **original_file:** reference-comparing-data-between-report-ui-csv-exports.md
- **images:** []

## Comparing Data Between Report UI and CSV Exports

When you export your reports in Cloudability , you may observe:

- The unit of measurements for some metrics do not match between report UI and exported CSV data.
- A few column headers do not match between report UI and exported CSV data.

Difference in Unit of Measurements (UoM) between report UI and exported CSV data

Exported data in CSV may show a different unit of measurement for some metrics. For some measures such as GB, and percentage, we want to provide values as decimals with full available precision and without formatting, so that you can format as desired for programmatic uses and don't have to try to "parse away" the formatting. However, providing such “raw numbers” with full decimal precision in the report UI would make the UI less usable.

Difference in Column Headers between report UI and Exported CSV data

Refer to this table to understand the mapping of those column headers that differ between exported CSV data and report UI:

| Header in Exported CSV | Header in Report UI | Remarks |
| --- | --- | --- |
| invoiced_cost | Cost (Total Blended) | � |
| blended_rate | Rate (Blended) | � |
| cost_before_tax | Cost (Total Unblended Before Taxes) | � |
| Iops | IOPS Months | � |
| gb_months | GiB Months | � |
| byte_hours | GiB Hours | � |
| Month | Month (Category) | � |
| service_key | Product Code | � |
| service_name | Product Name | � |
| region_zone | Availability Zone | � |
| account_identifier | Payer Account ID | � |
| account_name | Payer Account Name | � |
| vendor_account_identifier | Account ID | � |
| group_name [x] | Account Group [x] | 'x’ stands for the cardinality of Account Groups (For example: Account Group 1, Account Group 2, Account Group 3) in your Cloudability environment. |
| is_capex | One-time charges | � |
| Week | Week (Category) | � |
| bytes_transferred | Data Transfer (GiB) | � |
| unblended_cost | Cost (Total) | � |
| unblended_rate | Rate (Unblended) | � |
| reserved_utilization_rate | Reserved Coverage Rate | � |
| resource_identifier | Resource ID | � |
| resource_identifier_count | Resource Count | � |
| total_amortized_cost | Cost (Amortized) | � |
| reservation_identifier | Reservation ID | � |
| enhanced_service_name | Service Name | � |
| year_month | Month (Year) | � |
| year_week | Week (Year) | � |
| cost_adjusted | Cost Adjustment | � |
| adjusted_cost | Cost (Adjusted) | � |
| Category[x] | Business Dimension [x] | ‘x’ stands for the cardinality of Business Dimensions (For example: Business Dimension 1, Business Dimension 2, Business Dimension 3) in your Cloudability environment. |
| categorykey[x] | Business Dimension Key [x] | ‘x’ stands for the cardinality of Business Dimension Keys (For example: Business Dimension Key 1, Business Dimension Key 2, Business Dimension Key 3) in your Cloudability environment. |
| total_adjusted_amortized_cost | Cost (Adjusted Amortized) | � |
| public_on_demand_cost | Cost (List) | � |
| offering_class | Reservation Class | � |
| container_cluster_name | Cluster Name | � |
| container_namespace | Namespace | � |
| ancestry_numbers | GCP Ancestry Numbers | � |
| amortized_fairshare_cost | Fairshare Cost (Amortized) | � |
| amortized_utilized_cost | Utilized Cost (Amortized) | � |
| amortized_idle_cost Idle | Cost (Amortized) | � |
| adjusted_fairshare_cost | Fairshare Cost (Adjusted) | � |
| adjusted_utilized_cost | Utilized Cost (Adjusted) | � |
| adjusted_idle_cost | Idle Cost (Adjusted) | � |
| adjusted_amortized_fairshare_cost | Fairshare Cost (Adjusted Amortized) | � |
| adjusted_amortized_utilized_cost | Utilized Cost (Adjusted Amortized) | � |
| adjusted_amortized_idle_cost Idle | Cost (Adjusted Amortized) | � |

---

## Glossary of Cost Dimensions and Metrics

<!-- sub-header -->
- **breadcrumb:** Data reference > Glossary of Cost Dimensions and Metrics
- **source_path:** SSVCLNQ/product/glossary-of-cost-dimensions-and-metrics.html
- **original_file:** reference-glossary-cost-dimensions-metrics.md
- **images:** []

## Glossary of Cost Dimensions and Metrics

Cloudability's reporting tools allow you to analyze your cost and usage data to figure out exactly where your money is going. The dimensions and metrics available in your reports are identified below.

### Cost and Usage Dimensions

- Account ID : The unique identifier related to an AWS Account, Azure Subscription, GCP Project or OCI Tenancy.
- Account Name : The name given by the customer that's attached to each AWS Account, Azure Subscription, GCP Project or OCI Tenancy.
- ATUM Tower : Represents a high-level IT view of your organization’s technology functions, providing a broad cost categorization. Examples values include Network, Platform, End User and Application.
- ATUM Sub-Tower : Offers a more detailed categorization under each tower, for example breaking Platform down into Middleware and Database.
- ATUM Service Type : Represents a high-level business view of your cloud spend. This is the top-level categorization into services with values such as Platform Services, Delivery Services and End User Services.
- ATUM Service Category : Offers a more detailed categorization under each service type, for example breaking Delivery Services down into Operations, Security and Compliance, and Support.
- ATUM Service Name : This is the most detailed categorization related to services, for example breaking the Operations service category down into Event Management, IT Service Management, and Deployment and Administration.
- Availability Zone : A combination of the region and zone in which a resource exists. For example, us-east-1a.
- Azure Reservation Order Name : The name or description of the product or service that was ordered or consumed presently supported only for Azure.
- Cluster Name : The Kubernetes "Cluster Name" that the underlying cost items - such as VM, storage and network costs - belong to. The value matches the name setup by your admin when provisioning the cluster within Cloudability.
- Cluster Name : This is a container-specific dimension and is not currently supported.
- Compute Usage Type : Handy Cloudability-defined dimension for understanding the type of compute for some AWS services such as EC2 and RDS. This dimension can help the user quickly understand the region and category (such as Spot, Dedicated Host, Mirror Usage) of compute.
- Date : The calendar date - formatted "Mon DD, YYYY" (Aug 9, 2022).
- Day : The numeric calendar day (for example, "Aug 9, 2022" => 9).
- Day of Week : The day of week (for example, Monday).
- Engine : The database or cache engine (for example, Oracle, SQL Server, MySQL or Redis).
- Instance Category : The category of VM or Database an instance belongs to. Common categories include General Purpose, Compute Optimized and Memory Optimized.
- Instance Family : The family of VM or Database an instance belongs to. This will typically form the prefix to the full instance type definition. For AWS, family includes the type and generation (e.g., m6a, c6i, t3) for Azure it's the series (e.g., A,B,D) and for GCP it's the "series type" (e.g., standard, highmem). Data is not currently available for OCI.
- Instance Size : The size of VM or Database. This is correlated to key resource attributes such as the number of CPUs and available memory. Example values - large, xlarge, 2xlarge for AWS; 2,4,8 for Azure; n1-8-vcpu, n1-16-vcpu for GCP. Data is not currently available for OCI.
- Instance Type : The full identifier of the type of VM or Database instance, capturing both the family and size. This value forms one complete component of the product SKU (used alongside location and OS). For example, c6g.large for AWS, Standard_D2_v3 for Azure and standard.c2-8-vcpu for GCP. Data is not currently available for OCI.
- Invoice Date : The invoice date for any cost item as provided by the cloud vendor. This is reported in "Mon DD, YYYY" format. Cloud consumption during the month is usually given an invoice date of the first day of that month.
- Invoice ID : The invoice ID that corresponds to any charged cost item, as provided by AWS. For the current month, where the cost is not invoiced yet, you will see a value of "Estimated". Data is not currently available for Azure, GCP and OCI.
- Item Description : The most descriptive text available from each cloud vendor detailing each cost item. For the latest detailed billing exports this corresponds to "LineItemDescription" for AWS, "ProductName" + "additionalInfo" for Azure and "sku.description" for GCP and “product/Description” for OCI.
- Lease Type : The payment mode for the reported cost items, defaulting to "On-Demand". Valid values are: On-Demand, Savings Plan, Reserved and Spot. This is a reporting dimension defined by Cloudability to support multi-cloud cost categorization.
- Month (Category) : The month any cost item was incurred, formatted "Mon". Examples "Jun", "Jul", "Aug". This is useful for looking at costs by month for any year (such as show costs that occurred in July of any year).
- Month (Year) : The month and year of any cost item (formatted Month YYYY) useful for proper chronological sorting. Examples: July 2021, September 2022.
- Namespace : The Kubernetes “Namespace” assigned to underlying cost items that belong to a Kubernetes cluster. The cost amount allocated to each Namespace value is calculated by Cloudability through analyzing container resource utilization. Individual cloud resources, such as EC2 instances, are often split across multiple Namespaces due to their multi-tenant nature.
- Namespace : This is a container-specific dimension and is not currently supported.
- Operating System : The operating system for VMs as reported by the cloud vendors for billing purposes. Example values: Linux, Windows, Red Hat Enterprise Linux.
- Operation : This dimension shows the specific action taken upon a resource. For example, if the network is transferring data in or out of a VM instance. When paired with Resource ID, this helps customers understand both the source and actions that contributed to the cost. For the latest detailed billing exports this corresponds to "Operation" for AWS, "meterName" for Azure and "skuItem.categoryResourceGroup" for GCP and “cost/productSku” for OCI.
- Part Number : Identifier used to get specific meter pricing presently supported only for Azure and OCI.
- Payer Account ID : The unique identifier related to the AWS management account, Azure EA/MCA agreement or GCP Billing Account. AWS member accounts, Azure subscriptions and GCP projects and OCI tenancies are typically consolidated under these "payer accounts".
- Payer Account Name : The name related to the AWS management account, Azure EA/MCA agreement or GCP Billing Account or OCI Root Tenancy. Depending on your situation this value may fall back to the unique billing ID.
- Product Name : The official product name as provided by the vendor (for example, Amazon Elastic Compute Cloud, GCP Cloud Storage, Microsoft.Compute or OCI Compute).
- Region : The region in which a resource exists or a usage charge occurred, for example: us-east-1 for AWS, US East for Azure and us-east1 for GCP and us-ashburn-1 for OCI.
- Reservation Class : The commitment offering tied to any cost item. Example values include “standard” and “convertible” reserved instances, “EC2InstanceSavingsPlans” and “ComputeSavingsPlans” for savings plans.
- Reservation ID : The unique ID of the commitment (such as reserved instance and savings plan) tied to any cost item as provided by the cloud vendor. This is particularly useful for understanding exactly which commitment(s) was consumed by a subset of usage or specific VM.
- Reservation Name : The name of the purchased reservation instance.
- Resource ID : This is a unique identifier used by the vendor to distinguish the actual resources that are used. For example, this would be the instance ID of the VM, the name of the storage bucket, or an ID of the data volume. For GCP, we currently use the SKU ID to populate the Resource ID.
- Seller : The official seller of services. Using this dimension allows you to separate marketplace charges from your other cloud costs.
- Service Name : A dimension created by Cloudability that standardizes product naming conventions for AWS, Azure, GCP and OCI: AWS EBS becomes its own top-level product. Unified data that was mixed across multiple products: AWS tracks Cloudwatch partially as a product and as EC2. This separates Cloudwatch into its own service AWS tracks Glacier partially as a product and in S3. This consolidates all Glacier and S3 AWS has an import and export service, as well as a Snowball service. Service Name consolidates these. In some cases, AWS and Azure's data show multiple products for the same services: AWS has multiple names for Support. This consolidates them all into a single AWS Support line item. AWS has many administrative charges listed as top-level products like Amazon Partner Network, re:Invent Tickets, etc. These are consolidated into a single AWS Administrative item. Azure has Compute, Microsoft.Compute, and Virtual Machines. These are all the same and consolidated under Azure Compute. In some cases, AWS and GCP mirror each other fairly closely regarding the names of their services: GCP uses terms like Google Compute Engine and Google App Engine (AWS EC2), Google Cloud SQL, Google Cloud Firestore, and Google Cloud Bigtable (AWS RDS and DynamoDB). AWS billing files have inconsistent naming schemes for products. For example, the use of acronyms as opposed to full names (Amazon vs AWS). Service Name follows a single prefix pattern. AWS is the prefix for all Amazon Web Services. This is followed by the name that is seen in the AWS Console menu (for example, EC2, S3, RDS, Kinesis, Lambda, etc.). Azure is the prefix for all Microsoft Azure services. This is a reporting dimension defined by Cloudability to support multi-cloud cost categorization.
- Tenancy : AWS specific dimension identifying the tenancy of EC2 instances. Three valid values are shared, host and dedicated. "shared" is the default value.
- Transaction Type : The type of transaction for any cost item. Valid values are Usage, Recurring Charge (e.g., enterprise support charges, unused reserved instances), One Time (e.g., upfront reserved instance purchases), Tax and Credit. This is a reporting dimension defined by Cloudability to support multi-cloud cost categorization.
- Usage Type : Specifies the operational details of the usage line item. For example. USW1-BoxUsage:m2.2xlarge describes Amazon EC2 High-Memory Double ExtraLarge Instance box usage in the US West (Oregon) region.
- Usage Family : This is a standardized dimension defined by Cloudability to categorize the high-level types of cloud usage across providers. Example values include Instance Usage, Data Transfer, Storage, API Request, Network, Load Balancer Usage, Support and System Operation. Used together with the Service Name reporting dimension, Usage Family can help users to quickly understand what is driving their cloud spend.
- Vendor : The cloud vendor associated with the cost item. Valid values are Amazon, Azure, GCP and OCI.
- Week (Year) : The week and year of any cost item (formatted YYYY-WW) useful for proper chronological sorting. Examples: 2021-06, 2022-52.
- Week (Category) : The week any cost item was incurred, formatted "WW". Examples "01", "15", "52". This is useful for looking at costs by the week for any year (such as show costs that occurred in week 1 of any year).
- Year : The calendar year any cost item was occurred, formatted YYYY (for example, 2022).
- Zone : This field is specific to AWS, it corresponds to the letter for a specific zone in which an instance exists or a usage charge occurred within an Availability Zone. For example, the AWS Zone "a" corresponds to the Availability Zones "eu-west-1a" or "ap-southeast-2a" etc. This field is not used for Azure, GCP and OCI.

### Cost and Usage Metrics

- Cost (List) : This metric represents the cost of items that customers are charged at the public on-demand rate. This means any commitments (reserved instances and savings plans), spot instance pricing, and custom pricing (typically enterprise discounts) are not considered in this metric. The metric is derived by combining data available in the vendor’s detailed billing files and their API-based price sheets, and is currently implemented for all AWS services. For Azure, the “Cost (List)" metric is supported for on-demand services. Additionally, your commitment instance usage under “Reserved” and “Savings Plan” lease types are supported for select services – currently Azure Compute and Azure Database only.

- Cost (Total) : This is the default cost metric throughout Cloudability. It is a “cash” metric and simply represents the invoiced amount associated with any cost item as reported by the cloud vendor. For AWS, this corresponds to the lineItem/UnblendedCost column of the CUR file; for Azure, the CostInBillingCurrency column of the standard billing export; and for GCP, the cost attribute from the BigQuery table ; and for OCI, the cost/myCost column in the cost report. How “used” portions of Costs are allocated for RIs: Where AWS does not allocate the "used" portion of RIs to resources for UnblendedCost, Cloudability allocates it to those resources that benefitted from the RIs. Otherwise, charges would be allocated to the account in which the RI was purchased. You can allocate better showback or chargeback allocations due to this enhancement, which will increase transparency of actual usage.
- Cost (Total Blended) : This cost metric is specific to AWS and corresponds to the lineItem/BlendedCost column of the CUR file. This metric “blends” the impact of reserved instances and savings plans. This can lead to unexpected figures. Therefore, it is recommended to use either Cost (Total) or Cost (Amortized).
- Cost (Amortized) : In contrast to cost (total) - which is a “cash” metric - cost (amortized) is an “accrual” cost metric, representing the consumed cost during any period. This metric is handy for ensuring commitments such as reserved instances and savings plans (including upfront payments) are allocated to the time and place they are consumed. For AWS items, Cloudability relies on a combination of columns in the CUR to surface this value. For Azure the CostInBillingCurrency column of the amortized billing export is used. Note: Upfront commitment line items show as $0 with this metric.
- Cost (Adjusted) : Built from the Cost (Total) metric, this metric adjusts the figures to allow for any custom pricing rules. This metric is commonly used with AWS data so that the enterprise discounts can be factored in consistently at the usage line item level rather than appear in bulk at month’s end. This metric only appears for Cloudability customers who have turned on the custom pricing module.
- Cost (Adjusted Amortized) : Built from the Cost (Amortized) metric, this metric adjusts the figures to allow any custom pricing rules. This metric is most commonly used with AWS data so that enterprise discounts can be factored in consistently at the usage line item level rather than appear in bulk at month’s end. This metric only appears for Cloudability customers who have turned on the custom pricing module.
- Cost Adjustment : The amount by which the cost was adjusted.

This is not available unless Custom Pricing is enabled.

- Data Transfer (GiB) : Amount of data transferred in a particular time period.
- GiB Hours : A gibibyte-hour refers to the number of gibibytes stored on a cloud platform in a particular hourly period.

- GiB Months : It refers to the number of gibibytes of a resource for AWS, Azure, GCP and OCI in a particular monthly period.
- I/O Requests : Describes the number of data requests from a database service.
- IOPS Months : The storage input and output operations per second associated with storage services.
- On Demand Hours : The amount of on-demand computing hours used during the reporting period. For more information, see Frequently used dimensions and metrics .
- Rate (Blended) : For Consolidated Billing accounts, the effective rate for the line item calculated as an average of the cost of identical instances operating in that hour in the same Availability Zone.
- Rate (Unblended) : The cost per hour for a line item. This is summarized across the hours of a day. For additional information, see Emerge .
- Requests : The number of computing resources used in the units specified by each service. For example, your service may determine pricing by the amount of storage, number of requests, or hours of operation. For more information about how usage is calculated, click AWS Pricing .
- Reserved Coverage Rate : The percentage of total usage hours during the period which had Reserved Instances applied. For more information, see Frequently used dimensions and metrics .
- Reserved Hours : The number of reserved computing hours used during the reporting period. For more information, see Frequently used dimensions and metrics .
- Resource Count : This new metric indicates the count of unique resources in a given time frame. This allows customers to understand the number of assets they control and how it ebbs and flows over time.
- Usage Hours : The number of computing resources used in the units specified by each service. For example, your service may determine pricing by the amount of storage, number of requests, or hours of operation.
- Usage Quantity : The quantity consumed for the cost item. The unit is tied to the specific SKU and how it is charged. For example, this number will represent the number of instance hours consumed for VMs, GiB-months for storage and GiB for data transferred. For AWS and Azure spend this metric compliments the rate (unblended) and cost (total) metrics when used together in a report to explain the figure the cloud vendor charged you.

### Sustainability Metrics

- Estimated Carbon Emissions (MTCO2e) : This metric captures the estimated carbon emissions in metric tons of carbon dioxide equivalents.
- Power Consumed (kWh) : Power consumed in kilowatt hours.
- Operational Carbon Emission (MTCO2e) - This metrics represents the carbon emissions generated during the day-to-day operation of cloud services. It primarily comes from the electricity used to power and cool data centers while running workloads.
- Embodied Carbon Emission (MTCO2e) - This metrics represents the share of carbon emissions tied to the production and lifecycle of cloud infrastructure. In the cloud context, it’s estimated by allocating a portion of the total embodied emissions of physical servers and equipment based on your specific usage.

---

## Glossary of utilization dimensions and metrics

<!-- sub-header -->
- **breadcrumb:** Data reference > Glossary of utilization dimensions and metrics
- **source_path:** SSVCLNQ/product/glossary-of-utilization-dimensions-and-metrics.html
- **original_file:** reference-glossary-utilization-dimensions-metrics.md
- **images:** []

## Glossary of utilization dimensions and metrics

Cloudability's reporting tools allow you to slice and dice your utilization data so you can figure out exactly how your infrastructure is being used. Divided into two sections, the dimensions and metrics that are available in your reports are identified below.

1. Utilization dimensions
1. Utilization metrics

Utilization dimensions

- Account ID : The 12-digit AWS number used to identify an account. For the cost analytics of consolidated billing accounts, this refers to a linked account.
- Account Name : The name associated with an AWS account. For the cost analytics of consolidated billing accounts, this refers to a linked account.
- AMI : This dimension filters the data you request for all instances running this EC2 Amazon Machine Image (AMI). Available for instances with Detailed Monitoring enabled.
- Architecture : The base architecture of the instance hardware (for example, x86, x86_64, i386).
- Availability Zone : A combination of the region and zone in which an instance exists or a usage charge occurred (for example, us-east-1a).
- CPU Clock Speed : The base clock speed of the processors on the instance (GHz).
- Current State : The current state of the EC2 instance (for example, running, stopped). See the AWS Instance Lifecycle User Guide for additional information.
- Date : The calendar date (for example, YYYY-MM-DD).
- Day : The day of the month.
- Day of Week : The weekday (for example, Monday).
- Days Alive : The total number of days since the instance was initially launched.
- DNS Name : The public DNS name associated with a particular EC2 instance (for example, ec2-54-205-210-122.compute-1.amazonaws.com).
- Hour : The numeric hour of the day (for example, 1pm => 13).
- Instance Category : The instance category (for example, General Purpose, Compute Optimized, etc.).
- Instance ID : The ID associated with a particular AWS instance.
- Instance Name : The name of a particular EC2 instance.
- Instance Type : The size of an instance (for example, m1.medium). For more information, see Frequently used dimensions and metrics .
- IP Address : The IP address associated with a particular EC2 instance.
- Last Ran : The date the resource last ran.
- Launch Date : The launch date of a particular instance (for example, 2014-01-22).
- Launch Day : The launch day of a particular instance (for example, Monday).
- Launch Day of Week : The day of the week that a particular instance was launched (for example, Monday).
- Launch Month : The numeric month in which an instance was launched (for example, 1 => January).
- Launch Time : The date and time value describing when an instance was launched (for example, 2000-01-01T22:46:34Z).
- Launch Week : The week of the year in which an instance was launched (i.e. 52 would indicate the last week in a calendar year).
- Launch Year : The year in which an instance was launched.
- Month : The numeric calendar month (for example, 2014-1-15 => 12).
- OS : The operating system of an instance (for example, Linux).
- Private DNS Name : Amazon EC2 instances need IP addresses to communicate. Public IP addresses enable communication over the internet.
- Private IP : Amazon EC2 instances need IP addresses to communicate. Private IP addresses enable communication.
- Processor Architecture : The CPU architecture.
- Region : Region in which an instance exists or a usage charge occurred (for example, US East).
- Security Group IDs : A security group acts as a firewall that controls the traffic for one or more instances. Each security group is identified by a unique ID (for example, sg-xxxxxxxx).
- Security Groups Names : A security group acts as a firewall that controls the traffic for one or more instances. Each security group requires a unique name (limit 255 characters).
- Storage Type : No content is given for this entry yet
- Subnet ID : The subnet ID associated with an EC2 instance. If there is a subnet ID listed, the instance is in a VPC.
- Virtualization : The virtualized environment, if any, running on a given instance.
- Week : The numeric calendar week.
- Year : The calendar year (for example, 2014).
- Zone : Availability Zone in which an instance exists or a usage charge occurred (for example, 1a).

Utilization metrics

- Avg CPU Utilization : The percentage of allocated EC2 compute units that are currently in use on the instance. This metric identifies the processing power required to run an application upon a selected instance.
- Avg Estimated Cost : The average estimated cost of an instance based on the selected timeframe (utilization hours: average estimated hourly instance cost).
- Avg Hourly Cost : The average hourly cost based on the base rates established by AWS.
- Avg Hourly Cost Per Instance : The average hourly cost per instance based on the base rates established by AWS.
- Avg Memory Utilization : The average percentage of memory allocated by applications and the operating system for an instance. This metric excludes the memory in cache and buffers.
- Avg Running Instances Per Hour : The average number of running instances per hour. For more information, see Frequently used dimensions and metrics .
- Bandwidth In : The number of bytes received on all network interfaces by the instance. This metric identifies the volume of incoming network traffic to an application on a single instance.
- Bandwidth Out : The number of bytes sent out on all network interfaces by instance. This metric identifies the volume of outgoing network traffic to an application on a single instance.
- Burst Balance : Provides information about the percentage of I/O credits (for gp2) or throughput credits (for st1 and sc1) remaining in the burst bucket. Used with General Purpose SSD (gp2), Throughput Optimized HDD (st1), and Cold HDD (sc1) volumes only.
- Cost (Estimated On-demand) : The estimated cost based on the values found in the AWS Cost Allocation File.
- CPU Total (blue line) : The normalized percentage of maximum CPU utilization in the indicated hour, based on the maximum instance count for the entire ASG in the time window of 10 or 30 days. Example: If there are five instances in an ASG and all 5 instances are utilizing 100% of their CPU then the CPU total is 100%. If one instance is utilizing 100% of its CPU and the other four instances are utilizing 0% of their CPUs then the CPU total is 20%.
- CPU Utilization (Max) : The maximum percentage of CPU Utilization reached for the hour. For EC2, this is the maximum percentage of allocated EC2 compute units in use for an instance. When aggregated, this reports the peak across all instances and across the entire time period.
- Disk Access : Total bytes read and written for all ephemeral disks available to the instance (if your instance uses Amazon EBS, see Amazon EBS Metrics ).
- Disk I/O : Completed read and write operations from all ephemeral disks available to the instance.
- Disk Read Access : Total bytes read from all ephemeral disks available to the instance.
- Disk Read I/O : Completed read operations from all ephemeral disks available to the instance.
- Disk Write Access : Total bytes written to all ephemeral disks available to the instance.
- Disk Write I/O : Completed write operations to all ephemeral disks available to the instance.
- GPU Total (%) :- GPU Total (%) is handled in the same manner as CPU Total (%). (Refer to Rightsizing for AWS EC2 ASG )
- GPU Memory Total (%) : GPU Memory Total (%) is handled in the same manner as CPU Memory Total (%). (Refer to Rightsizing for AWS EC2 ASG )
- GPU Memory Utilization : Percentage of time over a sample period where memory was being written or read. Note: For successful results with GPU metrics, make sure you have configured minimal GPU metrics as a prerequisite.
- GPU Utilization : Percentage of time over a sample period where one or more kernels on the GPU was running.
- Hours Since Launch : The number of hours elapsed since an instance initially launched.
- Instance Count: CPU Total (red line) : The total number of instances running for this ASG in the indicated hour.
- Instance Count: Network Max (red line) : The total number of instances running for this ASG in the indicated hour.
- Instance Count: Memory Total(red line) : The total number of instances running for this ASG in the indicated hour.
- Launched Instances : The total number of launched instances in a given time period.
- Memory : The amount of memory available to the instance.
- Memory Total (blue line) : The normalized percentage of maximum memory utilization in the indicated hour, based on the maximum instance count for the entire ASG in the time window of 10 or 30 days. Example: If there are five instances in an ASG and all five instances are utilizing 100% of their memory, then the Memory total is 100%. If one instance is utilizing 100% of its memory and the other four instances are utilizing 0% of their memory then the Memory total is 20%.
- Network Max (blue line) : The total number of bits per second utilized based on the maximum instance count for the entire ASG in the indicated hour.
- Recommended: CPU Total (yellow dashed line) : The recommended normalized percentage of CPU utilization allocation for the entire ASG in the indicated hour.
- Recommended: Memory Total(yellow dashed line) : The recommended normalized percentage of memory utilization allocation for the entire ASG in the indicated hour.
- Recommended: Network Total (yellow dashed line) : The recommended network allocation for the entire ASG in the indicated hour.
- Recommended instance count: CPU Total (yellow line, displayed on hover) : The total number of instances recommended for this ASG in the indicated hour.
- Recommended instance count: Memory Total (yellow line, displayed on hover) : The total number of instances recommended for this ASG in the indicated hour.
- Storage : The amount for storage available to the instance. This number will not include EBS.
- Storage Devices : The total number of storage devices associated with an instance in a given time period.
- Recommended instance count (yellow line, displayed on hover) : The total number of instances recommended for this ASG in the indicated hour.
- Total Bandwidth : Total bytes transferred by a particular instance.
- Unique Instance Count : The total number of unique instances in a running state during a given time period.
- Utilization Hours : The total number of usage hours on an instance in a particular timeframe.
- Volume Consumed Read Write Ops : The total amount of read and write operations (normalized to 256K capacity units) consumed in a specified period of time. Used with Provisioned IOPS SSD volumes only.
- Volume Throughput Percentage : The percentage of I/O operations per second (IOPS) delivered of the total IOPS provisioned for an Amazon EBS volume. Used with Provisioned IOPS SSD volumes only. Note: This metric is not supported for Multi-Attach enabled volumes.

---

## Making the most of popular dimensions and metrics within Cloudability

<!-- sub-header -->
- **breadcrumb:** Data reference > Making the most of popular dimensions and metrics within Cloudability
- **source_path:** SSVCLNQ/product/frequently-used-dimensions-and-metrics.html
- **original_file:** reference-making-most-popular-dimensions-metrics-within-cloudability.md
- **images:**
  - 03-media/apptio-cloudability-standard/making_the_most__2016-11-03_09-12-37.jpg
  - 03-media/apptio-cloudability-standard/making_the_most_2016-11-03_09-18-07.jpg
  - 03-media/apptio-cloudability-standard/making_the_most_8_image04.jpg
  - 03-media/apptio-cloudability-standard/making_the_most__cursor_and_account_copyg.jpg
  - 03-media/apptio-cloudability-standard/making_the_most_image06.jpg
  - 03-media/apptio-cloudability-standard/making_the_most__image00.jpg
  - 03-media/apptio-cloudability-standard/making_the_most_image01.jpg

## Making the most of popular dimensions and metrics within Cloudability

There are a vast number of dimensions and metrics available in Cloudability reporting. We've listed some of the most popular and useful below. For a full list, check out our Glossary of Dimensions and Metrics .

Service Name (vs. Product Name)

![service vs product screenshot](../images/making_the_most__2016-11-03_09-12-37.jpg)

- AWS EBS becomes its own top-level product.
- Unified data that was mixed across multiple products:
- AWS tracks Cloudwatch partially as a product and as EC2; this separates Cloudwatch into its own service.
- AWS tracks Glacier partially as a product and in S3; this consolidates all Glacier and S3.
- AWS has an import and export service, as well as a Snowball service; Service Name consolidates these.
- In some cases, AWS and Azure data shows multiple products for the same services: AWS has multiple names for Support, this consolidates them all into a single AWS Support line item. AWS has many administrative charges listed as top-level products like: Amazon Partner Network, re:Invent Tickets, etc. These are consolidated into a single AWS Administrative item. Azure has Compute, Microsoft.Compute, and Virtual Machines; these are all the same and consolidated under Azure Compute.
- AWS billing files have inconsistent naming schemes for products, sometimes Amazon vs AWS; acronyms vs spelled out names. Service Name follows a single pattern of a prefix of AWS followed by the name that is seen in the AWS Console menu: EC2, S3, RDS, Kinesis, Lambda, etc. Similarly, Azure is the prefix for all Microsoft Azure services.

Any saved reports should use Service Name .

Usage Family (vs Usage Type)

![usag family vs product screenshot](../images/making_the_most_2016-11-03_09-18-07.jpg)

Usage Type is a very granular dimension that exposes specific operational details of each line item. This dimension can provide a great amount of utility when combined with contains and does not contain filter parameters.

Typical values to see returned are BoxUsage:c3.xlarge to signify on-demand usage, or HeavyUsage:m2.4xlarge to signify Heavy/Reserved usage, or EBS:VolumeP-IOPS.piops to signify Provisioned IOPS usage.

A usage type of Unknown is representative of things like the sign-up charge from an RI purchase.

Usage Family , in turn, is a standardized dimension created by Cloudability to consolidate similar values of Usage Type into a single high-level family, for example, Instance Usage, Data Transfer, Storage, or API Request. It's a great place to start breaking down your spend beyond Accounts and Services.

Item Description

![item description screenshot](../images/making_the_most_8_image04.jpg)

Item Description is an even more granular dimension that can expose still further operational detail of each line item. This dimension can also provide a great amount of utility when combined with contains and does not contain filter parameters.

Typical values to see returned are $0.105 per On Demand Linux c3.large Instance Hour to signify on-demand usage, or $0.070 per GB - next 100 TB/month data transfer out to signify data transfer, or USD 0.5589 hourly fee per Linux/UNIX, i2.4xlarge instance to signify RI usage hours, or $0.0290 per GB - next 450 TB/month of storage used to signify S3 costs, or $0.850 per Redshift Dense Storage Extra Large (DW1.XL) Compute Node-hour (or partial hour) to signify Redshift costs.

An Item Description of Sign up charge for subscription: ####, planId: ### (where ### are actual numbers) is representative of sign-up charges from an RI purchase. This allows you to create a filter for item description_does not contain_sign up to see your compute costs without the upfront fee included.

Transaction Type

![trnsaction type screenshot](../images/making_the_most__cursor_and_account_copyg.jpg)

This dimension was created by Cloudability to discretely break out Recurring Charges like AWS Support and monthly RI fees, One-Time Charges like RI sign up payments, Credits, Taxes, and Usage costs. It can be tremendously helpful in determining your RI efficiency and waste, and also helps to show how Blended and Unblended cost can vary by line item, even when they reach the same month-end total.

Compute Usage Type

![compute usage type screenshot](../images/making_the_most_image06.jpg)

This dimension very clearly breaks out what instances are running on-demand, spot, reserved, an RDS node, etc. Running a Cost Analytics report with Compute Usage Type and Item Description as the only dimensions will surface a complete detailed view.

- In order to see your Redshift costs, add a filter for compute usage type_equals_node .
- In order to see your ElastiCache costs, add a filter for compute usage type_equals_node usage .
- In order to see your RDS costs, add a filter for compute usage type_equals_instance usage .
- In order to see your Heavy RI costs, add a filter for compute usage type_equals_heavy usage .
- In order to see your On-Demand costs, add a filter for compute usage type_equals_box usage .

On-Demand Hours, Reserved Hours, Reserved Coverage Rate

![hours screenshot](../images/making_the_most__image00.jpg)

These metrics are invaluable in determining exactly which accounts, services, tags, or resources leveraged your Reserved Instances. The Detailed Billing Report is populated with hourly resolution across all of these parameters, allowing our analytics platform to group by any Dimension and show how it took advantage of RI hours over any reporting period chosen.

Adding a filter for reserved coverage rate_greater than_X% (where X% is a number without the percent symbol) is a great way to see which areas of your infrastructure could benefit from additional RI coverage.

Instance Type

![instance type screenshot](../images/making_the_most_image01.jpg)

This dimension combines the Instance Family and Instance Size dimensions and presents the full identifier of the instance, for example, c3.large .

In Cost Analytics , in order to see only your compute costs, add a filter for instance type_not equals_none , as the none instance type represents data transfer, elastic IP mapping, alarm months, read/write hours, GB storage, LoadBalancer GB processed, shard-hours, PIOPS, magnetic storage, GET/PUT/POST/COPY/LIST requests, and others.

In Usage Analytics this dimension will return only your EC2 instances.

�

Running Instances and Average Running Instances per Hour

![running instances screenshot](../images/making_the_most_image01.jpg)

The Running Instances metric is a count of all unique instance IDs that were running at one point during the reporting window. This is not necessarily a count of the instances that are live or running at the time the report is run. Rather, it's the sum of unique instance IDs that were running.

Average Running Instances per Hour is an average of the number of instances that were live each hour of the reporting window.

---
