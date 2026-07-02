---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Reparto de costes -Telemetría y asignaciones basadas en el consumo"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
  - "Reparto de costes en Cloudability"
source_path: "product/cost-sharing-telemetry.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Reparto de costes -Telemetría y asignaciones basadas en el consumo

Descripción general

Las asignaciones basadas en telemetría le permiten distribuir los costes compartidos en su entorno de nube utilizando métricas de uso reales de sus sistemas. Al cargar los datos de telemetría, puede crear normas de asignación más precisas y basadas en datos dentro del reparto de costes.

Beneficios

El uso de datos telemétricos para la imputación de costes ofrece varias ventajas clave, como:

- Distribución de costes basada en el uso : Asigne costes basados en el uso real del sistema en lugar de porcentajes estáticos o métricas estimadas
- Mayor precisión en los costes : Crear una correlación directa entre el consumo de recursos y la distribución de costes
- Modelo de imputación defendible : Respalda la imputación de costes con datos de uso concretos, lo que facilita la justificación de los modelos de devolución de gastos
- Compatibilidad con métricas flexibles : utilice cualquier métrica medible (llamadas API, uso informático, operaciones de almacenamiento) para tomar decisiones de asignación

Antes de empezar

El archivo que se utiliza para cargar los datos de telemetría debe ser un archivo « CSV » que contenga los siguientes campos obligatorios:

- Fecha: La marca de tiempo para la medición métrica
- Categoría: Mapas a su categoría de dimensión empresarial
- Valor: La medida métrica (por ejemplo, number\_of\_api\_requests, compute\_hours)

El siguiente ejemplo muestra un archivo en formato « CSV ».

| Fecha | Categoría | Número de solicitudes API |
| --- | --- | --- |
| 01-01-2025 | Equipo A | 15000 |
| 01-01-2025 | Equipo B | 8500 |
| 01-01-2025 | Equipo C | 12000 |

Utilización de la telemetría en el reparto de costes

Siga los pasos que se indican a continuación para utilizar la telemetría y las asignaciones basadas en el consumo:

1. Seleccione Organizar/Compartir costes en el panel de navegación izquierdo
2. Seleccione el botón Nueva asignación
3. Seleccione una dimensión en el cuadro de diálogo modal Nueva asignación y, a continuación, seleccione el botón Crear
4. Seleccione la pestaña Datos de telemetría
5. Selecciona el botón «Subir archivo de telemetría» y sube el archivo « CSV »
6. El archivo « CSV » aparecerá en la tabla «Telemetría», en la pestaña «Datos de telemetría»
7. Seleccione la pestaña Reglas
8. Seleccione el botón Nueva regla
9. Seleccione Telemetría / Consumo en el desplegable Método de asignación
10. Seleccione al menos una opción en la lista Fuente (de)
11. Los valores de destino aparecen desactivados porque están definidos en el archivo « CSV » que se ha subido
12. Guardar la regla de asignación

El sistema calculará automáticamente los coeficientes de asignación basándose en sus datos de telemetría y los aplicará a sus costes compartidos.

Buenas prácticas

Siga las prácticas recomendadas en Telemetría que se indican a continuación:

- Asegúrese de que sus datos telemétricos cubren el mismo periodo de tiempo que sus periodos de imputación de costes.
- Compruebe que los valores del campo Categoría coinciden con las categorías de dimensión empresarial existentes.
- Las actualizaciones periódicas de los datos telemétricos proporcionarán la distribución de costes más precisa.
- Tenga en cuenta la estacionalidad y los patrones de uso a la hora de seleccionar las métricas adecuadas para la asignación.

**Tema para padres:** [Compartir costes en Cloudability](../product/cost-sharing.html)
