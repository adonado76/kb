---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Servicio sencillo de «showback» de « PxQ »"
breadcrumb:
  - "Billing"
  - "Patrones de diseño y casos de uso"
source_path: "boit/billing/design-uc/uc-simple.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Servicio sencillo de «showback» de « PxQ »

**Problema**

Quieres una vista mensual transparente que responda a:

«¿Quién utiliza qué servicios, cuánto utilizan y cuál es el coste calculado?»

**Entradas**

- Catálogo de servicios/ofertas con unidades e indicadores facturables
- Maestro de consumidores
- Datos de consumo mensual (unidades por servicio y consumidor)
- Tarifas por servicio y período

**Pasos**

1. Confirme que el **catálogo de ofertas** está actualizado y que los indicadores de facturación están configurados correctamente.
2. Cargar o actualizar **los datos de consumo** del periodo actual.
3. Cargar o confirmar **las tarifas** para cada oferta activa durante el período.
4. Ejecute los modelos de facturación en el entorno adecuado (en desarrollo/pruebas para realizar pruebas, en producción para su uso real).
5. Abre **la** factura/el informe resumido del periodo.
6. Filtrar por consumidor según sea necesario y confirmar:
   - Los servicios enumerados cumplen con las expectativas.
   - Las unidades y las tarifas parecen correctas.
   - Los cargos totales son razonables.

**Informes clave**

- Factura / informe resumido
- Informe resumido para el consumidor
- Informe de control de calidad/excepciones para mapeos faltantes
