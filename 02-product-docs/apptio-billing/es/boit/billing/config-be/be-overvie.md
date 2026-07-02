---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Ámbito de aplicación y requisitos previos"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/be-overvie.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ámbito de aplicación y requisitos previos

En esta sección se describe cómo se configura Billing Essentials en un proyecto de Costing Essentials, desde la instalación de los componentes hasta las primeras facturas utilizables. Se da por hecho que Costing Essentials ya está implementado y es estable.

Nota: Se aplica únicamente a Billing Essentials.

Los pasos de configuración en TBM Studio suelen ser realizados por un administrador con acceso a Studio o por un socio/equipo de IBM que actúa en nombre de la organización de TI.

## Ámbito de aplicación y requisitos previos

Antes de realizar cualquier cambio, confirme lo siguiente:

- La organización utiliza **Billing Essentials** (plantilla de componente versión 200).
- El proyecto **Costing Essentials** está en funcionamiento y utiliza entornos de desarrollo, prueba y producción.
- Existe un plan claro para:
  - Ofertas facturables (servicios/productos).
  - Consumidores (unidades de negocio, centros de coste, etc.).
  - Fuentes de consumo (cómo se medirá el uso).
  - Estrategia de tarifas (cómo se fijan y mantienen las tarifas).

Requisitos técnicos mínimos:

- Acceso al proyecto Costing Essentials en TBM Studio (para el equipo de configuración).
- Acuerdo sobre qué entornos utilizar para la configuración inicial, el control de calidad y la puesta en marcha.
