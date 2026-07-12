---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Coste total de propiedad de los centros de datos: primeros pasos"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de infraestructura"
  - "Centros de datos"
source_path: "cost-transparency/infra-use-cases/dc-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Coste total de propiedad de los centros de datos: primeros pasos

La solución de coste total de propiedad (TCO) para centros de datos permite a las organizaciones conocer el coste total, la capacidad, la utilización y las limitaciones operativas de su infraestructura de centros de datos. Ofrece información sobre los costes de las instalaciones, el consumo de energía y refrigeración, la densidad de los racks y la asignación de recursos de infraestructura, con el fin de facilitar la optimización, la consolidación y la planificación de inversiones a largo plazo.

## Instalación de componentes

**Coste total de propiedad de los centros de datos**

El componente «TCO de los centros de datos» proporciona el marco básico necesario para modelar, asignar y elaborar informes sobre los costes, la capacidad, la utilización y las limitaciones operativas de los centros de datos. El componente instala los conjuntos de datos, las tablas editables, las métricas, la lógica de asignación y las estructuras de datos básicas necesarias para analizar las operaciones del centro de datos y establecer una economía unitaria fundamentada en todas las ubicaciones e instalaciones.

Este componente es necesario antes de instalar cualquiera de los componentes de generación de informes que se indican a continuación:

- **Informes sobre el coste total de propiedad (TCO** ) de los centros de datos: instala los informes clásicos para la elaboración de informes y el análisis del coste total de propiedad (TCO) de los centros de datos
- **Informes** de TCO de centros de datos en NX: instala los informes de NX para la elaboración de informes y el análisis del TCO de los centros de datos.

Los clientes pueden instalar el componente de generación de informes Classic o NX, según sus preferencias en cuanto a la experiencia de generación de informes. No obstante, el componente básico del coste total de propiedad (TCO) de los centros de datos debe instalarse primero en todos los casos.

## Requisitos previos

Debe instalar los siguientes componentes antes de instalar la solución Data Centers TCO:

- CTF – Fuente de costes
- CTF – IT Towers
- CTF – Trabajo
- CTF – Proveedores

Entre los componentes opcionales se incluyen:

- Aplicaciones CT – Servidores
- Aplicaciones de TC – Almacenamiento
- Aplicaciones CT – Mainframes
- CT Apps – Aplicaciones
- Aplicaciones de TC – Servicios
- Coste total de propiedad del producto

## Fuentes habituales de datos

Los datos sobre costes, utilización y operaciones de los centros de datos suelen proceder de:

- Sistemas de contabilidad general y sistemas financieros
- Plataformas de gestión de la infraestructura de centros de datos (DCIM)
- Sistemas de monitorización de la alimentación y la refrigeración
- CMDB y plataformas de gestión de activos
- Sistemas de gestión de instalaciones
- Sistemas de proveedores y de compras

Estas fuentes proporcionan metadatos financieros, de capacidad, de infraestructura y operativos que se utilizan para la asignación de recursos, el análisis de la utilización y la elaboración de informes sobre la rentabilidad de las unidades.

## Conjuntos de datos

El conjunto de datos principal para la solución es la tabla «Data Centers Feed». Carga y asigna los datos operativos, financieros y de capacidad del centro de datos a los datos maestros de centros de datos que se incluyen con el componente.

Entre los atributos habituales de los conjuntos de datos se incluyen:

- Nombre e identificación del centro de datos
- Región y tipo de centro
- Capacidad y uso de las unidades de rack
- Potencia y consumo
- Capacidad de refrigeración y utilización
- Superficie útil y espacio ocupado
- Administrador, nivel y metadatos operativos

Una vez cargados y asignados los datos, compruebe que las asignaciones sean correctas para garantizar que los costes del centro de datos se distribuyan adecuadamente entre los objetos de computación, almacenamiento e infraestructura de apoyo, con vistas a la elaboración de informes y análisis posteriores.
