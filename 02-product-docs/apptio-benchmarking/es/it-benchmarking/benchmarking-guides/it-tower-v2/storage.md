---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Almacenamiento"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v2/storage.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Almacenamiento

| Subtorre de recursos informáticos | Definiciones | Ejemplos | Coste unitario Unidad de medida (estándar) (véase [la definición](#unit "(se abre en una pestaña o una ventana nueva)") ) |
| --- | --- | --- | --- |
| En línea | Recursos de almacenamiento en línea conectados a servidores. Excluye el almacenamiento integrado (interno) en el servidor (está incluido en el coste del servidor). Esto incluye el almacenamiento de recuperación ante desastres. | SAN, NAS, CAS ( iSCSI, ) | TB instalada |
| Fuera de línea | Recursos de almacenamiento sin conexión conectados a los servidores. Esto incluye el almacenamiento de recuperación ante desastres. | Copia de seguridad en cinta S/W de copia de seguridad/archivo | TB instalada |
| Mainframe en línea | Recursos de almacenamiento en línea conectados a Mainframes. Esto incluye el almacenamiento de recuperación ante desastres. | SAN, NAS, CAS ( iSCSI, ) | TB instalada |
| Mainframe fuera de línea | Recursos de almacenamiento sin conexión conectados a Mainframes. Esto incluye el almacenamiento de recuperación ante desastres. | Copia de seguridad en cinta  S/W de copia de seguridad/archivo | TB instalada |

**Composición del pool de costes de almacenamiento**

| Subtorre de recursos informáticos | Trabajo interno/externo | Hardware del sistema | Software | Servicios exteriores | Instalaciones y energía | Telecomunicaciones |
| --- | --- | --- | --- | --- | --- | --- |
| En línea  Mainframe en línea | Analistas/ingenieros de almacenamiento que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Discos y controladores de almacenamiento, Servidores de almacenamiento, Conmutadores de fibra | Gestión del almacenamiento, virtualización, replicación, informes, seguridad, supervisión. Controladores y software de red para NAS. | Servicios gestionados de almacenamiento. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Fuera de línea  Mainframe fuera de línea | Analistas/ingenieros de sistemas que prestan apoyo y operaciones técnicas (copia de seguridad en línea y gestión de cintas), planificación y gestión de procesos, administración (incluida la gestión) | Sistemas especializados de copia de seguridad/archivo, subsistemas de cinta, suministros fuera de línea (por ejemplo, cintas) | Mantenimiento de copias de seguridad/restauración/archivado, informes, seguridad, supervisión, gestión/migración de soportes | Servicios gestionados de almacenamiento. Servicios gestionados de archivo externo. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |

**Unidades de medida de almacenamiento**

| Subtorre de recursos informáticos | Unidad de medida (estándar) | Directrices |
| --- | --- | --- |
| En línea  Mainframe en línea | Almacenamiento total en disco (bruto) instalado en TB | La capacidad física bruta máxima de todas las unidades de disco, tecnologías (es decir, SAN, NAS, iSCSI, CAS, DASD, etc.) y ubicaciones (incluidas las ubicaciones de recuperación de desastres). Por ejemplo, para una matriz de almacenamiento que contiene 64 unidades de disco clasificadas por el fabricante como unidades de 800 Gbytes, el almacenamiento en disco instalado es de 51.2 Tbytes.  Para matrices de almacenamiento virtual como RAMAC o ICEBERG, introduzca la capacidad máxima declarada por el proveedor del dispositivo tras la compresión, tal y como figura en los acuerdos de compra o en los folletos del producto.  Producción y conmutación por error - FC SAN, NAS de gama alta, SSD  Incluir volúmenes de recuperación de desastres |
| Fuera de línea  Mainframe fuera de línea | Total de almacenamiento en cinta instalado en TB | Copia de seguridad de la cinta  Incluir volúmenes de recuperación de desastres |
