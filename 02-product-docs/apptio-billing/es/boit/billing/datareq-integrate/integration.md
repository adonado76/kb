---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Mecanismos de integración y opciones fuera de Studio"
breadcrumb:
  - "Billing"
  - "Requisitos e integración de datos"
source_path: "boit/billing/datareq-integrate/integration.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Mecanismos de integración y opciones fuera de Studio

Los datos pueden llegar a Facturación a través de varios mecanismos. Las que se utilicen dependerán de quién gestione la implementación y de las herramientas disponibles.

Opciones comunes:

- **ETL estructurado en TBM Studio**
  - Se utiliza cuando la organización de TI, el socio o el equipo de IBM tiene acceso completo a Studio y a la integración.
  - Adecuado para fuentes recurrentes de CMDB, PPM, proveedores de servicios en la nube, RR. HH. y Finanzas.
- **Datalink o plataformas de integración**
  - Se utiliza para automatizar la ingesta desde múltiples sistemas sin necesidad de manipular archivos manualmente.
  - Útil cuando los sistemas de origen están basados en la nube o cuando se requieren actualizaciones casi en tiempo real.
- **Carga de tablas y mantenimiento del front-end**
  - Se utiliza cuando el acceso al estudio es limitado o cuando ciertos datos de referencia son gestionados por equipos orientados al negocio.
  - Ejemplos:
    - Cargando tablas de tarifas actualizadas.
    - Actualización de pequeñas listas de referencia para ofertas o tablas de correspondencias.

Directrices:

- Utilice la integración automatizada para datos de gran volumen o que cambian con frecuencia (por ejemplo, consumo, uso de la nube, coste de proyectos).
- Reserve las cargas manuales para:
  - Tablas pequeñas que cambian con poca frecuencia (por ejemplo, un catálogo de productos o una lista de tarifas).
  - Ajustes controlados o correcciones puntuales.

Las secciones posteriores de esta guía dan por sentado que estos requisitos de datos y patrones de integración están establecidos al describir los pasos de configuración, el ciclo de facturación y cómo interpretar los resultados de facturación.
