---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Storage"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v2/storage.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Storage

| IT Resource Sub Tower | Definitions | Examples | Unit Cost Unit of Measure (standard) (see [definition](#unit "(Opens in a new tab or window)")  ) |
| --- | --- | --- | --- |
| Online | Online Storage resources attached to Servers. It excludes storage that is bundled (internal) in the server (it is included in the server cost). This includes Disaster Recovery storage. | SAN, NAS, iSCSI, CAS | Installed TB |
| Offline | Offline Storage resources attached to Servers. This includes Disaster Recovery storage. | Tape Backup Backup/Archival S/W | Installed TB |
| Mainframe Online | Online Storage resources attached to Mainframes. This includes Disaster Recovery storage. | SAN, NAS, iSCSI, CAS | Installed TB |
| Mainframe Offline | Offline Storage resources attached to Mainframes. This includes Disaster Recovery storage. | Tape Backup  Backup/Archival S/W | Installed TB |

**Storage Cost Pool Composition**

| IT Resource Sub Tower | Internal/External Labor | Hardware | Software | Outside Services | Facilities & Power | Telecom |
| --- | --- | --- | --- | --- | --- | --- |
| Online  Mainframe Online | Storage analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Storage disk & controllers, Storage servers, Fiber switches | Storage management, virtualization, Replication, Reporting, Security, Monitoring. Drivers & network software for NAS. | Managed storage services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Offline  Mainframe Offline | Systems analysts/engineers providing technical operations & support (online backup & tape mgmt), Planning & Process Mgmt, Admin (including mgmt.) | Specialized backup/ archive systems, Tape subsystems, Offline supplies (e.g. tapes) | Backup/restore/ archive maintenance, Reporting, Security, Monitoring, Media Handling/migration | Managed storage services. Managed off-site archive services. | N/A (at the Tower Level, included in the technology services TCO) | N/A |

**Storage Units of Measure**

| IT Resource Sub Tower | Unit of Measure (standard) | Guidelines |
| --- | --- | --- |
| Online  Mainframe Online | Total installed (raw) disk storage in TB | The maximum raw physical capacity of all disk drives, technologies (i.e. SAN, NAS, iSCSI, CAS, DASD etc.) and locations (including Disaster Recovery locations). For example, for storage array containing 64 disk drives rated by the manufacturer as 800 Gbyte drives, the installed disk storage is 51.2 Tbytes.  For virtual storage arrays such as RAMAC or ICEBERG, enter the vendor’s maximum claimed capacity of the device after compression, as found in purchasing agreements or product brochures.  Production and Failover – FC SAN, High End NAS, SSD  Include disaster recovery volumes |
| Offline  Mainframe Offline | Total installed tape storage in TB | Tape back up  Include disaster recovery volumes |
