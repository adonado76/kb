---
source_system: "apptio-benchmarking"
practice: "tbm"
language: "es"
doc_type: "it-benchmarking"
title: "Calidad de los datos y rutinas de validación"
breadcrumb:
  - "Benchmarking"
  - "Informes comparativos"
  - "Operaciones y gobernanza"
source_path: "it-benchmarking/operations-governance/data-quality.html"
images: []
capability_ids: []
last_updated: "2026-05-18"
summary: ""
---
# Calidad de los datos y rutinas de validación

Los puntos de referencia son una buena forma de detectar problemas de modelado. Úsalas en lugar de ocultarlas.

## Validación anual

En cada actualización anual:

- Compare **la estructura de TI ( OpEx )** con la del año anterior:
  - Los grandes cambios deben corresponder a acontecimientos reales (migraciones, reestructuraciones) o a cambios explícitos en los modelos.
- Compare **los costes unitarios clave de infraestructura** con respecto al año anterior:
  - Los grandes saltos justifican una comprobación tanto de los datos de costes como de volumen.
- Conciliar **los ratios de gasto en TI frente a los ingresos** con Finanzas para garantizar el nivel establecido.

Si un salto se debe a un cambio en el modelo TBM, indique claramente ese año como un «cambio estructural» en su documentación o comentario.

## Comprobaciones de cordura antes del uso ejecutivo

Antes de cualquier reunión importante:

- Confirme que los filtros de pares reflejan la historia: sector, rango de tamaño, región, año.
- Asegúrate de poder responder:
  - ¿Qué incluye esta métrica?
  - ¿Con quién nos comparamos?
  - ¿Es probable que esta diferencia sea real o se basa en los datos?

Si no puede responder a estas preguntas en un lenguaje sencillo, no utilice esa vista todavía. Corrija la configuración o vuelva a consultar la métrica en [Referencia de datos y metodología](../home.html#benchmarking__data-methodology).
