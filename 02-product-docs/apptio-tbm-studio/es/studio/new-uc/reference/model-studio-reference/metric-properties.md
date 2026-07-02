---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Propiedades métricas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia del estudio de modelos"
  - "Métricas de modelo"
source_path: "studio/new-uc/reference/model-studio-reference/metric-properties.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Propiedades métricas

Cada métrica tiene propiedades configurables que controlan su comportamiento. Las propiedades marcadas con (\*) se aplican únicamente a las métricas calculadas.

**Referencia completa de la propiedad**

|  |  |  |
| --- | --- | --- |
| **Propiedad** | **Valores** | **Descripción** |
| Vista predeterminada | Nombre del informe | Informe que se muestra al hacer clic en el enlace de métricas |
| Tipo de modelo | Modelo, calculado | Si el valor métrico se aplica mediante asignaciones (Modelo) o se calcula mediante una fórmula (Calculado) |
| Tipo de métrica | Cálculo de costes, fijación de precios, datos numéricos | Cálculo de costes = monetario; Fijación de precios = precio × cantidad; Numérico = otros |
| Oculto | Booleano | Oculta la métrica en las tablas de unidades del objeto modelo |
| Formato de tabla | Fórmula | Formato de visualización en tablas (por ejemplo, =Currency($\_)) |
| Formato del gráfico | Patrón | Formato numérico en el eje del gráfico (p. ej., $#,###) |
| Prefijo de tabla | Texto | Prefijo añadido a la medida en los gráficos (p. ej., $) |
| Sufijo de tabla | Texto | Sufijo añadido a la medida en los gráficos |
| Comportamiento temporal | Suma, media, volver a calcular | Cómo se acumulan los datos de las métricas a lo largo de los periodos |
| Cálculo del valor\* | Fórmula | Fórmula que define el valor de la métrica calculada |
| ¿Se puede sumar\* | Booleano | Si los valores se pueden sumar o recalcular |
| Incluir en modelos virtuales\* | Booleano | Incluir en modelos filtrados y recursivos |
| Ignorar para filtrado interno\* | Booleano | Excluir de la evaluación del filtrado de filas con valor cero |
| Intervalo de tiempo\* | Ninguno, Trimestral, Anual | Obtener el valor del primer periodo del intervalo |

**Opciones de comportamiento temporal**

|  |  |
| --- | --- |
| **Opción** | **Comportamiento** |
| Suma | Calcula cada período por separado y, a continuación, suma los períodos. Úsalo para métricas aditivas como el coste. |
| Promedio | Calcula cada periodo, suma los resultados y divide el total entre el número de periodos. Utilizar para métricas de tasas. |
| Volver a calcular | Calcula los valores agregados en todas las columnas y, a continuación, vuelve a ejecutar la fórmula. Úsalo para calcular ratios. |

**Tema principal:** [Métricas del modelo](../../../../studio/new-uc/reference/model-studio-reference/model-metrics.html)
