---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Servicios Primeros pasos"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso de la solución"
  - "Servicios"
source_path: "cost-transparency/solution-uc/services-gs.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Servicios Primeros pasos

Utilice el componente Servicios para consolidar y analizar los costes tecnológicos por servicio. El componente CT Apps - Servicios proporciona la estructura de datos y los objetos de modelo necesarios para la elaboración de informes y el análisis de los costes de los servicios.

Instale y configure el componente Servicios, luego cargue los datos de sus servicios, incluyendo definiciones de servicios, propiedad de los servicios, métricas de consumo y categorización de servicios. Una vez instalado el componente, asigne sus datos a las tablas adecuadas.

## Instalación de componentes

El componente CT Apps– Services proporciona visibilidad sobre el gasto en TI en servicios, lo que permite a las organizaciones comprender los costes totales de los servicios, realizar un seguimiento de los cambios en el gasto mensual y medir el rendimiento en comparación con el plan. Consolida los costes subyacentes de tecnología, aplicaciones, mano de obra y proveedores en una visión a nivel de servicio, lo que favorece la transparencia constante de los costes de los servicios y el análisis de la cartera.

## Componente instalado

**Aplicaciones de TC – Servicios**

El componente CT Apps – Services instala las estructuras de datos, los conjuntos de datos, las métricas y los informes fundamentales necesarios para analizar los costes, las tendencias y el rendimiento presupuestario de los servicios empresariales en toda la empresa.

**Aplicaciones de TC - Servicios - Informes NX (componente adicional)**

Este componente ofrece informes NX predefinidos basados en datos de servicios para realizar análisis por servicios, categorías y periodos de tiempo.

Utiliza este componente cuando:

- Necesitas informes de servicios estándar
- ¿Quieres analizar las tendencias en cuanto a costes y consumo?
- Necesitas informes periódicos sobre los servicios

## Requisitos previos

Debe instalar los siguientes componentes antes de instalar el componente Servicios:

• CTF: fuente de costes

• Torres CTF-IT

• Aplicaciones CT: aplicaciones

## Fuentes comunes de datos

Los datos de servicios empresariales suelen proceder de catálogos de servicios, sistemas CMDB, herramientas de gestión de carteras de aplicaciones y plataformas de gestión de servicios. Los datos que utilice determinarán el nivel de detalle disponible para el análisis de los costes del servicio y el seguimiento del consumo.

Las fuentes de datos comunes incluyen:

- **Plataformas de gestión de servicios:** definiciones de servicios, datos del catálogo de servicios y métricas de consumo ( ServiceNow, BMC Remedy, Cherwell).
- **Base de datos de gestión de la configuración (CMDB):** relaciones entre servicios y aplicaciones y mapeo de dependencias de servicios.
- **Gestión de la cartera de aplicaciones:** propiedad del servicio, fase del ciclo de vida del servicio y asignaciones de aplicaciones a servicios ( ServiceNow APM, LeanIX ).
- **Sistemas de gestión empresarial de TI:** datos sobre el coste de los servicios, volúmenes de consumo de servicios y métricas de nivel de servicio.
- **Catálogos de servicios:** definiciones de servicios publicados, descripciones de servicios y categorización de servicios.

## Conjuntos de datos

Deberá cargar los datos del servicio y asignarlos a la tabla Todos los servicios empresariales. Aunque no existe una tabla de datos maestros independiente para el componente CT Apps - Servicios, la tabla Todos los servicios empresariales cumple una función similar y contiene todas las definiciones y atributos de los servicios.

**Todos los servicios empresariales**

Esta tabla define todos los servicios empresariales de su cartera de servicios. Contiene la identificación del servicio, la categorización, la propiedad, las métricas de consumo y la configuración de la asignación. Todos los datos de servicio deben asignarse a esta tabla.
