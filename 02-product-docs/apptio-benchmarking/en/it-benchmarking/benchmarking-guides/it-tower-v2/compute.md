---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Compute"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v2/compute.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Compute

| IT Resource Sub Tower | Definitions | Examples | Unit Cost Unit of Measure (standard) (see [definition](#unit "(Opens in a new tab or window)")  ) |
| --- | --- | --- | --- |
| Servers | Physical and virtual servers running a version of Microsoft's Windows Server operating system; includes hardware, software, labor and support services. | Windows Server 2k  Red Hat Server | Logical Server |
| Unix | Servers running vendor-specific, proprietary Unix operating systems (e.g. IBM AIX, Sun Solaris, HP UX); includes hardware, software, labor and support services. | IBM AIX  Sun Solaris | Logical Server , Physical Server |
| Midrange | Midrange covers proprietary servers that provide substantial distributed systems (on platforms such as Unisys or Tandem). The common theme is a distributed architecture and the ability to support multiple clients in parallel. | iSeries (AS 400)  Tandem, DEC servers | Configured MIPS |
| Mainframe | Traditional mainframe computers and operations running legacy operating systems. | IBM mainframes running MVS, VM, OS/390, zOS, zLinux.  Unisys mainframes | Configured MIPS |

**Compute Cost Pool Composition** 

| IT Resource Sub Tower | Internal/External Labor | Hardware | Software | Outside Services | Facilities & Power | Telecom |
| --- | --- | --- | --- | --- | --- | --- |
| Servers | Systems analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Physical and logical servers including HW: chassis, power supply, CPU, memory, Internal storage, network cards, host adapters; SW: OS, virtualization & monitoring | O/S, Virtualization, Monitoring, Security | Managed Windows compute infrastructure services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Unix | Systems analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Chassis, power supply, CPU, memory, Internal storage, network cards, host adapters | O/S, Virtualization, Security, Mgmt & tools | Managed Unix compute infrastructure services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Midrange | Systems analysts/engineers providing technical operations & support, Planning & process mgmt, Admin (including mgmt.) | Chassis, power supply, CPU, memory, Internal storage, network cards, host adapters | O/S, Virtualization, Security, Mgmt & tools | Managed midrange compute infrastructure services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Mainframe | Systems analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Chassis, power supply, CPU, memory, Internal storage, network cards, host adapters | O/S, Virtualization, Security, Mgmt & Tools | Managed mainframe compute infrastructure services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |

**Compute Unit of Measure**

| IT Resource Sub Tower | Unit of Measure (standard) | Guidelines |
| --- | --- | --- |
| Servers  Unix | Logical Servers | An operating system image, partition or virtual server hosted on a physical server. OS Instances may be implemented using partitioning firmware (as provided on large Unix servers from Sun and IBM), or through third party utilities such as VMware or Microsoft. The term “VM” (Virtual Machine) has become common parlance for an “OS Instance” except that a physical machine with no VMs still counts as one OS Instance. Do not count firmware, stub operating systems, the ESX host or virtualizing software as a separate OS Instance. Include Disaster Recovery volumes.  E.g. a hypervisor with 50 virtual machines would be counted as 50 OS instances. Do not count the physical host hypervisor as a separate OS instance. |
| Mainframe  Midrange | Total Configured MIPs | MIPS is defined as: Millions of Instructions per Second. A measure of the processing capacity of a mainframe or mid-range CPU. The practical maximum processing capacity of a partition, taking into account multi-processor overheads and the way that the mainframe has been configured.  Midrange systems which are rated by IBM in CPWs, are converted to MIPS. |
