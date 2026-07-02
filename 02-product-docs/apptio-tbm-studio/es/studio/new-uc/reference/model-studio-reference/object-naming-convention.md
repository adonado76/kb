---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Convenciones de nomenclatura de objetos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Objetos modelo"
source_path: "studio/new-uc/reference/model-studio-reference/object-naming-convention.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Convenciones de nomenclatura de objetos

Una nomenclatura coherente mejora la facilidad de mantenimiento del modelo y la comprensión por parte del usuario.

**Patrones de nomenclatura recomendados**

|  |  |  |
| --- | --- | --- |
| **Patrón** | **Formato** | **Ejemplo** |
| Fuentes de los costes | [Tipo] [Período/Calificador] | Datos reales de la fuente de costes, presupuesto de la fuente de costes |
| Grupos de costes | [Categoría] [Calificador] | Datos reales de mano de obra, datos reales de instalaciones, activos fijos |
| Infraestructura | [Tipo de recurso] | Servidores, almacenamiento, redes, centros de datos |
| Servicios | [Categoría de servicio] | Servicios tecnológicos, aplicaciones empresariales |
| Consumidores | [Tipo de consumidor] | Unidades de negocio, departamentos, clientes |

**Buenas prácticas en la elección de nombres**

- Utiliza nombres descriptivos que indiquen la función del objeto en el modelo
- Incluye el calificativo «Valores reales», «Presupuesto» o «Previsión» cuando los objetos sean específicos de una métrica
- Evita los caracteres especiales que puedan causar problemas en las fórmulas o los informes
- Los nombres deben ser concisos, pero sin perder su significado
- Indique el propósito del documento en el campo «Descripción»

**Nota:** Los nombres de los objetos aparecen en los informes del modelo y son visibles para los usuarios finales. Elige nombres que tengan sentido para tus partes interesadas.

**Problemas habituales**

|  |  |  |
| --- | --- | --- |
| **Emitir** | **Causa** | **Resolución** |
| El objeto del modelo no es visible | El paso del modelo no se ha añadido a la tabla | Añadir el paso «Modelo» a la transformación de la tabla |
| No se puede crear la asignación | Mesas sin reservar | Comprueba tanto el texto de origen como el de destino |
| No hay datos en el objeto del modelo | Errores de transformación o falta de puntos | Comprueba que la transformación de « Data Studio » se haya realizado correctamente |
| Valores de identificador duplicados | Configuración de identificadores no únicos | Añadir columnas al identificador para garantizar la unicidad |

*→ Consulte [la sección «Problemas habituales» para obtener información detallada sobre la resolución de problemas](../../ts-support/ds-issues.html)*

**Tema principal:** [Objetos modelo](../../../../studio/new-uc/reference/model-studio-reference/model-objects.html)
