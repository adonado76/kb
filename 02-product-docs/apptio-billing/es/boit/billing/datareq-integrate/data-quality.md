---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Expectativas sobre la calidad de los datos"
breadcrumb:
  - "Billing"
  - "Requisitos e integración de datos"
source_path: "boit/billing/datareq-integrate/data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Expectativas sobre la calidad de los datos

Los datos erróneos aparecerán inmediatamente en los resultados de facturación: líneas que faltan, cargos inexplicables o tarifas que parecen incorrectas.

Como mínimo, espere mantener lo siguiente:

- **integridad referencial**
  - Todos los consumidores de Facturación deben figurar en el maestro de consumidores.
  - Todas las ofertas de consumo deben figurar en el catálogo de ofertas.
  - Todos los objetos de dominio (aplicación, servidor, cuenta en la nube, proyecto) utilizados en las vistas de facturación deben existir en su tabla maestra.
- **Integridad**
  - Los consumos de las ofertas clave deben estar completos para cada periodo de facturación.
  - Los atributos críticos de los datos maestros (por ejemplo, ID del consumidor, unidad de medida, período de vigencia, moneda) no deben dejarse en blanco.
- **Coherencia**
  - Los identificadores y las claves no deben cambiar arbitrariamente entre períodos.
  - Las jerarquías para los consumidores y las ofertas deben permanecer lo suficientemente estables como para marcar tendencia.
- **Comprobaciones de razonabilidad**
  - Busca:
    - Volúmenes nulos o negativos donde no deberían existir.
    - Aumentos o descensos repentinos en las unidades que no se explican por acontecimientos reales.
    - Tasas que parecen desviadas en órdenes de magnitud.

Estas comprobaciones pueden implementarse en los informes de costes o de facturación, pero deben formar parte de una rutina mensual estándar antes de que se publiquen las facturas.
