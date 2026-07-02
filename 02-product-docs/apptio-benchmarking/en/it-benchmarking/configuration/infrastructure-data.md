---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Infrastructure data and volumes"
breadcrumb:
  - "Benchmarking"
  - "Configuration Guide"
source_path: "it-benchmarking/configuration/infrastructure-data.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Infrastructure data and volumes

For infra benchmarks, you need details for cost, volume, and FTEs. Cost alone is not enough.

**Data sources**  
Volume data typically comes from:

- CMDB or asset management systems.
- Monitoring and capacity management tools.
- Spreadsheets maintained by infra teams.

For each infra-related Resource Sub-Tower that you want to benchmark, you need to enter:

1. Annual cost aligned to that Resource Sub-Tower.
2. A volume or capacity metric that matches the benchmark definition.
3. FTE (full-time equivalent) volumes reflecting IT org staff supporting/contributing to the
   Resource Sub-Tower.

![Interactive Benchmarking Configuration – Cost Pools, Resource Towers Volumes, & FTEs](../../resources/images/it%20benchmarking_images/data-sources.png)

Examples:

- “Servers” Resource Sub-Tower
  - Cost: server hardware, OS licenses, related labor, and services.
  - Volume: number of servers or vCPUs, depending on metric definition.
  - FTE: full-time equivalent supporting servers’ maintenance and related processes.
- “Storage” Resource Sub-Tower
  - Cost: storage hardware, licenses, labor, and services.
  - Volume: TB of usable capacity.
  - FTE: full-time equivalent supporting storage devices’ maintenance and related processes.
- “Network” Resource Sub-Tower
  - Cost: network hardware, support, licenses, labor.
  - Volume: devices or ports.
  - FTE: full-time equivalent supporting network devices’ maintenance and related processes.

**Mapping volumes to Sub-Towers**  
Your mapping must be consistent:

- The volume must align with the cost scope.
- Do not double count the same device in multiple Resource Sub-Towers unless that is explicitly
  the design.
- Use the unit expected by the benchmark definition.

If your CMDB is messy, start with the cleanest Resource Towers and Resource Sub-Towers first.
It is better to have a few solid infra metrics than many broken ones.

**TBM Resource Towers and Sub-Towers**  
Resource Tower support is available up
through TBM version 4 and earlier. Details for the Resource Towers, Sub-Towers, and Unit of
Measurement appear in the table below:

