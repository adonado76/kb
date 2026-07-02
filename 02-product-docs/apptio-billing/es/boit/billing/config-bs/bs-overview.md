---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Ámbito de aplicación y requisitos previos"
breadcrumb:
  - "Billing"
  - "Configuración del estándar de facturación (implementación)"
source_path: "boit/billing/config-bs/bs-overview.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ámbito de aplicación y requisitos previos

En esta sección se describe cómo se configura Billing Standard sobre un proyecto Costing Standard, desde la instalación de los componentes hasta las primeras facturas con dominios enriquecidos utilizables. Se da por hecho que Costing Standard ya está implementado y es estable.

Nota: Se aplica únicamente a la norma de facturación.

La configuración en TBM Studio normalmente la realiza un administrador o una persona con un rol equivalente que tenga acceso a Studio.

## Ámbito de aplicación y requisitos previos

Antes de realizar cambios, confirme:

- La organización utiliza **el estándar de facturación** (plantilla de componentes versión 120 o anterior).
- Existe un proyecto **de norma de cálculo de costes** con:
  - En entornos de desarrollo, prueba y producción.
  - Un modelo de costes operativo que ya admite torres tecnológicas, aplicaciones, servicios y consumidores.
- Hay un diseño claro para:
  - Ofertas facturables (servicios/productos).
  - Consumidores (unidades de negocio, centros de coste, proyectos, productos, etc.).
  - Modelado de dominios:
    - Aplicaciones
    - Los servidores y el almacenamiento
    - Cuentas y servicios en la nube
    - Dispositivos de usuario final
    - Proyectos
    - Las personas jurídicas, si los precios de transferencia están dentro del ámbito de aplicación
    - Estrategia de tarifas y enfoque de varianza (coste frente a plan frente a precio).

Requisitos técnicos previos:

- Acceso de TBM Studio al proyecto Costing Standard.
- Acuerdo sobre qué dominios se utilizarán activamente en el momento del lanzamiento y cuáles se introducirán gradualmente más adelante.
