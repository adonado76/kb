---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Arquitectura de Billing Essentials"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Arquitectura de soluciones y dependencias"
source_path: "boit/billing/sol-arch-depend/be-arch.html"
images:
  - "resources/images/boit_images/bearch.png"
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Arquitectura de Billing Essentials

Billing Essentials se implementa dentro del mismo proyecto que ejecuta Costing Essentials. No hay un punto final independiente para Billing Essentials. Todo el contenido se entrega como componentes adicionales y colecciones de informes dentro de ese proyecto.

Nota: Se aplica únicamente a Billing Essentials.

Elementos fundamentales:

- **Componentes**
  - Facturación - Cargo
  - Facturación: informe de cargos
- **Dónde se instalan**
  - Instalado por TAS o un socio en el proyecto Costing Essentials utilizando TBM Studio.
  - Añadir modelos, tablas, métricas y definiciones de informes que respalden el proceso de facturación.
- **Cómo lo ven los usuarios**
  - Expuesto como una **recopilación de informes de «facturación»** en la interfaz de Costing Essentials.
  - Los usuarios acceden a los informes de Billing Essentials de la misma manera que acceden a otros informes de Costing Essentials.

![](../../../../../../03-media/apptio-billing/resources/images/boit_images/bearch.png)

Fig. n.º: Componentes «Facturación-Cargo» y «Informes de facturación-Cargo» resaltados

Dependencias y supuestos:

- El proyecto Costing Essentials ya está implementado y recibiendo datos sobre costes y consumo.
- Las tablas de elementos esenciales de facturación requeridos se rellenan con:
  - Catálogo de ofertas facturables.
  - Identificadores de consumidores.
  - Unidades y tarifas.
- Los usuarios que necesitan acceder a los informes de Billing Essentials tienen acceso frontal al proyecto y a la colección de informes de facturación.
