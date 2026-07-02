---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Red"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower/network.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Red

| Subtorre de recursos informáticos | Definiciones | Ejemplos | Unidad de medida (estándar) |
| --- | --- | --- | --- |
| LAN (red de área local) | Red de área local física e inalámbrica que conecta los equipos dentro de los centros de datos centrales y conecta a los usuarios finales de las zonas de trabajo de las oficinas a las redes más amplias de la empresa. | - Enrutadores, DNS, DHCP - Conmutadores, puntos de acceso inalámbricos | Puertos |
| WAN (red de área extensa) | Equipos de red de área extensa, mano de obra y servicios de apoyo que conectan directamente centros de datos, oficinas y terceros (excluye servicios de telecomunicaciones y comunicaciones). | - Enrutadores WAN - Multiplexores (por ejemplo: WDM, CWDM, DWDM) - Módems - Conmutadores de paquetes - Conmutadores Frame Relay | Dispositivos |
| Voz | Recursos de voz que permiten o distribuyen servicios de voz a través de equipos locales, incluidos PBX, buzón de voz VoIP, y teléfonos (excluidos los servicios de telecomunicaciones y comunicación). | - Conmutador de voz (PBX) - Teléfono de voz - VoIP S/W - Buzón de voz | Teléfonos |

**Composición del grupo de costes de la red**

| Subtorre de recursos informáticos | Trabajo interno/externo | Hardware del sistema | Software | Servicios exteriores | Instalaciones y energía | Telecomunicaciones |
| --- | --- | --- | --- | --- | --- | --- |
| LAN (red de área local) | Analistas/ingenieros de redes que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Conmutadores, puntos de acceso inalámbricos (menos probable en instalaciones de CC) | Gestión de redes, Seguridad | Servicios gestionados para infraestructuras de red. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| WAN (red de área extensa) | Analistas/ingenieros de redes que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Enrutadores, cortafuegos, DNS, DHCP, gestión de redes. | Gestión de redes, Seguridad | Servicios gestionados para infraestructuras de red. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Voz | Analistas/ingenieros de telecomunicaciones que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | PBX, VoIP/IPT Servidores, Buzón de voz, Teléfonos, Suministros MAC | Conmutador de voz, software VoIP/IPT, buzón de voz, gestión de redes, facturación | Servicios gestionados para la red PBX de voz. | N/D | N/D |

**Red Unidad de medida**

| Subtorre de recursos informáticos | Unidad de medida (estándar) | Directrices |
| --- | --- | --- |
| WAN | Dispositivos conectados al usuario final | Se recogen por separado por tipo de dispositivo en cada ficha, y son un campo calculado en la Encuesta de selección por pares. Aquí se incluye la definición de alto nivel y se incluyen definiciones detalladas para cada tipo de dispositivo. Un dispositivo de usuario final es un dispositivo utilizado por un usuario. El objetivo principal de una WAN es conectar los dispositivos de los usuarios finales entre sí y con recursos centrales como servidores y almacenamiento. El número de dispositivos de usuario final (DUE) incluye:   - Todos los PC, terminales, clientes ligeros, PDA, smartphones y tabletas que puedan conectarse a la LAN; - Todas las impresoras conectadas en red; - Puntos de acceso inalámbricos (cuenta cada uno como un dispositivo de usuario final); - El número máximo de puertos de Acceso Remoto concurrentes; - Otros dispositivos periféricos del usuario o cliente, como cajeros automáticos, terminales de punto de venta, etc.   Cuando un router es operado por IT en las instalaciones de un tercero, el número de EUDs para este router es 1. Un ejemplo típico es cuando un banco instala uno de sus routers en los locales de una cámara de compensación, para garantizar la seguridad de las comunicaciones.  No incluya lo siguiente en el recuento de dispositivos de usuario final:   - Servidores - Los volúmenes de los servidores conectados a la WAN se recogen por separado en la torre de computación - Routers y switches (no suelen estar en manos de los usuarios).   Un punto de acceso inalámbrico (WAP) es un dispositivo que permite a los dispositivos inalámbricos conectarse a una red cableada mediante Wi-Fi o normas afines conformes a IEEE 802.11. El WAP suele conectarse a un router (a través de una red cableada) y puede retransmitir datos entre los dispositivos inalámbricos (como ordenadores o impresoras) y los dispositivos cableados de la red.  Los puertos de acceso remoto simultáneo se refieren al número de conexiones remotas simultáneas), que admiten VPN o accesos similares |
| LAN | Puertos LAN activos | Un puerto activo es un puerto de un switch o router que ha sido activado y/o habilitado para que un dispositivo pueda utilizarlo. Un puerto puede estar activo aunque no se esté utilizando en ese momento. Por ejemplo, para las organizaciones que utilizan hot-desking (o hotelling), los puertos LAN se consideran activos incluso si un usuario no está sentado en ese momento en el hot-desk (o escritorio de hotel). Un conmutador de red o "blade" (tarjeta) en un chasis de conmutador no se considera activo, si para su funcionamiento se requiere actividad MAC dura o blanda (por ejemplo, aplicar alimentación al conmutador); parchear físicamente el conmutador; o aplicar políticas ( QoS o VLAN) para la red. |
| Voz | Teléfono | El microteléfono es el instrumento de voz de punto final utilizado por un usuario para comunicarse con otra persona a través de una red de voz (RTPC o IP).  Incluye microteléfonos compatibles con PBX, Centrex, PBX Híbrida, Centrex Híbrida, VoIP y Soft Phones (el microteléfono es una combinación de una aplicación de software en un PC o estación de trabajo y un auricular/microteléfono conectado al PC o estación de trabajo).  La definición de microteléfono no incluye FAX, contestadores automáticos dedicados, sistemas de buzón de voz o sistemas interactivos de respuesta de voz (IVR). |
