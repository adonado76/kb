---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Red"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v21-v30/network.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Red

| Subtorre de recursos informáticos | Definiciones | Ejemplos | Coste unitario Unidad de medida (estándar) (véase [la definición](#unit "(se abre en una pestaña o una ventana nueva)") ) | Unidad de medida de la eficacia ETC (véase [la definición](#fte "(se abre en una pestaña o una ventana nueva)") ) |
| --- | --- | --- | --- | --- |
| LAN/WAN | Red de área local física e inalámbrica que conecta los equipos dentro de los centros de datos centrales y conecta a los usuarios finales de las zonas de trabajo de las oficinas con las redes más amplias de la empresa.  Equipos de red de área extensa, mano de obra y servicios de apoyo que conectan directamente centros de datos, oficinas y terceros (excluye servicios de telecomunicaciones y comunicaciones). | Enrutadores, DNS, DHCP  Conmutadores, puntos de acceso inalámbricos  Multiplexores (por ejemplo: WDM, CWDM, DWDM)  Módems  Conmutadores de paquetes  Conmutadores Frame Relay | Usuarios | Miles de dispositivos de datos (LAN, WAN) por ETC de datos |
| Voz | Recursos de voz que permiten o distribuyen servicios de voz a través de equipos locales, incluidos PBX, buzón de voz VoIP, y teléfonos (excluye servicios de telecomunicaciones y comunicación). | Conmutador de voz (PBX), auricular de voz, software de conmutación de voz ( VoIP ), buzón de voz | Teléfonos | Miles de terminales por ETC de voz |
| Transporte | Circuitos de redes de voz y datos e instalaciones y servicios de acceso asociados; incluye redes de datos dedicadas y virtuales, acceso a Internet y circuitos de voz. Uso de voz y datos asociado a llamadas telefónicas estándar, servicio de número 800, movilidad y otros tránsitos de datos basados en la facturación por uso. | Circuitos: Líneas arrendadas  MPLS/ATM  Anillos SONET  Acceso a Internet  Instalaciones de transmisión propiedad del cliente y mantenidas por éste  Troncales dedicadas  Fibra dedicada/propia  Gestión de gastos S/W  Herramientas de gestión  Uso de voz y datos (Internet) | Usuarios | No soportado |

**Composición del grupo de costes de la red**

| Subtorre de recursos informáticos | Trabajo interno/externo | Hardware del sistema | Software | Servicios exteriores | Instalaciones y energía | Telecomunicaciones |
| --- | --- | --- | --- | --- | --- | --- |
| LAN/WAN | Analistas/ingenieros de redes que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Conmutadores, puntos de acceso inalámbricos (menos probable en instalaciones de CC)  Enrutadores, cortafuegos, DNS, DHCP, gestión de redes. | Gestión de redes, Seguridad | Servicios gestionados para infraestructuras de red. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Voz | Analistas/ingenieros de telecomunicaciones que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | PBX, VoIP/IPT Servidores, Buzón de voz, Teléfonos, Suministros MAC | Conmutador de voz, software VoIP/IPT, buzón de voz, gestión de redes, facturación | Servicios gestionados para la red PBX de voz. | N/D | N/D |
| Transporte | Analistas/ingenieros de telecomunicaciones que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión)  Analistas/ingenieros de sistemas que prestan apoyo y operaciones técnicas | N/D | Software de gestión de gastos de telecomunicaciones, Herramientas de gestión | N/D | N/D - seguimiento en el fondo de costes de telecomunicaciones | Circuitos: Líneas de acceso, líneas alquiladas, instalaciones de transmisión propiedad y mantenidas por el cliente, trunking dedicado, acceso a Internet Fibra dedicada/propia, anillos SONET, MPLS, ATM Utilización: Salientes y entrantes, uso de voz y datos 800 entrantes, larga distancia saliente, servicios de enrutamiento de llamadas, servicios avanzados de llamadas, uso de Internet |

**Unidades de medida de la red**

| Subtorre de recursos informáticos | Unidad de medida (estándar) | Directrices |
| --- | --- | --- |
| LAN/WAN | Usuarios | El número de usuarios que consumen servicios de TI (incluidos empleados a tiempo completo, contratistas, consultores, proveedores) y se utiliza para calcular el coste LAN/WAN por usuario. La mayoría de los clientes recopilan este recuento mediante un recuento de ID de usuario para el inicio de sesión en la red, pero también son aceptables otras estimaciones. |
| Voz | Teléfono | El microteléfono es el instrumento de voz de punto final utilizado por un usuario para comunicarse con otra persona a través de una red de voz (RTPC o IP).  Incluye microteléfonos compatibles con PBX, Centrex, PBX Híbrida, Centrex Híbrida, VoIP y Soft Phones (el microteléfono es una combinación de una aplicación de software en un PC o estación de trabajo y un auricular/microteléfono conectado al PC o estación de trabajo).  La definición de microteléfono no incluye FAX, contestadores automáticos dedicados, sistemas de buzón de voz o sistemas interactivos de respuesta de voz (IVR). |
| Transporte | Usuarios | El número de usuarios que consumen servicios informáticos (incluidos empleados a tiempo completo, contratistas, consultores, proveedores) y se utiliza para calcular el coste de comunicación por usuario. La mayoría de los clientes recopilan este recuento mediante un recuento de ID de usuario para el inicio de sesión en la red, pero también son aceptables otras estimaciones. |
