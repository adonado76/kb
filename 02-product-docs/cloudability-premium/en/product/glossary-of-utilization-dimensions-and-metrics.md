---
source_system: "cloudability-premium"
practice: "finops"
language: "en"
doc_type: "product"
title: "Glossary of utilization dimensions and metrics"
breadcrumb:
  - "Cloudability Premium"
  - "Data reference"
source_path: "product/glossary-of-utilization-dimensions-and-metrics.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Glossary of utilization dimensions and metrics

Cloudability's reporting tools allow you to slice and dice your utilization data so you can
figure out exactly how your infrastructure is being used. Divided into two sections, the dimensions
and metrics that are available in your reports are identified below.

1. [Utilization dimensions](#utilization_dimensions "(Opens in a new tab or window)")
2. [Utilization metrics](#utilization_metrics "(Opens in a new tab or window)")

**Utilization dimensions**

- Account ID  : The 12-digit AWS number used to identify an account. For the
  cost analytics of consolidated billing accounts, this refers to a linked account.
- Account Name  : The name associated with an AWS account. For the cost
  analytics of consolidated billing accounts, this refers to a linked account.
- AMI  : This dimension filters the data you request for all instances running
  this EC2 Amazon Machine Image (AMI). Available for instances with Detailed Monitoring enabled.
- Architecture  : The base architecture of the instance hardware (for example,
  x86, x86\_64, i386).
- Availability Zone  : A combination of the region and zone in which an
  instance exists or a usage charge occurred (for example, us-east-1a).
- CPU Clock Speed  : The base clock speed of the processors on the instance
  (GHz).
- Current State  : The current state of the EC2 instance (for example,
  running, stopped). See the  [AWS Instance Lifecycle User Guide](http://docs.aws.amazon.com/awsec2/latest/userguide/ec2-instance-lifecycle.html "(Opens in a new tab or window)")  for additional information.
- Date  : The calendar date (for example, YYYY-MM-DD).
- Day  : The day of the month.
- Day of Week  : The weekday (for example, Monday).
- Days Alive  : The total number of days since the instance was initially
  launched.
- DNS Name  : The public DNS name associated with a particular EC2 instance
  (for example, ec2-54-205-210-122.compute-1.amazonaws.com).
- Hour  : The numeric hour of the day (for example, 1pm => 13).
- Instance Category  : The instance category (for example, General Purpose,
  Compute Optimized, etc.).
- Instance ID  : The ID associated with a particular AWS instance.
- Instance Name  : The name of a particular EC2 instance.
- Instance Type  : The size of an instance (for example, m1.medium). For more
  information, see  [Frequently used
  dimensions and metrics](frequently-used-dimensions-and-metrics.html)  .
- IP Address  : The IP address associated with a particular EC2 instance.
- **Last Ran**  : The date the resource last ran.
- Launch Date  : The launch date of a particular instance (for example,
  2014-01-22).
- Launch Day  : The launch day of a particular instance (for example, Monday).
- Launch Day of Week  : The day of the week that a particular instance was
  launched (for example, Monday).
- Launch Month  : The numeric month in which an instance was launched (for
  example, 1 => January).
- Launch Time  : The date and time value describing when an instance was
  launched (for example, 2000-01-01T22:46:34Z).
- Launch Week  : The week of the year in which an instance was launched (i.e.
  52 would indicate the last week in a calendar year).
- Launch Year  : The year in which an instance was launched.
- Month  : The numeric calendar month (for example, 2014-1-15 => 12).
- OS  : The operating system of an instance (for example, Linux).
- Private DNS Name  : Amazon EC2 instances need IP addresses to communicate.
  Public IP addresses enable communication over the internet.
- Private IP  : Amazon EC2 instances need IP addresses to communicate. Private
  IP addresses enable communication.
- Processor Architecture  : The CPU architecture.
- Region  : Region in which an instance exists or a usage charge occurred (for
  example, US East).
- Security Group IDs  : A security group acts as a firewall that controls the
  traffic for one or more instances. Each security group is identified by a unique ID (for example,
  sg-xxxxxxxx).
- Security Groups Names  : A security group acts as a firewall that controls
  the traffic for one or more instances. Each security group requires a unique name (limit 255
  characters).
- Storage Type  : No content is given for this entry yet
- Subnet ID  : The subnet ID associated with an EC2 instance. If there is a
  subnet ID listed, the instance is in a VPC.
- Virtualization  : The virtualized environment, if any, running on a given
  instance.
- Week  : The numeric calendar week.
- Year  : The calendar year (for example, 2014).
- Zone  : Availability Zone in which an instance exists or a usage charge
  occurred (for example, 1a).

**Utilization metrics**

- Avg CPU Utilization  : The percentage of allocated EC2 compute units that
  are currently in use on the instance. This metric identifies the processing power required to run an
  application upon a selected instance.
- Avg Estimated Cost  : The average estimated cost of an instance based on the
  selected timeframe (utilization hours: average estimated hourly instance cost).
- Avg Hourly Cost  : The average hourly cost based on the base rates
  established by AWS.
- Avg Hourly Cost Per Instance  : The average hourly cost per instance based
  on the base rates established by AWS.
- Avg Memory Utilization  : The average percentage of memory allocated by
  applications and the operating system for an instance. This metric excludes the memory in cache and
  buffers.
- Avg Running Instances Per Hour  : The average number of running instances
  per hour. For more information, see [Frequently used dimensions and metrics](frequently-used-dimensions-and-metrics.html)  .
- Bandwidth In  : The number of bytes received on all network interfaces by
  the instance. This metric identifies the volume of incoming network traffic to an application on a
  single instance.
- Bandwidth Out  : The number of bytes sent out on all network interfaces by
  instance. This metric identifies the volume of outgoing network traffic to an application on a
  single instance.
- Burst Balance  : Provides information about the percentage of I/O credits
  (for gp2) or throughput credits (for st1 and sc1) remaining in the burst bucket. Used with General
  Purpose SSD (gp2), Throughput Optimized HDD (st1), and Cold HDD (sc1) volumes only.
- Cost (Estimated On-demand)  : The estimated cost based on the values found
  in the AWS Cost Allocation File.
- CPU Total (blue line)  : The normalized percentage of maximum CPU
  utilization in the indicated hour, based on the maximum instance count for the entire ASG in the
  time window of 10 or 30 days. Example: If there are five instances in an ASG and all 5 instances are
  utilizing 100% of their CPU then the  **CPU total**  is 100%. If one instance is utilizing 100%
  of its CPU and the other four instances are utilizing 0% of their CPUs then the  **CPU total** 
  is 20%.
- **CPU Utilization (Max)**  : The maximum percentage of CPU Utilization reached for the hour. For
  EC2, this is the maximum percentage of allocated EC2 compute units in use for an instance. When
  aggregated, this reports the peak across all instances and across the entire time period.
- Disk Access  : Total bytes read and written for all ephemeral disks
  available to the instance (if your instance uses Amazon EBS, see  [Amazon EBS Metrics](http://docs.aws.amazon.com/amazoncloudwatch/latest/developerguide/ebs-metricscollected.html "(Opens in a new tab or window)")  ).
- Disk I/O  : Completed read and write operations from all ephemeral disks
  available to the instance.
- Disk Read Access  : Total bytes read from all ephemeral disks available to
  the instance.
- Disk Read I/O  : Completed read operations from all ephemeral disks
  available to the instance.
- Disk Write Access  : Total bytes written to all ephemeral disks available to
  the instance.
- Disk Write I/O  : Completed write operations to all ephemeral disks
  available to the instance.
- **GPU Total (%)**  :- GPU Total (%) is handled in the same manner as CPU Total (%). (Refer to
   [Rightsizing
  for AWS EC2 ASG](rightsizing-for-aws-autoscaling-groups.html)  )
- **GPU Memory Total (%)**  : GPU Memory Total (%) is handled in the same manner as CPU Memory
  Total (%). (Refer to  [Rightsizing for AWS EC2 ASG](rightsizing-for-aws-autoscaling-groups.html)  )
- **GPU Memory Utilization**  : Percentage of time over a sample period where memory was being
  written or read.

  Note:

  For successful results with GPU metrics, make sure you have configured  [minimal GPU metrics](https://docs.aws.amazon.com/dlami/latest/devguide/tutorial-gpu-monitoring-gpumon.html "(Opens in a new tab or window)")  as a prerequisite.
- **GPU Utilization**  : Percentage of time over a sample period where one or more kernels on the
  GPU was running.
- Hours Since Launch  : The number of hours elapsed since an instance
  initially launched.
- **Instance Count: CPU Total (red line)**  : The total number of instances running for this ASG
  in the indicated hour.
- **Instance Count: Network Max (red line)**  : The total number of instances running for this ASG
  in the indicated hour.
- **Instance Count: Memory Total(red line)**  : The total number of instances running for this ASG
  in the indicated hour.
- Launched Instances  : The total number of launched instances in a given time
  period.
- Memory  : The amount of memory available to the instance.
- **Memory Total (blue line)**  : The normalized percentage of maximum memory utilization in the
  indicated hour, based on the maximum instance count for the entire ASG in the time window of 10 or
  30 days. Example: If there are five instances in an ASG and all five instances are utilizing 100% of
  their memory, then the  **Memory total**  is 100%. If one instance is utilizing 100% of its
  memory and the other four instances are utilizing 0% of their memory then the  **Memory total** 
  is 20%.
- **Network Max (blue line)**  : The total number of bits per second utilized based on the maximum
  instance count for the entire ASG in the indicated hour.
- **Recommended: CPU Total (yellow dashed line)**  : The recommended normalized percentage of CPU
  utilization allocation for the entire ASG in the indicated hour.
- **Recommended: Memory Total(yellow dashed line)**  : The recommended normalized percentage of
  memory utilization allocation for the entire ASG in the indicated hour.
- **Recommended: Network Total (yellow dashed line)**  : The recommended network allocation for
  the entire ASG in the indicated hour.
- **Recommended instance count: CPU Total (yellow line, displayed on hover)**  : The total number
  of instances recommended for this ASG in the indicated hour.
- **Recommended instance count: Memory Total (yellow line, displayed on hover)**  : The total
  number of instances recommended for this ASG in the indicated hour.
- Storage  : The amount for storage available to the instance. This number
  will not include EBS.
- Storage Devices  : The total number of storage devices associated with an
  instance in a given time period.
- **Recommended instance count (yellow line, displayed on hover)**  : The total number of
  instances recommended for this ASG in the indicated hour.
- Total Bandwidth  : Total bytes transferred by a particular instance.
- Unique Instance Count  : The total number of unique instances in a running
  state during a given time period.
- Utilization Hours  : The total number of usage hours on an instance in a
  particular timeframe.
- Volume Consumed Read Write Ops  : The total amount of read and write
  operations (normalized to 256K capacity units) consumed in a specified period of time. Used with
  Provisioned IOPS SSD volumes only.
- Volume Throughput Percentage  : The percentage of I/O operations per second
  (IOPS) delivered of the total IOPS provisioned for an Amazon EBS volume. Used with Provisioned IOPS
  SSD volumes only.

  Note:

  This metric is not supported for Multi-Attach enabled volumes.
