---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Resumen y descripción general de las ediciones"
breadcrumb:
  - "Billing"
  - "Administración y operaciones"
  - "Edición y capacidades"
source_path: "boit/billing/edition-capabilities/es-intro.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Resumen y descripción general de las ediciones

La facturación está disponible en dos ediciones: **Billing Essentials** y **Billing Standard**.

Resuelven el mismo problema fundamental, pero con diferentes niveles de alcance y flexibilidad.

- Una organización determinada utiliza **una edición de facturación a la vez**, alineada con su proyecto de cálculo de costes.
- **Billing Essentials** se suministra a través de la plantilla de componentes **versión 200** junto con una implementación **de Costing Essentials**.
- **El estándar de facturación** se suministra a través de plantillas de componentes **de la versión 120 y anteriores**, junto con una implementación **del estándar de cálculo de costes**.

## Resumen de la edición

**Fundamentos de facturación**

- Se centra en implementar un **proceso de facturación o reporte de costes ( PxQ** ) limpio y repetible.
- Aparece como una **recopilación de informes de facturación** en el mismo proyecto que ejecuta Costing Essentials.
- La personalización se limita a los informes.
- Destaca:
  - Facturas sencillas y comprensibles.
  - Configuración sencilla de tarifas y cálculo de cargos.
  - Superficie de configuración mínima.

## Norma de facturación

- Incluye todas las funciones básicas de Billing Essentials.
- Añade un **conjunto más amplio de componentes** compatibles:
  - Vistas específicas del dominio (nube, servidores, almacenamiento, aplicaciones, proyectos, dispositivos de usuario final).
  - Análisis y optimización de la tasa unitaria.
  - Análisis de la variación entre el coste, el plan y el precio.
  - Informes entre empresas y entidades jurídicas.
- Expuesto a través de un **punto final de facturación independiente**, además del punto final del proyecto Costing Standard.

**Comparación de capacidades** La siguiente tabla resume las diferencias entre las ediciones en cuanto a las áreas de capacidad típicas.

| **Área de capacidad** | **Ejemplos** | **Fundamentos de facturación** | **Norma de facturación** |
| --- | --- | --- | --- |
| **Calificación de la esencia « PxQ »** | Multiplicar las unidades por las tarifas para calcular los cargos por período | Sí | Sí (incluye el comportamiento Essentials) |
| **Gestión de tarifas básicas** | Mantener las tablas de tarifas y marcar las ofertas como facturables | Sí | Sí (con vistas de tarifas específicas del dominio adicionales) |
| **Generación de facturas** | Informes, exportaciones y archivos en línea con formato de factura | Sí | Sí (más desgloses adicionales por dominio) |
| **Validación y revisión de facturas** | Validar los cargos antes de su liberación, investigar anomalías | Sí | Sí (con un desglose más detallado por dominio) |
| **Preparación del diario** | Exportar datos listos para el diario para Finanzas | Sí | Sí |
| **Vistas de facturación específicas de la nube** | Tarifas unitarias de la nube, desgloses a nivel de proveedor y a nivel de servicio | Limitado\* | Listo para usar (nube y componentes relacionados) |
| **Vistas centradas en la aplicación** | Cargos por aplicación, familia de aplicaciones o cartera | Limitado\* | Listo para usar (aplicaciones e informes relacionados) |
| **Vistas del dominio de infraestructura** | Servidores, almacenamiento, dispositivos de usuario final, etc. | Limitado\* | Listo para usar (servidores, almacenamiento, dispositivos de usuario final) |
| **Vistas centradas en proyectos** | Cargos y recuperación por proyecto, programa o iniciativa | Limitado\* | Fuera de la caja (Proyectos y vistas relacionadas) |
| **Análisis y optimización de la tasa unitaria** | Tendencias, varianza y análisis de factores determinantes para las tarifas unitarias | Limitado\* | Análisis ampliado y específico del dominio |
| **Coste frente a plan frente a variación de precios** | Comparar el coste real, el coste previsto y el precio/recuperación | Limitado\* | Fuera de la caja (variación de costes, variación del plan, precio) |
| **Precios de transferencia y entidades jurídicas** | Flujos entre empresas, visión de la entidad jurídica de los cargos y efectos fiscales | Nee | Listo para usar (precios de transferencia entre empresas, datos fiscales) |
| **Apoyo en escenarios/previsiones** | Compare diferentes supuestos de tarifas, volumen o servicios | Limitado\* | Ampliado (planificación más estructurada y uso de variaciones) |

\* Contenido limitado fuera de la caja. Las personalizaciones solo están permitidas para los informes.
