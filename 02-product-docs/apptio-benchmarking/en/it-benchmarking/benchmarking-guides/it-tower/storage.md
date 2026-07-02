---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Storage"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower/storage.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Storage

| IT Resource Sub Tower | Definitions | Examples | Unit of Measure (standard) |
| --- | --- | --- | --- |
| Tier 1 | Storage resources which enable mission critical applications & services and requires highest levels of availability. | - FC SAN - High-end NAS - Switches, Disks, Cabling & SSD - Replication SW | Installed TB |
| Tier 2 | Storage resources which enable essential but non-mission critical applications, services and data; requires relatively high service level performance. | - FC SAN - High-end NAS - Switches, Disks, Cabling | Installed TB |
| Tier 3 | Storage resources used for non-essential, historical and other information where immediate availability is not required. | - SAN, NAS - Switches, Disks, Cabling - Disk to Disk | Installed TB |
| Tier 4 | Storage resources used for archive, backup & recovery to support data loss, data corruption, disaster recovery and compliance requirements. | - Tape Backup - Backup/Archival S/W | Installed TB |

**Storage Cost Pool Composition**

| IT Resource Sub Tower | Internal/External Labor | Hardware | Software | Outside Services | Facilities & Power | Telecom |
| --- | --- | --- | --- | --- | --- | --- |
| Tier 1 | Storage analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Storage disk & controllers, Storage servers, Fiber switches | Storage maintenance, Replication, Reporting, Security, Monitoring | Managed storage services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Tier 2 | Storage analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Storage disk & controllers, Storage servers, Fiber switches | Storage maintenance, Replication, Reporting, Security, Monitoring | Managed storage services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Tier 3 | Storage analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Storage disk & controllers, Storage servers, Fiber switches | Storage maintenance, Replication, Reporting, Security, Monitoring | Managed storage services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Tier 4 | Systems analysts/engineers providing technical operations & support (online backup & tape mgmt), Planning & Process Mgmt, Admin (including mgmt.) | Specialized backup/ archive systems, Tape subsystems, Offline supplies (e.g. tapes) | Backup/restore/ archive maintenance, Reporting, Security, Monitoring, Media Handling / migration | Managed storage services. Managed off-site archive services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |

**Storage Units of Measure**

| IT Resource Sub Tower | Unit of Measure (standard) | Guidelines |
| --- | --- | --- |
| Tier 1 | Total installed (raw) disk storage in TB | The maximum raw physical capacity of all disk drives, technologies (i.e. SAN, NAS, iSCSI, CAS, DASD etc.) and locations (including Disaster Recovery locations). For example, for storage array containing 64 disk drives rated by the manufacturer as 800 Gbyte drives, the installed disk storage is 51.2 Tbytes.  For virtual storage arrays such as RAMAC or ICEBERG, enter the vendor’s maximum claimed capacity of the device after compression, as found in purchasing agreements or product brochures.  Production and Failover – FC SAN, High End NAS, SSD  Include Mainframe storage  Include disaster recovery volumes |
| Tier 2 | Total installed (raw) disk storage in TB | Non mission critical, Dev & Test  Include disaster recovery volumes |
| Tier 3 | Total installed (raw) disk storage in TB | Storage for lower performing requirements  Disk to Disk Back Up, Online Archiving, VTL  Include disaster recovery volumes |
| Tier 4 | Total installed tape storage in TB | Tape back up  Include disaster recovery volumes |
