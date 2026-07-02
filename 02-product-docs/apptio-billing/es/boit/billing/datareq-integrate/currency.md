---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Divisas y mercado de divisas"
breadcrumb:
  - "Billing"
  - "Requisitos e integración de datos"
source_path: "boit/billing/datareq-integrate/currency.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Divisas y mercado de divisas

La facturación puede operar en entornos multidivisa, pero suele ser más sencillo si los resultados de la facturación se presentan en una **única moneda de presentación** para las partes interesadas del negocio.

Puntos clave:

- **Monedas de origen**
  - El cálculo de costes puede recibir costes en múltiples divisas y convertirlos utilizando los tipos de cambio.
  - Los volúmenes de consumo suelen ser neutros en términos monetarios.
- **Moneda de presentación**
  - Decida en qué moneda deben presentarse las facturas y los diarios (por ejemplo, USD).
  - Asegúrese de que los tipos de cambio utilizados en el cálculo de costes se apliquen de forma coherente para que los cargos de facturación concuerden.
- **Facturación entre entidades**
  - Para escenarios de varios países o varias entidades, confirme lo siguiente:
    - ¿Qué tipos de cambio se utilizan para la facturación interna y para los informes externos?
    - Si la facturación debe reflejar el tipo de cambio por separado o solo el resultado convertido.

Documente la configuración de la moneda desde el principio y manténgala estable. Cambiar la lógica de FX a mitad de año puede crear confusión, a menos que se comunique claramente y sea trazable.
