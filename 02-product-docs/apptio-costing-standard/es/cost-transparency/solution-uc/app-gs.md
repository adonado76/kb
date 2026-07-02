---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Aplicaciones Introducción"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de la solución"
  - "Aplicaciones"
source_path: "cost-transparency/solution-uc/app-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Aplicaciones Introducción

El componente Aplicaciones forma parte del módulo Aplicaciones y servicios de transparencia de costes. Permite a las organizaciones asignar los costes relacionados con la infraestructura y las aplicaciones a estas últimas, con el fin de calcular con precisión el coste total de propiedad (TCO) de las aplicaciones. Este componente instala las estructuras de datos, métricas e informes necesarios para analizar los costes de las aplicaciones en materia de mano de obra, infraestructura, proyectos y servicios de apoyo.

## Instalación de componentes

**CT Apps – Aplicaciones**

El componente Aplicaciones instala nuevos conjuntos de datos, métricas e informes, lo que ayuda a asignar los costes relacionados con la infraestructura y las aplicaciones para determinar el coste total de propiedad (TCO) de las aplicaciones de la empresa.

**Aplicaciones CT: Informes NX (componente adicional)**

Este componente ofrece informes NX predefinidos basados en los datos de la aplicación para realizar análisis que abarquen diferentes aplicaciones, carteras y periodos de tiempo.

Utiliza este componente cuando:

- Necesitas informes de aplicación estándar
- ¿Quieres analizar las tendencias en cuanto a costes y consumo?
- Necesitas informes periódicos sobre las aplicaciones

## Requisitos previos

Debe instalar los siguientes componentes antes de instalar el componente Aplicaciones:

- CTF: Fuente de costes
- CTF- Torres de TI

**Fuentes comunes de datos**

Los datos sobre los costes y las características de las aplicaciones suelen proceder de sistemas de contabilidad general, plataformas de inventario de aplicaciones o CMDB, herramientas de gestión de proyectos y carteras, y sistemas de gestión de servicios de TI. Los costes relacionados con la infraestructura proceden de fuentes de datos de computación, almacenamiento, servicio técnico y proyectos ya configuradas en el modelo de costes.

## Conjuntos de datos

Al instalar el componente CT Apps – Aplicaciones, se crea un nuevo grupo Aplicaciones con las siguientes tablas:

- Aplicaciones (tabla modelo)
- Aplicaciones Datos maestros

Después de cargar los datos de la aplicación, asigne el conjunto de datos a la tabla de datos maestros de aplicaciones. Después de mapear los datos, se debe asignar valor desde las torres de recursos de TI, servidores, tickets y proyectos a las aplicaciones en el modelo de costes.
