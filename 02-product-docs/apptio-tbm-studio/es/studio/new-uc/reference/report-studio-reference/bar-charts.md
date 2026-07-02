---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de barras"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/bar-charts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de barras

Los gráficos de barras muestran barras horizontales para comparar valores entre categorías. Son el tipo de gráfico predeterminado al añadir un nuevo gráfico a un informe y resultan ideales cuando las etiquetas de las categorías son largas o cuando se comparan muchos elementos.

**Gráfico de barras horizontales**

El gráfico de barras horizontal estándar muestra una sola serie de valores con barras que se extienden de izquierda a derecha. Cada barra representa el valor de una categoría, lo que facilita la comparación de magnitudes entre diferentes elementos, como centros de coste, aplicaciones o unidades de negocio.

**Cuándo utilizarlo: para** comparar valores entre categorías con etiquetas largas, clasificar elementos por valor o mostrar datos en los que el eje de categorías necesita más espacio que el eje de valores.

**Gráfico de barras horizontales apiladas**

Los gráficos de barras horizontales apiladas dividen cada barra en segmentos que representan diferentes series. Esto muestra tanto el valor total como la composición de dicho total. Utiliza esto cuando necesites mostrar cómo contribuyen los distintos componentes a una cifra global.

**Cuándo utilizarlo: Para** mostrar relaciones entre los costes parciales y los totales, sin perder la posibilidad de comparar los totales entre categorías, como por ejemplo, mostrar el desglose de los costes por tipo de gasto para cada departamento.

**Configuración de los datos del gráfico de barras**

|  |  |
| --- | --- |
| **Área de configuración** | **Descripción** |
| Leyenda | Arrastra los campos de dimensión para definir las categorías que se mostrarán como barras independientes o segmentos de barra (en el caso de los gráficos apilados). La leyenda determina cómo se agrupan los datos. |
| Valores | Arrastra los campos métricos para especificar los valores que representa la longitud de las barras. Las métricas múltiples generan barras agrupadas o segmentos apilados adicionales. |
| Eje | Arrastra los campos de dimensión o de tiempo para definir las etiquetas del eje Y (para barras horizontales). Los campos de tiempo permiten una presentación en forma de gráfico de tendencias. |
| Filtros | Arrastra los campos y configura los criterios de filtrado para limitar los datos que se muestran en el gráfico. |

**Propiedades específicas del gráfico de barras**

- Número máximo de filas: controla el número de barras que se muestran. Los elementos sobrantes se agrupan en una barra denominada «Otros».
- Gráficos de una sola serie con colores distintos: cuando esta opción está activada, cada barra de un gráfico de una sola serie se muestra en un color diferente.
- Orden inverso: invierte el orden de las barras en el eje.
- Ocultar eje X / Ocultar eje Y: Elimina las etiquetas de los ejes del gráfico.
- Ocultar líneas de cuadrícula: elimina las líneas de cuadrícula horizontales y verticales para lograr un aspecto más limpio.

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
