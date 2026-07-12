---
source_system: "apptio-cloudability-standard"
practice: "tbm"
language: "en"
doc_type: "cloudability-standard"
title: "Set up Azure Memory Metrics Collection"
breadcrumb:
  - "Getting data into Cloudability"
  - "Connect Microsoft Azure"
  - "Set up Azure Memory Metrics Collection"
source_path: "SSVCLNQ/admin/set_up_azure_memory_metrics_collection.html"
images:
  - "03-media/apptio-cloudability-standard/azure_monitoring.jpg"
capability_ids: []
last_updated: "2026-07-09"
summary: ""
---
# Set up Azure Memory Metrics Collection

*Azure Monitor Agent collects monitoring data from Azure virtual machines and pushes it to Azure Monitor.*

## About this task

There are two types of metrics available from Azure Monitor:

- Standard Metrics : CPU Percentage, Disk Reads/Writes, Network Throughput
- Guest OS Metrics : Memory Utilization

For more information about Azure Monitor metrics, see Supported metrics with Azure Monitor .

## Procedure

1. Install Azure Monitor Agent Linux Installation Using Azure PowerShell: Set-AzVMExtension -Name AzureMonitorLinuxAgent -ExtensionType AzureMonitorLinuxAgent -Publisher Microsoft.Azure.Monitor -ResourceGroupName <resource-group-name> -VMName <virtual-machine-name> -Location <location> -TypeHandlerVersion <version-number> -EnableAutomaticUpgrade $true Using Azure CLI: az vm extension set --name AzureMonitorLinuxAgent --publisher Microsoft.Azure.Monitor --ids <vm-resource-id> --enable-auto-upgrade true For further details, refer to Azure Monitor Agent Management . Windows Installation Using Azure PowerShell: Set-AzVMExtension -Name AzureMonitorWindowsAgent -ExtensionType AzureMonitorWindowsAgent -Publisher Microsoft.Azure.Monitor -ResourceGroupName <resource-group-name> -VMName <virtual-machine-name> -Location <location> -TypeHandlerVersion <version-number> -EnableAutomaticUpgrade $true Using Azure CLI: az vm extension set --name AzureMonitorWindowsAgent --publisher Microsoft.Azure.Monitor --ids <vm-resource-id> --enable-auto-upgrade true Note: To confirm successful agent installation, check the extensions section of your virtual machine.
1. Send Guest OS Metrics with Azure Monitor Agent Azure Monitor Agent supports pushing guest OS metrics directly to Azure Monitor. Follow the steps below to configure data collection. Reference: Data Collection Rules for Azure Monitor Agent Create Data Collection Rule From the Monitor menu, select Data Collection Rules . Select Create to create a new data collection rule and associations. Enter a Rule name and specify a Subscription , Resource Group , Region , and Platform Type . On the Resources tab: Select + Add resources and associate resources to the data collection rule. Resources can be Virtual Machines, Virtual Machine Scale Sets, and Azure Arc for servers. The Azure portal installs Azure Monitor Agent on resources that don't already have it installed. Select Enable Data Collection Endpoints . Select a data collection endpoint for each of the resources associated with the data collection rule. On the Collect and deliver tab, select Add data source to add a data source and set a destination. Select a Data source type . Select which data you want to collect. For performance counters, you can select from a predefined set of objects and their sampling rate. For events, you can select from a set of logs and severity levels. Important: Cloudability only takes into account the following metrics for Memory Utilization: Windows: Memory Available Bytes + Memory Committed Bytes Linux: mem/available + mem/used On the Destination tab, add one or more destinations for the data source. You can select multiple destinations of the same or different types. For instance, you can select multiple Log Analytics workspaces, which is also known as multihoming. Select Add data source and then select Review + create to review the details of the data collection rule and association with the set of virtual machines. Select Create to create the data collection rule. Note: It can take up to 5 minutes for data to be sent to the destinations after you create the data collection rule.
