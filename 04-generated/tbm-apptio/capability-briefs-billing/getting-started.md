---
concept: "Getting Started (posicionamiento de Billing, ediciones, conceptos fundacionales, roles y permisos)"
practice: tbm
language: en
doc_type: capability_brief
products_covered:
  - apptio-billing
status: draft
generated_from:
  - kb/02-product-docs/apptio-billing-standard/en/billing.md
  - kb/02-product-docs/apptio-billing-standard/en/billing-overview.md
  - kb/02-product-docs/apptio-billing-standard/en/billing-editions-costing-editions.md
  - kb/02-product-docs/apptio-billing-standard/en/billing-core-concepts-services-units-rates-recovery-journals.md
  - kb/02-product-docs/apptio-billing-standard/en/billing-key-benefits.md
  - kb/02-product-docs/apptio-billing-standard/en/started-glossary-acronyms.md
  - kb/02-product-docs/apptio-billing-standard/en/permissions-overview-roles.md
  - kb/02-product-docs/apptio-billing-standard/en/permissions-access-types-billing-standard.md
  - kb/02-product-docs/apptio-billing-standard/en/permissions-access-patterns-billing-essentials.md
  - kb/02-product-docs/apptio-billing-standard/en/permissions-access-patterns-billing-standard.md
  - kb/02-product-docs/apptio-billing-standard/en/permissions-segregation-duties-recommended-practices.md
  - kb/02-product-docs/apptio-billing-standard/en/permissions-managing-access-over-time.md
  - kb/02-product-docs/apptio-billing-standard/en/started-support-resources.md
last_updated: "2026-07-06"
---
# Getting Started — Cómo Apptio Billing Aborda Esta Capacidad

## El concepto

Costing Standard responde qué costó la tecnología; Billing responde una pregunta distinta y posterior: cómo se convierte ese costo ya calculado en una factura o un cargo que un consumidor interno del negocio puede entender, cuestionar y, eventualmente, pagar o presupuestar. Billing es, en la propia definición del producto, **la capa de contenido que transforma datos de costo y consumo de Tecnología en cargos facturables y reportes listos para entregar a consumidores internos**. Sin esta capa, un modelo de costeo TBM maduro puede decir "cuánto cuesta el servicio X en total", pero no puede decirle a un consumidor específico "esto es lo que te toca pagar a ti, por lo que realmente consumiste, a esta tarifa".

## Cómo lo resuelve Apptio Billing

**Dos ediciones, no una sola solución monolítica.** Billing se ofrece en dos ediciones — **Billing Essentials** y **Billing Standard** — con distinto nivel de sofisticación de modelo y distinto esfuerzo de implementación. Esta distinción de edición aparece de forma consistente a lo largo de toda la documentación (permisos, implementación, arquitectura, reportes se documentan por separado para cada edición), y es la primera decisión de alcance que hay que tomar con un cliente. La relación con Costing es explícita: Billing consume el modelo de costo ya construido en Costing (Standard o Essentials) como su fuente de verdad — Billing no recalcula el costo desde cero, lo traduce en cargos.

**Cinco conceptos fundacionales que se repiten en todo el producto:**
- **Services** — la unidad de negocio que se factura (una aplicación, una plataforma, un servicio compartido de TI).
- **Units** — la métrica de consumo que dirige el cargo (usuarios, transacciones, GB, horas de cómputo).
- **Rates** — el precio por unidad, definido y gestionado por el equipo de Billing, normalmente en un ciclo de planeación anual.
- **Recovery** — el mecanismo por el cual el costo total del servicio se "recupera" del conjunto de consumidores, ponderado por su consumo real.
- **Journals** — el mecanismo de salida financiera: entradas contables generadas a partir de los cargos calculados, listas para exportarse hacia el sistema financiero del cliente (ERP/libro mayor) para chargeback real, no solo showback informativo.

Estos cinco términos son el vocabulario mínimo indispensable antes de tener cualquier conversación técnica sobre Billing — son, para Billing, el equivalente de lo que ATUM/Cost Pool/Resource Tower son para Costing Standard.

