---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Computación"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower/compute.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Computación

| Subtorre de recursos informáticos | Definiciones | Ejemplos | Coste unitario Unidad de medida (estándar) (véase [la definición](#unit "(se abre en una pestaña o una ventana nueva)") ) |
| --- | --- | --- | --- |
| Servidores | Servidores físicos y virtuales que ejecutan una versión del sistema operativo Windows Server de Microsoft; incluye hardware, software, mano de obra y servicios de asistencia. | Servidor Windows 2k  Red Hat Servidor | Servidor lógico |
| Unix | Servidores con sistemas operativos Unix propietarios específicos de un proveedor (por ejemplo, IBM AIX, Sun Solaris, HP UX); incluye hardware, software, mano de obra y servicios de asistencia. | IBM AIX  Sun Solaris | Servidor lógico, Servidor físico |
| Linux | Servidores físicos y virtuales que ejecutan una versión del sistema operativo de servidor Linux; incluye hardware, software, mano de obra y servicios de asistencia. | - Red Hat Servidor | Servidor lógico, servidor físico |
| Sistema principal | Ordenadores centrales tradicionales y operaciones con sistemas operativos heredados. | - IBM - Tandem | MIPS configurado |

**Cálculo de la composición del pool de costes**

| Subtorre de recursos informáticos | Trabajo interno/externo | Hardware del sistema | Software | Servicios exteriores | Instalaciones y energía | Telecomunicaciones |
| --- | --- | --- | --- | --- | --- | --- |
| Windows | Analistas/ingenieros de sistemas que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Servidores físicos y lógicos, incluidos hardware: chasis, fuente de alimentación, CPU, memoria, almacenamiento interno, tarjetas de red, adaptadores de host; software: sistema operativo, virtualización y supervisión | O/S, Virtualización, Supervisión, Seguridad | Servicios gestionados de infraestructura informática Windows. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Linux | Analistas/ingenieros de sistemas que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Chasis, fuente de alimentación, CPU, memoria, almacenamiento interno, tarjetas de red, adaptadores de host | Sistemas operativos, virtualización, seguridad, gestión y herramientas | Servicios gestionados de infraestructura informática Linux. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Unix | Analistas/ingenieros de sistemas que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Chasis, fuente de alimentación, CPU, memoria, almacenamiento interno, tarjetas de red, adaptadores de host | Sistemas operativos, virtualización, seguridad, gestión y herramientas | Servicios gestionados de infraestructura informática Unix. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Sistema principal | Analistas/ingenieros de sistemas que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Chasis, fuente de alimentación, CPU, memoria, almacenamiento interno, tarjetas de red, adaptadores de host | Sistemas operativos, virtualización, seguridad, gestión y herramientas | Servicios gestionados de infraestructura informática de mainframe. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |

**Calcular unidad de medida**

| Subtorre de recursos informáticos | Unidad de medida (estándar) | Directrices |
| --- | --- | --- |
| Windows  Linux  Unix | Servidores físicos | Incluye servidores físicos independientes e hipervisores (que alojan máquinas virtuales). Cuenta cada servidor como 1. No cuente las máquinas virtuales alojadas en hipervisores. Incluir volúmenes de recuperación de desastres. |
| Windows  Linux  Unix | Servidores lógicos | Una imagen del sistema operativo, partición o servidor virtual alojado en un servidor físico. Las instancias del SO pueden implementarse utilizando firmware de particionamiento (como el que se proporciona en los grandes servidores Unix de Sun y IBM ), o a través de utilidades de terceros como VMware o Microsoft. El término "VM" (Máquina Virtual) se ha convertido en el lenguaje común para una "Instancia de SO", excepto que una máquina física sin VMs sigue contando como una Instancia de SO. No cuente el firmware, los sistemas operativos stub, el host ESX o el software de virtualización como una Instancia de SO independiente. Incluir volúmenes de recuperación de desastres  E.g., un hipervisor con 50 máquinas virtuales se contaría como 50 Instancias de SO. No cuente el hipervisor del host físico como una instancia de SO independiente. |
| Sistema principal | Total de PIM configurados | MIPS se define como: Millones de instrucciones por segundo. Incluya el total de PIM instalados, no sólo el promedio de PIM utilizados. Incluir volúmenes de recuperación de desastres. |
