---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Vendedor: Primeros pasos"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financiero"
  - "Proveedor"
source_path: "cost-transparency/it-financials/vendor-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Vendedor: Primeros pasos

Utilice la función Proveedores para analizar el gasto en proveedores de TI en toda la organización y respaldar la transparencia, la consolidación y las decisiones de optimización de los proveedores. Los informes de proveedores se habilitan instalando el componente **CTF – Vendors** y cargando los datos de gastos de proveedores en el proyecto Costing Standard.

Antes de utilizar los informes de proveedores, instale los componentes necesarios y asegúrese de que los datos de los proveedores se hayan cargado y asignado a la tabla de datos maestros de proveedores.

## Instalación de componentes

- **CTF – Proveedores** : el componente **CTF – Proveedores** permite realizar análisis de gastos a nivel de proveedor dentro de Costing Standard. No se instala automáticamente y debe añadirse explícitamente al proyecto.

Este componente permite:

- Visibilidad del gasto en proveedores en toda la organización
- Análisis de la concentración y fragmentación de los proveedores
- Informes de gastos de proveedores en centros de costes, proyectos y torres de recursos de TI

Después de instalar este componente, se deben cargar los datos de los proveedores y asignarlos a la tabla de datos maestros de proveedores para completar los informes de proveedores.

**CTF: Informes de proveedores NX (componente adicional)**

Este componente ofrece informes NX predefinidos basados en datos de proveedores para realizar análisis de costes por proveedor, categoría y periodo.

Utiliza este componente cuando:

- Necesitas informes de costes estándar de los proveedores
- ¿Quieres comparar los datos reales con los presupuestos?
- Necesitas que los proveedores te envíen informes de forma regular

## Requisitos previos

**CTF (fuente de costes** ): proporciona los datos básicos sobre costes necesarios para asociar los gastos con los proveedores.

**Fuentes comunes de datos** : los datos de los proveedores suelen proceder del libro mayor o de los datos maestros de los proveedores que se mantienen en los sistemas financieros. Estos sistemas proporcionan los identificadores de los proveedores y el gasto asociado necesario para la elaboración de informes a nivel de proveedor.

## Conjuntos de datos maestros

- **Datos maestros de proveedores** : la tabla de datos maestros de proveedores almacena los identificadores de proveedores y los atributos relacionados que se utilizan para el análisis a nivel de proveedor. Normalmente, se carga una tabla de datos de un único proveedor y se añade a esta tabla de datos maestros.

El conjunto de datos cargado debe incluir campos que puedan asignarse a la estructura de datos maestros del proveedor para permitir la elaboración de informes precisos.
