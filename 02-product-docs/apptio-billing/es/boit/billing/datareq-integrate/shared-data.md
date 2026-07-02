---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Fundamentos de datos compartidos"
breadcrumb:
  - "Billing"
  - "Requisitos e integración de datos"
source_path: "boit/billing/datareq-integrate/shared-data.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Fundamentos de datos compartidos

La facturación se sitúa por encima del cálculo de costes. Si los datos que alimentan el cálculo de costes y la facturación son deficientes, las facturas serán deficientes. En esta sección se detalla qué datos necesita el departamento de facturación, cómo se estructuran normalmente y dónde suele producirse la integración.

Tanto Billing Essentials como Billing Standard se basan en unos pocos fundamentos comunes:

- **Consumidores**
  - Unidades de negocio, centros de coste, departamentos, proyectos u otras entidades que reciben cargos.
  - Debe tener identificadores únicos y estables, y una jerarquía (por ejemplo, BU → Departamento → Centro de costes).
- **Ofertas (servicios/productos)**
  - El catálogo de lo que se está facturando.
  - Cada oferta debe incluir:
    - Un identificador único.
    - Un nombre reconocible para los interesados en el negocio.
    - Una unidad de medida (por ejemplo, usuarios por mes, GB por mes).
    - Un estado (activo, jubilado, solo interno).
- **Consumo**
  - Registros que muestran «cuánto de qué» ha consumido un consumidor en un periodo determinado.
  - Necesita como mínimo:
    - Identificación del consumidor.
    - Ofrecer ID (o algo explícitamente asignado a ella).
    - Punto.
    - Unidades consumidas.
- **Tarifas**
  - Precio o recuperación por unidad.
  - Debe estar vinculado a las ofertas y los periodos, y poder recuperarse de forma determinista (por ejemplo, tipo efectivo para ese periodo).

- **Resultados del cálculo de costes**
  - Resultados de cálculo de costes que representan el lado de los costes (por ejemplo, coste por unidad, coste por servicio, coste por consumidor) que Facturación puede utilizar para:
    - Validación de tarifas.
    - Análisis de varianza.
    - Ajustes o precios basados en los costes.

Si estas bases son inestables o incompletas, es probable que surjan problemas más adelante: cargos que faltan, tarifas inexplicables o facturas que no se pueden conciliar con los costes.