**Beneficios clave documentados**: transparencia de costo hacia el consumidor de negocio, incentivos de consumo responsable (al ver el cargo real asociado a su uso, un consumidor tiene motivo para optimizar), y una vía formal de chargeback que conecta el modelo TBM con el proceso financiero real de la organización (vía journals), no solo con un reporte informativo.

**Modelo de roles y permisos, diferenciado por edición.** La documentación distingue explícitamente los patrones de acceso para Billing Essentials de los de Billing Standard — la edición más simple (Essentials) tiene un modelo de permisos más acotado, mientras Standard, al tener más objetos de dominio configurables, requiere un modelo de permisos más granular. Se documentan explícitamente **patrones de segregación de funciones** (quién puede definir tarifas vs. quién puede aprobar su publicación vs. quién solo consume reportes) y una guía específica de **cómo gestionar el acceso a lo largo del tiempo** — reconociendo que el modelo de permisos de un proyecto de Billing no es estático, cambia según la fase de madurez del programa.

**Canales de soporte** están documentados como una sección propia dentro de Getting Started, consistente con el patrón ya visto en Costing Standard y Planning.

## Por qué importa en una conversación con el cliente

La elección Essentials vs. Standard es, otra vez —como ya vimos repetidamente en Costing Standard con sus pares de soluciones (Public Cloud, Compute, Storage, Service Desk)— la pregunta de discovery más importante y la palanca de venta incremental más natural: un cliente puede empezar con Essentials para un chargeback rápido y simple, y migrar a Standard cuando necesite lógica de precio y varianza más sofisticada.

Los cinco conceptos fundacionales (Services, Units, Rates, Recovery, Journals) son el vocabulario que hay que fijar en la primera conversación técnica — en particular, la distinción entre Recovery (el mecanismo de reparto del costo total) y Rates (el precio unitario ya definido) suele confundirse, y vale la pena aclararla con un ejemplo concreto antes de avanzar.

El énfasis explícito en Journals como mecanismo de salida (no solo un reporte, sino una integración real hacia el sistema financiero) es un diferenciador importante frente a la percepción común de que "billing interno" es solo un ejercicio de reporting — vale la pena posicionar desde el inicio que Billing puede llegar hasta el asiento contable real, si el cliente lo necesita.

## Documentos fuente

- Billing (introducción de producto) — `kb/02-product-docs/apptio-billing-standard/en/billing.md`
- Billing overview — `kb/02-product-docs/apptio-billing-standard/en/billing-overview.md`
- Billing editions and Costing editions — `kb/02-product-docs/apptio-billing-standard/en/billing-editions-costing-editions.md`
- Core concepts: services, units, rates, recovery, journals — `kb/02-product-docs/apptio-billing-standard/en/billing-core-concepts-services-units-rates-recovery-journals.md`
- Key benefits — `kb/02-product-docs/apptio-billing-standard/en/billing-key-benefits.md`
- Glossary & Acronyms — `kb/02-product-docs/apptio-billing-standard/en/started-glossary-acronyms.md`
- Overview and roles — `kb/02-product-docs/apptio-billing-standard/en/permissions-overview-roles.md`
- Permissions and access types for Billing Standard — `kb/02-product-docs/apptio-billing-standard/en/permissions-access-types-billing-standard.md`
- Access patterns for Billing Essentials — `kb/02-product-docs/apptio-billing-standard/en/permissions-access-patterns-billing-essentials.md`
- Access patterns for Billing Standard — `kb/02-product-docs/apptio-billing-standard/en/permissions-access-patterns-billing-standard.md`
- Segregation of duties and recommended practices — `kb/02-product-docs/apptio-billing-standard/en/permissions-segregation-duties-recommended-practices.md`
- Managing access over time — `kb/02-product-docs/apptio-billing-standard/en/permissions-managing-access-over-time.md`
- Support resources — `kb/02-product-docs/apptio-billing-standard/en/started-support-resources.md`

*Nota: versión en español/portugués se genera en una siguiente pasada. Hipervínculos a documentación oficial de IBM pendientes de verificación individual.*