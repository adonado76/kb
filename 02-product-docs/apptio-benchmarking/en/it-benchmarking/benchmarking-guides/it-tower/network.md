---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "en"
doc_type: "it-benchmarking"
title: "Network"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower/network.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Network

| IT Resource Sub Tower | Definitions | Examples | Unit of Measure (standard) |
| --- | --- | --- | --- |
| LAN (local area network) | Physical and wireless local area network connecting equipment within the core data centers and connecting end users in office working areas to the company's broader networks. | - Routers, DNS, DHCP - Switches, Wireless Access Points | Ports |
| WAN (wide area network) | Wide area network equipment, labor and support services directly connecting data centers, offices and third-parties (excludes telecom and communication services). | - WAN Routers - Multiplexers (ex: WDM, CWDM, DWDM) - Modems - Packet Switches - Frame Relay Switches | Devices |
| Voice | Voice resources which enable or distribute voice services through on premise equipment including PBX, VoIP, voicemail and handsets (excludes telecom and communication services). | - Voice Switch (PBX) - Voice Handset - VoIP S/Ws - Voice-Mail | Handsets |

**Network Cost Pool Composition**

| IT Resource Sub Tower | Internal/External Labor | Hardware | Software | Outside Services | Facilities & Power | Telecom |
| --- | --- | --- | --- | --- | --- | --- |
| LAN (local area network) | Network analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Switches, Wireless Access Points (less likely in DC facility) | Network Mgmt, Security | Managed services for network infrastructure. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| WAN (wide area network) | Network analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | Routers, Firewalls, DNS, DHCP, Network mgmt. | Network Mgmt, Security | Managed services for network infrastructure. | N/A (at the Tower Level, included in the technology services TCO) | N/A |
| Voice | Telecom analysts/engineers providing technical operations & support, Planning & Process Mgmt, Admin (including mgmt.) | PBX, VoIP/IPT Servers, Voicemail, Phones, MAC Supplies | Voice switch, VoIP/IPT software, Voicemail, Network Mgmt, Chargeback | Managed services for voice PBX network. | N/A | N/A |

**Network Unit of Measure**

| IT Resource Sub Tower | Unit of Measure (standard) | Guidelines |
| --- | --- | --- |
| WAN | End User Connected Devices | These are collected separately by type of device on each tab, and they are a calculated field on the Peer Selection Survey. The high level definition is included here, and detailed definitions are included for each device type. An end user device is a device used by a user. The primary purpose of a WAN is to connect end user devices to each other, and to central resources such as servers and storage. The number of end user devices (EUDs) includes:   - All PCs, terminals, thin clients, PDAs, smartphones and tablets that can be connected to the LAN; - All network connected printers; - Wireless access points (count each as one end user device); - The maximum number of concurrent Remote Access ports; - Other user or customer peripheral devices such as ATMs, POS terminals, and so on.   When a router is operated by IT on a third party premises, the number of EUDs for this router is 1. A typical example is when a Bank installs one of its routers on a clearing house premises, to guarantee secure communications.  Do not include the following in the count of end user devices:   - Servers - Volumes for Servers connected to the WAN are collected separately in the Compute Tower - Routers and switches (not usually in the hands of users).   A Wireless Access Point (WAP) is a device that allows wireless devices to connect to a wired network using Wi-Fi or related standards conforming to IEEE 802.11. The WAP usually connects to a router (via a wired network), and can relay data between the wireless devices (such as computers or printers) and wired devices on the network.  Concurrent Remote Access Ports refers to the number of simultaneous remote connections), supporting VPN or similar access |
| LAN | Active LAN Ports | An active port is a port on a switch or router that has been activated and/or enabled so that a device can use it. A port may be active even if it is not currently in use. For example, for organizations using hot-desking (or hotelling), LAN ports are considered active even if a user is not currently seated at the hot-desk (or hotel desk). A network switch or ”blade” (card) in a switch chassis is not considered active, if hard or soft MAC activity (e.g. applying power to switch); physically patching the switch; or applying policies (QoS or VLAN) for the network is required for its operation. |
| Voice | Handset | Handset is the end-point voice instrument used by a user for communicating with another party via a voice network (PSTN or IP).  Includes handsets supported by PBX, Centrex, PBX Hybrid, Centrex Hybrid, VoIP and Soft Phones (the handset is a combination of a software application on a PC or workstation and headset/handset connected to the PC or workstation).  The handset definition does not include: FAX machines, dedicated answering machines, voice mail systems or interactive voice response (IVR) systems. |
