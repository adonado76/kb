---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Dispositivos de red: Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Dispositivos de red"
source_path: "cost-transparency/infra-use-cases/nd-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Dispositivos de red: Introducción

Utilice los componentes de la vista general de costes de dispositivos de red para cargar, modelar y asignar los costes de infraestructura de red en toda la empresa. Esta capacidad permite a las organizaciones asignar los costes de LAN, WAN, voz y otros dispositivos de red de los centros de datos y las oficinas a los consumidores de dichos servicios, lo que proporciona transparencia sobre cómo se incurren y consumen los costes de red en TI y en el negocio.

**Instalación de componentes**

Aplicaciones CT: dispositivos de red

El componente Dispositivos de red instala un nuevo objeto, admite conjuntos de datos y ofrece estrategias de asignación recomendadas para distribuir los costes de infraestructura de red. Estos costes se asignan a los siguientes consumidores típicos:

Sistema principal

Equipos de red que dan soporte a los mainframes en los centros de datos empresariales.

Servidores físicos

Equipos de red que dan soporte a la infraestructura de servidores en los centros de datos empresariales.

Dispositivos de almacenamiento

Equipos de red que dan soporte a plataformas de almacenamiento en centros de datos empresariales.

Dispositivos de usuario final

Equipos de red que admiten conectividad por cable e inalámbrica para ordenadores personales, portátiles y dispositivos móviles en oficinas.

**Requisitos previos**

Debe instalar los siguientes componentes antes de instalar el componente Dispositivos de red:

CTF: Fuente de costes

CTF- Torres de TI

**Fuentes comunes de datos**

Los datos de los dispositivos de red suelen proceder de sistemas financieros, como el libro mayor general para la información sobre costes y presupuestos, combinados con herramientas de gestión y supervisión de redes (por ejemplo, SolarWinds, Cisco DNA Center, herramientas basadas en SNMP), plataformas CMDB y sistemas de gestión de activos. En conjunto, estas fuentes proporcionan visibilidad sobre el inventario, los costes, la utilización y las relaciones de la red, lo que es necesario para una asignación y un informe precisos de los costes de la red.

**Conjuntos de datos**

El conjunto de datos principal que se necesita es el de datos maestros de dispositivos de red, que recoge atributos de los dispositivos como la ubicación, el tipo, la finalidad, el origen y la infraestructura compatible. Este conjunto de datos se completa con información extraída de los sistemas de gestión de redes, supervisión, CMDB y financieros, y se utiliza para asignar los costes de red a los servidores físicos, dispositivos de almacenamiento, dispositivos de los usuarios finales y mainframes dentro del modelo de costes.
