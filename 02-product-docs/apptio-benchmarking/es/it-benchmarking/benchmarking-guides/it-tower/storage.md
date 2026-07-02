---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Almacenamiento"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower/storage.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Almacenamiento

| Subtorre de recursos informáticos | Definiciones | Ejemplos | Unidad de medida (estándar) |
| --- | --- | --- | --- |
| Nivel 1 | Recursos de almacenamiento que permiten aplicaciones y servicios de misión crítica y requieren los más altos niveles de disponibilidad. | - FC SAN - NAS de gama alta - Conmutadores, discos, cableado y SSD - Replicación SW | TB instalada |
| Nivel 2 | Recursos de almacenamiento que permiten aplicaciones, servicios y datos esenciales pero no críticos para la misión; requiere un rendimiento de nivel de servicio relativamente alto. | - FC SAN - NAS de gama alta - Conmutadores, discos, cableado | TB instalada |
| Nivel 3 | Recursos de almacenamiento utilizados para información no esencial, histórica y de otro tipo en la que no se requiere disponibilidad inmediata. | - SAN, NAS - Conmutadores, discos, cableado - Disco a disco | TB instalada |
| Nivel 4 | Recursos de almacenamiento utilizados para el archivo, la copia de seguridad y la recuperación para soportar la pérdida de datos, la corrupción de datos, la recuperación de desastres y los requisitos de cumplimiento. | - Copia de seguridad en cinta - S/W de copia de seguridad/archivo | TB instalada |

**Composición del pool de costes de almacenamiento**

| Subtorre de recursos informáticos | Trabajo interno/externo | Hardware del sistema | Software | Servicios exteriores | Instalaciones y energía | Telecomunicaciones |
| --- | --- | --- | --- | --- | --- | --- |
| Nivel 1 | Analistas/ingenieros de almacenamiento que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Discos y controladores de almacenamiento, Servidores de almacenamiento, Conmutadores de fibra | Mantenimiento del almacenamiento, Replicación, Informes, Seguridad, Supervisión | Servicios gestionados de almacenamiento. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Nivel 2 | Analistas/ingenieros de almacenamiento que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Discos y controladores de almacenamiento, Servidores de almacenamiento, Conmutadores de fibra | Mantenimiento del almacenamiento, Replicación, Informes, Seguridad, Supervisión | Servicios gestionados de almacenamiento. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Nivel 3 | Analistas/ingenieros de almacenamiento que prestan apoyo y operaciones técnicas, planificación y gestión de procesos, administración (incluida la gestión) | Discos y controladores de almacenamiento, Servidores de almacenamiento, Conmutadores de fibra | Mantenimiento del almacenamiento, Replicación, Informes, Seguridad, Supervisión | Servicios gestionados de almacenamiento. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |
| Nivel 4 | Analistas/ingenieros de sistemas que prestan apoyo y operaciones técnicas (copia de seguridad en línea y gestión de cintas), planificación y gestión de procesos, administración (incluida la gestión) | Sistemas especializados de copia de seguridad/archivo, subsistemas de cinta, suministros fuera de línea (por ejemplo, cintas) | Mantenimiento de copias de seguridad/restauración/archivado, informes, seguridad, supervisión, gestión/migración de soportes | Servicios gestionados de almacenamiento. Servicios gestionados de archivo externo. | N/A (a nivel de torre, incluido en el TCO de los servicios tecnológicos) | N/D |

**Unidades de medida de almacenamiento**

| Subtorre de recursos informáticos | Unidad de medida (estándar) | Directrices |
| --- | --- | --- |
| Nivel 1 | Almacenamiento total en disco (bruto) instalado en TB | La capacidad física bruta máxima de todas las unidades de disco, tecnologías (es decir, SAN, NAS, iSCSI, CAS, DASD, etc.) y ubicaciones (incluidas las ubicaciones de recuperación de desastres). Por ejemplo, para una matriz de almacenamiento que contiene 64 unidades de disco clasificadas por el fabricante como unidades de 800 Gbytes, el almacenamiento en disco instalado es de 51.2 Tbytes.  Para matrices de almacenamiento virtual como RAMAC o ICEBERG, introduzca la capacidad máxima declarada por el proveedor del dispositivo tras la compresión, tal y como figura en los acuerdos de compra o en los folletos del producto.  Producción y conmutación por error - FC SAN, NAS de gama alta, SSD  Incluir almacenamiento Mainframe  Incluir volúmenes de recuperación de desastres |
| Nivel 2 | Almacenamiento total en disco (bruto) instalado en TB | No misión crítica, Desarrollo y pruebas  Incluir volúmenes de recuperación de desastres |
| Nivel 3 | Almacenamiento total en disco (bruto) instalado en TB | Almacenamiento para necesidades de menor rendimiento  Copias de seguridad de disco a disco, archivado en línea, VTL  Incluir volúmenes de recuperación de desastres |
| Nivel 4 | Total de almacenamiento en cinta instalado en TB | Copia de seguridad de la cinta  Incluir volúmenes de recuperación de desastres |
