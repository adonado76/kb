---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Referencia para la resolución de problemas de asignación"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear modelos de costes"
  - "Crear asignaciones"
source_path: "studio/new-uc/howtoguides/build-cost-model/troubleshoot-alloc.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Referencia para la resolución de problemas de asignación

## Mensajes de error habituales y soluciones

|  |  |  |
| --- | --- | --- |
| **Mensaje de error** | **Causa** | **Solución** |
| No se han encontrado claves vinculadas | No existen columnas coincidentes o no contienen valores comunes | Comprueba los nombres de las columnas y verifica que haya datos en ambas tablas |
| No se han encontrado enlaces de columnas | La asignación automática heredada no encuentra columnas coincidentes | Cambia a la coincidencia explícita de claves; desactiva la relación automática |
| La tabla de ratios de asignación es demasiado grande | Demasiadas combinaciones de origen y destino | Añade relaciones entre datos para limitar el ámbito; reduce la granularidad de los identificadores |

## Lista de comprobación para cuando la asignación no funciona

Cuando las asignaciones den resultados inesperados, comprueba lo siguiente:

- Se han desprotegido tanto la tabla de origen como la de destino
- El paso del modelo existe en ambas tablas
- La asignación se guarda (no solo se previsualiza)
- En ambas tablas hay columnas coincidentes con valores comunes
- La columna de ponderación es numérica y no contiene valores nulos ni negativos
- Los filtros no excluyen todas las filas de origen
- No hay asignaciones conflictivas para el mismo destino
- Se ha ejecutado el cálculo del modelo tras los cambios

## Consejos para optimizar el rendimiento

- **Utiliza relaciones entre datos:** limita el ámbito de asignación y mejora el rendimiento.
- **Reducir la granularidad de los identificadores:** un menor número de identificadores únicos se traduce en tablas de asignación más pequeñas.
- **Limitar las rutas de asignación:** cada asignación supone una sobrecarga de cálculo.
- **Revisar tablas grandes:** los objetos de modelo con más de 50 000 filas pueden necesitar optimización.

## ¿Qué viene ahora?

Una vez creadas las asignaciones:

- [Seguimiento de los flujos de costes a lo largo del modelo](trace-cost-flow.html) : aprende a realizar un seguimiento de los costes individuales a través de varios niveles.
- [Crear informes de modelos (diagramas de Sankey)](create-model-rep.html) : Crea visualizaciones de Sankey de tu modelo de costes.
- Comprender [la arquitectura del modelo](../../concepts-architecture/model-architecture/model-concepts-overview.html) : Profundiza en tus conocimientos sobre el funcionamiento de las asignaciones.

**Tema principal:** [Crear asignaciones](../../../../studio/new-uc/howtoguides/build-cost-model/create-allocation.html)
