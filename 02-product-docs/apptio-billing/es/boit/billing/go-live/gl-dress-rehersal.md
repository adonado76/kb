---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Ensayo general"
breadcrumb:
  - "Billing"
  - "Manual de puesta en marcha"
source_path: "boit/billing/go-live/gl-dress-rehersal.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Ensayo general

Un ensayo general es una ejecución completa de principio a fin en **Desarrollo** y verificada en **Preproducción** que imita lo que se publicará en Producción.

## Ámbito del ensayo general

Como mínimo, el ensayo debe incluir:

- Actualización de datos para el período seleccionado (o un período de prueba realista) en Desarrollo.
- Ejecuciones de cálculo de costes completos que alimentan la facturación en desarrollo.
- Facturación completa en desarrollo:
  - Cálculo del núcleo PxQ.
  - Cualquier modelo específico del dominio dentro del ámbito (por ejemplo, nube, proyectos, aplicaciones).
- Validación del informe en Desarrollo:
  - Vistas de facturas/resúmenes.
  - Vistas detalladas/desglosadas.
  - Diarios y exportaciones.
- Controles de calidad en la fase de preparación:
  - Comprobaciones estructurales, de volumen y de velocidad.
  - Conciliación con el cálculo de costes, cuando proceda.

Si alguno de ellos falla, no estás listo para la puesta en marcha de la producción.

## Documentación de los resultados del control de calidad

Registrar, al menos:

- ¿Qué ID de compilación de Staging se utilizó?
- ¿Qué conjuntos de datos se cargaron y qué fechas abarcan?
- Cualquier anomalía detectada y cómo se abordó.
- Firmas de:
  - Administrador/Analista (validez técnica).
  - Finanzas (si se incluyen las devoluciones/diarios).
  - Uno o dos propietarios clave de servicios o productos.

Esto se convierte en tu referencia cuando alguien te pregunte más adelante: «¿Qué cambió en el momento del lanzamiento?»
