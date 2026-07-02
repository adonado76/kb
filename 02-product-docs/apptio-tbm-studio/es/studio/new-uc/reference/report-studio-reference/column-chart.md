---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de columnas"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/column-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de columnas

Los gráficos de columnas muestran barras verticales y resultan especialmente útiles para mostrar cambios a lo largo del tiempo o comparar elementos cuando se trata de periodos de tiempo. Comparten las mismas opciones de configuración de datos que los gráficos de barras, pero presentan los datos en vertical.

**Gráfico de columnas verticales**

El gráfico de columnas estándar muestra los valores en forma de barras verticales. Esta es la opción más habitual para comparaciones de series temporales en las que el eje X representa periodos de tiempo como meses, trimestres o años.

**Cuándo utilizarlo: para** comparar valores entre distintos periodos, mostrar cambios de un periodo a otro o presentar datos cuyo orden de lectura natural sea de izquierda a derecha, siguiendo el orden cronológico.

**Gráfico de columnas apiladas**

Los gráficos de columnas apiladas dividen cada columna para mostrar la composición de los totales. Esto permite a los usuarios ver tanto la evolución de los valores totales como la contribución de los componentes de cada periodo a ese total.

**Cuándo utilizarlo: para** mostrar cómo varían los componentes de los costes a lo largo del tiempo, al tiempo que se muestra la tendencia general, como por ejemplo el gasto mensual en TI desglosado por infraestructura, aplicaciones y servicios.

**Creación de un gráfico de columnas**

1. En la pestaña Informe, haz clic en Gráfico. El gráfico se muestra por defecto en formato de barras horizontales.
2. En el panel «Configuración de componentes», selecciona un objeto de modelo en el menú desplegable.
3. Arrastra un campo de dimensión al área de la leyenda para definir las agrupaciones de barras.
4. Arrastra un campo métrico al área «Valores» para definir qué miden las columnas.
5. Arrastra un campo de tiempo (meses, trimestres, años) al área del eje.
6. Selecciona la pestaña «Ad Hoc» y haz clic en el icono de la columna para cambiar de barras horizontales a verticales.

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
