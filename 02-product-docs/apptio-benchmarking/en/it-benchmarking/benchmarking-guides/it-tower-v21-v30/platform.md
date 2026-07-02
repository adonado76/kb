---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Platform"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v21-v30/platform.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Platform

| IT Resource Sub Tower | Definitions | Examples | Unit Cost Unit of Measure (standard) | FTE Efficiency Unit of Measure |
| --- | --- | --- | --- | --- |
| Database | Server-based database management systems (DBMS) such as Oracle. | MS SQL  Oracle on servers | Database Instances | Database instances per Server Database FTE |
| Middleware | Server Middleware - software that links databases and servers of different architectures, and the effort required to support it. | WebSphere, ColdFusion, JBoss, Apache. | Middleware Instances | Middleware instances per Server Middleware FTE |
| Mainframe Database | Mainframe-based database management systems such as DB2 | DB2  Oracle on mainframe | Databases | Databases per Mainframe Database FTE |
| Mainframe Middleware | Mainframe Middleware - software that links databases and mainframes of different architectures, and the effort required to support it. | IBM’s MQ Series | Middleware Instances | Middleware instances per Mainframe Middleware FTE |

**Platform Cost Pool Composition**

| IT Resource Sub Tower | Internal/External Labor | Hardware | Software | Outside Services | Facilities & Power | Telecom |
| --- | --- | --- | --- | --- | --- | --- |
| Database | Personnel for operational and second level support including administration, configuration, updates etc. | N/A | Database software | Managed services for server databases | N/A | N/A |
| Middleware | Personnel for operational and second level support including administration, configuration, updates etc. | N/A | Middleware software | Managed services for server middleware | N/A | N/A |
| Mainframe Database | Personnel for operational and second level support including administration, configuration, updates etc. | N/A | Database software | Managed services for mainframe databases | N/A | N/A |
| Mainframe Middleware | Personnel for operational and second level support including administration, configuration, updates etc. | N/A | Middleware software | Managed services for mainframe middleware | N/A | N/A |

**Platform Unit of Measure**

| IT Resource Sub Tower | Unit of Measure (standard) | Guidelines |
| --- | --- | --- |
| Database | Database Instances | A database instance is a logical database hosted within a DBMS installation. Note: Some cases a DBMS may host several database instances. System tables and other master data are not counted and only data provided to end-users and end-user applications are counted (including development and test dbs). |
| Mainframe Database | Databases | A mainframe database is a database sub-process (provision of database management systems (DBMS) such as DB2 and Oracle on Mainframe platforms). |
| Middleware  Mainframe Middleware | Middleware Instances | Number of instances of middleware package. |
