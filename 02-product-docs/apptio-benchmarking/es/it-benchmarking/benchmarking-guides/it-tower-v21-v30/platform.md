---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Plataforma"
breadcrumb: []
source_path: "it-benchmarking/benchmarking-guides/it-tower-v21-v30/platform.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Plataforma

| Subtorre de recursos informáticos | Definiciones | Ejemplos | Coste unitario Unidad de medida (estándar) | ETC Eficacia Unidad de medida |
| --- | --- | --- | --- | --- |
| Base de datos | Sistemas de gestión de bases de datos (SGBD) basados en servidor, como Oracle. | MS SQL  Oracle en los servidores | Instancias de la base de datos | Instancias de base de datos por servidor ETC de base de datos |
| Middleware | Middleware de servidor: software que vincula bases de datos y servidores de diferentes arquitecturas, y el esfuerzo necesario para soportarlo. | WebSphere, ColdFusion, JBoss, Apache. | Instancias de middleware | Instancias de middleware por servidor ETC de middleware |
| Base de datos Mainframe | Sistemas de gestión de bases de datos basados en mainframe, como DB2 | DB2  Oracle en mainframe | Bases de datos | Bases de datos por ETC de base de datos mainframe |
| Middleware de Mainframe | Mainframe Middleware: software que enlaza bases de datos y mainframes de diferentes arquitecturas, y el esfuerzo necesario para soportarlo. | IBM MQ Series | Instancias de middleware | Instancias de middleware por ETC de middleware de mainframe |

**Composición del Pool de Costes de la Plataforma**

| Subtorre de recursos informáticos | Trabajo interno/externo | Hardware del sistema | Software | Servicios exteriores | Instalaciones y energía | Telecomunicaciones |
| --- | --- | --- | --- | --- | --- | --- |
| Base de datos | Personal para asistencia operativa y de segundo nivel, incluida la administración, configuración, actualizaciones, etc. | N/D | Software de bases de datos | Servicios gestionados para bases de datos de servidores | N/D | N/D |
| Middleware | Personal para asistencia operativa y de segundo nivel, incluida la administración, configuración, actualizaciones, etc. | N/D | Software intermedio | Servicios gestionados para middleware de servidor | N/D | N/D |
| Base de datos Mainframe | Personal para asistencia operativa y de segundo nivel, incluida la administración, configuración, actualizaciones, etc. | N/D | Software de bases de datos | Servicios gestionados para bases de datos mainframe | N/D | N/D |
| Middleware de Mainframe | Personal para asistencia operativa y de segundo nivel, incluida la administración, configuración, actualizaciones, etc. | N/D | Software intermedio | Servicios gestionados para middleware de mainframe | N/D | N/D |

**Plataforma Unidad de medida**

| Subtorre de recursos informáticos | Unidad de medida (estándar) | Directrices |
| --- | --- | --- |
| Base de datos | Instancias de la base de datos | Una instancia de base de datos es una base de datos lógica alojada en una instalación DBMS. Nota: En algunos casos, un SGBD puede alojar varias instancias de base de datos. Las tablas del sistema y otros datos maestros no se contabilizan y sólo se contabilizan los datos proporcionados a los usuarios finales y a las aplicaciones de usuario final (incluidas las bases de datos de desarrollo y de prueba). |
| Base de datos Mainframe | Bases de datos | Se trata de un subproceso de bases de datos (suministro de sistemas de gestión de bases de datos (SGBD) como DB2 y Oracle en plataformas Mainframe). |
| Middleware  Middleware de Mainframe | Instancias de middleware | Número de instancias del paquete middleware. |
