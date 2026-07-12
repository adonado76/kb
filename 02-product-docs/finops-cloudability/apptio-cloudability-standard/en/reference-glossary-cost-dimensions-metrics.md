---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Glossary of Cost Dimensions and Metrics"
breadcrumb:
  - "Data reference"
  - "Glossary of Cost Dimensions and Metrics"
source_path: "SSVCLNQ/product/glossary-of-cost-dimensions-and-metrics.html"
images: []
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Glossary of Cost Dimensions and Metrics

Cloudability's reporting tools allow you to analyze your cost and usage data to figure out exactly where your money is going. The dimensions and metrics available in your reports are identified below.

## Cost and Usage Dimensions

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

## Cost and Usage Metrics

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

## Sustainability Metrics

- Estimated Carbon Emissions (MTCO2e) : This metric captures the estimated carbon emissions in metric tons of carbon dioxide equivalents.
- Power Consumed (kWh) : Power consumed in kilowatt hours.
- Operational Carbon Emission (MTCO2e) - This metrics represents the carbon emissions generated during the day-to-day operation of cloud services. It primarily comes from the electricity used to power and cool data centers while running workloads.
- Embodied Carbon Emission (MTCO2e) - This metrics represents the share of carbon emissions tied to the production and lifecycle of cloud infrastructure. In the cloud context, it’s estimated by allocating a portion of the total embodied emissions of physical servers and equipment based on your specific usage.
