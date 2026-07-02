---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Preparación de datos de consumidores"
breadcrumb:
  - "Billing"
  - "Configuración de los elementos esenciales de facturación (implementación)"
source_path: "boit/billing/config-be/prepare.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Preparación de datos de consumidores

El modelo Billing Essentials necesita una visión coherente de a quién se le factura.

Pasos:

1. **Alinearse con la estructura de consumidores existente en Costing.**
   - Identifique el objeto o tabla «consumidor» utilizado por Costing (por ejemplo, unidades de negocio, centros de coste, departamentos).
   - Confirme la clave principal y la jerarquía.
2. **Asegúrese de que la cobertura sea completa.**
   - Confirme que todas las entidades que se espera facturar aparecen en el maestro de consumidores.
   - Añadir nuevas entradas para:
     - Nuevas unidades de negocio.
     - Nuevos centros de coste.
     - Nuevas entidades de proyecto o producto, si se tratan como consumidores.
3. **Validar asignaciones**
   - Si Billing utiliza tablas de mapeo (por ejemplo, mapeo de un ID externo al ID interno del consumidor), asegúrese de que:
     - Cada ID externo en los datos de consumo se asigna a un ID de consumidor interno.
     - Las entradas huérfanas se resuelven antes de la primera facturación.
