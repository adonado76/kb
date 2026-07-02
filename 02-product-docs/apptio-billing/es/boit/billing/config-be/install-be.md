---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Instalación de los componentes de Billing Essentials"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/install-be.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Instalación de los componentes de Billing Essentials

Billing Essentials se entrega como componentes que se instalan en el proyecto Costing Essentials existente.

Pasos generales:

1. Abre el **proyecto Costing Essentials** en TBM Studio.
2. Navega hasta el área donde se gestionan los componentes.
3. Localizar e instalar:
   - Facturación – Cargo
   - Facturación – Informes de cargos
4. Confirme la instalación:
   - Crea los modelos y conjuntos de datos esperados.
   - Añade la colección de informes «Facturación» al proyecto.

Comprobaciones posteriores a la instalación:

- Verifique que los modelos de facturación se compilan sin errores en Desarrollo.
- Confirma que las nuevas tablas y métricas aparecen en el modelo de datos del proyecto.
- Confirme que la recopilación de informes «Facturación» aparece en el árbol de informes (aunque aún no se haya publicado en Producción).