| **Tower Name** | **Sub-Tower Name** | **Sub-Tower Description** | **Unit of Measure** | **Unit of Measure Description** | **Benchmarking Available?** |
| --- | --- | --- | --- | --- | --- |
| Application | Application Development | Resources involved with the analysis, design, development, code, test and release packaging services associated with application development projects. Optional Level 3 categories include: Development, QA | FTE-Hrs | Total hours contributed by full-time equivalent personnel for Application Development activities. | Yes |
| Application | Application Support & Operations | The operations, support, fix and minor enhancements associated with existing applications. | FTE-Hrs | Total hours contributed by full-time equivalent personnel for Application Support & Operations activities. | Yes |
| Application | Business Software | Software expenditures including licensing, SaaS, maintenance and support related to off-the-shelf software purchases. | Licensed Software | Number of software licenses procured and in use, typically aligned with vendor agreements. | Yes |
| Compute | Converged Infrastructure | Purpose-built appliances that provide compute, storage and network capabilities in one box. | Appliances | Number of integrated hardware/software devices deployed with converged compute, storage, and network functionality. | No |
| Compute | High Performance Computing | High-Performance Computing (HPC) is used for solving complex computational problems through massive concurrent use of computing resources and parallel processing techniques. HPC technology is applied in areas such as scientific and industrial research, product engineering and development, and complex business modeling, simulation and analysis. HPC hardware and software technologies are specialized and optimized for massively parallel computing and processing vast amounts of data. | Petaflops | Total number of double precision petaflops (Rpeak) of all High Performance Compute processing nodes that are delivered using conventional CPUs. A petaflop is a unit of computing speed equal to one thousand million million (10 to the power of 15) floating-point operations per second. | No |
| Compute | Mainframe | Traditional mainframe computers and operations running legacy operating systems. | Configured MIPS | Number of Million Instructions Per Second configured on mainframe systems, representing compute capacity. Configured MIPS represent the practical maximum processing capacity of a partition, taking into account multi-processor overheads and the way that the mainframe has been configured. | Yes |
| Compute | Midrange | Servers running IBM AS/400 platform including hardware, software, labor and support services. | Configured MIPS | Number of Million Instructions Per Second configured on mainframe systems, representing compute capacity. Configured MIPS represent the practical maximum processing capacity of a partition, taking into account multi-processor overheads and the way that the mainframe has been configured. | Yes |
| Compute | Servers | Physical and virtual servers running a version of Microsoft's Windows Server or the Linux operating system; includes hardware, software, labor and support services. Optional Level 3 categories include: Windows, Linux. and Public Cloud Compute. | Logical Servers | Number of virtual or logical server instances provisioned for on-premise compute workloads. | Yes |
| Compute | Unix | Servers running vendor-specific, proprietary Unix operating systems (e.g., IBM AIX, Sun Solaris, HP UX); includes hardware, software, labor and support services. | Logical Servers | Number of virtual or logical server instances provisioned for on-premise compute workloads. | Yes |
| Data Center | Enterprise Data Center | Purpose-built data center facilities that house and protect critical IT equipment including the space, power, environment controls, racks, cabling and "smart hand" support. | kW-mo | Kilowatt-months of power consumed by Enterprise Data Centers. | No |
| Data Center | Other Facilities | Computer rooms and MDF/IDF/telco closets that house IT equipment in corporate headquarters, call centers or other general purpose office buildings. | Sq Ft | Physical area in square feet occupied by technology infrastructure within data center facilities. | No |
| Delivery | Client Management | Resources or “account managers” aligned with the lines of business to understand business needs, communicate IT products, services and status of IT projects. | Tasks | Count of discrete operational-related activities performed and completed by the Client Management team. | No |
| Delivery | IT Service Management | Resources involved with the incident, problem and change management activities as part of the IT Service Management process (excludes the Tier 1 help desk and Deskside Support). | Reviews | Count of service or operational reviews conducted for quality or compliance purposes. | Yes |
| Delivery | Operations Center | Centralized IT Operations Center resources including monitoring and intervention e.g., NOC (network operations center), GOC (global operations center). | Tasks | Count of discrete operational or security-related activities performed by the Operations Center team. | No |
| Delivery | Program, Product & Project Management | Resources involved with managing and supporting IT related projects and/or continuous product development (e.g. Agile) across business and IT-driven initiatives. | Tasks | Count of discrete operational-related activities performed by the Tech Portfolio & Project Management team. | No |
| End User | Conferencing & AV | Audio and video conferencing equipment typically used in conference rooms and dedicated telepresence rooms to enable workforce communications. | Users | Number of individual accounts configured and enabled to leverage Conferencing & AV services. | Yes |
| End User | Deskside Support | Local support resources that provide on-site support for moves, adds, changes and hands on issue resolution. | Personal Devices | Number of devices supported by Deskside Support services. Personal devices include personal computers, smartphones, tablets, thin clients, and handheld devices. | Yes |
| End User | End User Software | Client related software used to author, create, collaborate and share documents and other content. Examples include email, communications, messaging, word processing, spreadsheets, presentations, desktop publishing, graphics and others. Optional Level 3 categories include Productivity; Communications; Collaboration. | Licensed Software | Number of software licenses procured and in use, typically aligned with vendor agreements. | Yes |
| End User | IT Help Desk | Centralized Tier 1 help desk resources that handle user requests, answer questions and resolve issues. | Contacts | Number of help desk interactions handled by the Help Desk team. Contacts include incidents, service requests, and information requests raised to the Help Desk team by end users or monitoring tools. Contacts initiated by the Help Desk team to follow-up with end users should also be included. | Yes |
| End User | Mobile Devices | Client compute tablets, smart phones (iOS, Android, Windows Mobile) and apps used by individuals to perform work. | Devices | Number of handheld devices used to deliver end user computing functionality such as email, browsing, or media access. Examples of mobile devices include smartphones, tablets, and PDAs. | Yes |
| End User | Network Printers | Printers located on or near users’ desktops. Examples include network connected personal printers, ink-jet printers, laser printers, departmental or copy-room printers. Only include network connected printers. Do not include printers connected to an end user computer. | Users | Number of users that are configured to leverage network printers. | No |
| End User | Workspace | Client compute physical desktops, portable laptops, thin client machines, peripherals (including monitors, pointer devices and attached personal printers) used by individuals to perform work. | Personal Devices | Number of devices supported by Workspace services. Personal devices include personal computers, smartphones, tablets, thin clients, and handheld devices. | Yes |
| IT Management | Enterprise Architecture | Enterprise architecture services including business, information, application and technical architecture to drive standardization, integration and efficiency among business technology solutions. | Users | Number of users that are authorized and configured to receive IT services. | Tower Only |
| IT Management | IT Management & Strategic Planning | IT management and administration resources; typically CIO, senior IT leaders and administrative support including centralized IT strategy and planning. | Users | Number of users that are authorized and configured to receive IT services. | Tower Only |
| IT Management | IT Finance | Resources involved in the planning, budgeting, spend management and chargeback of IT expenditures and the costing of IT products and services. | Users | Number of users that are authorized and configured to receive IT services. | Tower Only |
| IT Management | IT Vendor Management | Resources involved in the selection, contract management, oversight, performance management and general delivery of services by 3rd party vendors and external service providers. | Users | Number of users that are authorized and configured to receive IT services. | Tower Only |
| Network | LAN/WAN | Physical and wireless local area network connecting equipment within the core data centers and connecting end users in office working areas to the organization's broader networks. Wide area network equipment, labor and support services directly connecting data centers, offices and third parties (excludes telecom and communication services). Optional Level 3 categories include: LAN, WAN. | Users | Number of users that are authorized and configured to access corporate networks. | Yes |
| Network | Transport | Data network circuits and associated access facilities and services; includes dedicated and virtual data networks and internet access. Also includes usage associated with mobility and other data transit based on usage billing. Voice network circuits and associated access facilities and services. Also includes usage associated with standard telephone calls and 800 number service. Both voice and data transport may include terrestrial and non-terrestrial (e.g., satellite) technologies. Optional Level 3 categories include: Data, Voice. | Users | Number of users that are authorized and configured to access corporate networks. | Yes |
| Network | Voice | Voice resources which enable or distribute voice services through on-premise equipment including PBX, VoIP, voicemail and handsets (excludes telecom and communication services). | Devices | Number of voice communication devices such as desk phones or VoIP handsets. | Yes |
| Output | Central Print | Central print services; often provided to support customer billing or customer documentation support processes. Unit of measure: page. | Million Images | Millions of printed or processed images delivered in centralized print operations. | Yes |
| Platform | Big Data | Systems and resources for integrating, managing and analyzing high volumes of low density, unstructured data that is received at high rates of velocity. | Processing Hours | Total hours spent processing data or executing compute-intensive tasks. | No |
| Platform | Container Orchestration | Tools and resources for managing the lifecycles of containers. Includes the control and automation of tasks such as provisioning and deployment of containers, maintaining availability, scaling up or removing containers to manage application loads, relocating containers, allocating resources for containers, and monitoring container and host health. | Containers | Number of containerized application instances deployed and managed. | No |
| Platform | Database | Distributed database services focused on the physical database (versus the logical design) including DBAs, DBMS, tools and operational support. | Database Instances | Number of logical databases hosted within a DBMS installation. In some cases the DBMS may only be used for a single database, in which case the number of database instances is one. In other cases a DBMS may host multiple database instances. | Yes |
| Platform | Mainframe Database | Mainframe database services focused on the physical database (versus the logical design) including the DBAs, DBMS, tools and operational support. | Databases | Number of distinct database systems deployed across Mainframe environments. | Yes |
| Platform | Mainframe Middleware | Mainframe platform, application and system integration resources enabling cross application development, communications and information sharing. | Middleware Instances | Number of middleware instances deployed across Mainframe environments. | Yes |
| Platform | Middleware | Distributed platform, application and system integration resources enabling cross application development, communications and information sharing. | Middleware Instances | Number of middleware instances deployed across server environments. | Yes |
| Security & Compliance | Compliance | IT Compliance resources setting policy, establishing controls and measuring compliance to relevant legal and compliance requirements. Optional Level 3 categories include: Data Privacy. The implementation actions defined by Compliance policy (e.g. implementing controls like multi-factor authentication) are not included in the Compliance sub-tower and are part of the respective towers where the actions take place (e.g. Compute, Storage, Network, Application, End User). | Managed Systems | Number of systems under centralized management or monitoring for Regulatory & Audit compliance. | No |
| Security & Compliance | Disaster Recovery | IT Disaster Recovery resources setting DR policy, establishing process & means, dedicated failover facilities, performing DR testing. NOTE: DR designated equipment is included directly in its own sub-tower (e.g., extra servers for DR are included in Compute tower, etc.). The implementation actions defined by Disaster Recovery policy (e.g. building DR servers) are not included in the Disaster & Recovery sub-tower and are part of the respective towers where the actions take place (e.g. Compute, Storage, Network). | Managed Systems | Number of systems within the technology landscape that are configured and managed by the Disaster Recovery team. | No |
| Security & Compliance | Security | IT Security resources setting policy, establishing process & means, measuring compliance and responding to security breaches. and providing real-time operational security such as vulnerability scanning, managing firewalls, intrusion prevention systems, and security information and event management (SIEM). Optional Level 3 categories include: Cyber Security. The implementation actions defined by security policies (e.g. mitigating security breaches by applying patches) are not included in the Security sub-tower and are part of the respective towers where the actions take place (e.g. Compute, Storage, Network). | Managed Systems | Number of systems within the technology landscape that are managed and monitored by the Digital Security team. | No |
| Storage | Mainframe Offline Storage | Any storage resources used for archive, backup & recovery to support data loss, data corruption, disaster recovery and compliance requirements of the mainframe storage. | Installed TB | Total installed storage capacity in terabytes across Offline Mainframe storage systems. | Yes |
| Storage | Mainframe Online Storage | Mainframe attached storage arrays and the associated equipment, software and labor to run and operate. | Installed TB | Total installed storage capacity in terabytes across Online Mainframe storage systems. | Yes |
| Storage | Offline Storage | Offline storage resources used for archive, backup & recovery to support data loss, data corruption, disaster recovery and compliance requirements of the distributed storage. | Installed TB | Total installed storage capacity in terabytes across Offline Storage systems. | Yes |
| Storage | Online Storage | Central storage such as SAN, NAS and similar technologies for the distributed compute infrastructure; includes the equipment, software and labor to run and operate. Optional Level 3 categories include: On-Premise, Public Cloud Storage. | Installed TB | Total installed storage capacity in terabytes across Online Storage systems. | Yes |
