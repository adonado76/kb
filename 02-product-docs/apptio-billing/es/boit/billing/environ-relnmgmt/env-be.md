---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Flujo de entorno para Billing Essentials"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Entornos y gestión de lanzamientos"
source_path: "boit/billing/environ-relnmgmt/env-be.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Flujo de entorno para Billing Essentials

Nota: Se aplica únicamente a Billing Essentials.

Billing Essentials forma parte del proyecto Costing Essentials y sigue su ciclo de vida ambiental.

Implicaciones:

- Cualquier cambio en la configuración de Billing Essentials (modelos, tablas, informes) se realiza **en** Desarrollo del proyecto Costing Essentials.
- Cuando se registran los artículos:
  - Se crea una nueva compilación en desarrollo.
  - Se crea automáticamente una compilación de ensayo correspondiente.
- El control de calidad de Billing Essentials se realiza sobre la versión **preliminar** del proyecto Costing Essentials:
  - Ejecutar modelos de Billing Essentials o procesos programados.
  - Abrir y validar los informes de Billing Essentials.
  - Comprueba que las facturas, las vistas detalladas y los archivos coincidan con lo esperado.

Cuando se promueve la compilación de ensayo:

- El entorno **de producción** para Costing Essentials y Billing Essentials se actualiza conjuntamente.
- Los usuarios finales verán el comportamiento y los informes actualizados de Billing Essentials una vez que finalice la promoción.

<imagen: muestra una vista de compilaciones o versiones para un proyecto de Costing Essentials, destacando una compilación específica con una nota que menciona los cambios de Billing Essentials en su descripción>

Recomendaciones operativas:

- Documento que recoge los cambios realizados en Billing Essentials para que puedan rastrearse durante la investigación de incidencias.
- Alinee los lanzamientos de Billing Essentials con los lanzamientos de Costing Essentials siempre que sea posible para simplificar la comunicación con las partes interesadas.
