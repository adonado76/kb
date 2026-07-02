---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de tendencias"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/trend-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de tendencias

Los gráficos de tendencias son gráficos de líneas especializados, diseñados específicamente para mostrar la evolución de los valores a lo largo del tiempo. Incluyen compatibilidad integrada con intervalos de tiempo y pueden incorporar proyecciones estadísticas para pronosticar valores futuros.

**Creación de un gráfico de tendencias**

1. En la pestaña Informe, haz clic en Gráfico.
2. En el panel «Configuración de componentes», arrastra los campos a las áreas correspondientes.
3. Arrastra un campo de tiempo (meses, trimestres, años) al área del eje. Esto es lo que convierte el gráfico en un gráfico de tendencias.
4. Haz clic con el botón derecho del ratón en el campo de tiempo del área «Eje» para configurar el intervalo de tiempo.

**Opciones de intervalo de tiempo**

Al hacer clic con el botón derecho del ratón en un campo de tiempo en el área «Eje», puedes elegir entre estos intervalos predefinidos:

- Este trimestre: muestra los tres meses del trimestre fiscal actual.
- Este semestre: muestra los seis meses del semestre fiscal actual.
- Este año: muestra los 12 meses del ejercicio fiscal actual.
- Rango: abre un cuadro de diálogo en el que puedes establecer meses personalizados hacia atrás y hacia adelante a partir del periodo actual.

**Fijar el periodo de tiempo**

Por defecto, los gráficos de tendencias muestran datos relativos al periodo de tiempo seleccionado actualmente. Para fijar el gráfico a un intervalo de tiempo concreto, independientemente de la selección de fecha del informe, utilice el campo «Intervalo de tiempo de los datos» en la pestaña «Avanzadas» del cuadro de diálogo «Propiedades». Por ejemplo, configura el «Periodo de fecha y hora» en «Inicio del ejercicio fiscal actual» para que siempre se muestre el ejercicio fiscal completo.

**Añadir proyecciones**

Los gráficos de tendencias pueden incluir proyecciones que estiman valores futuros a partir de datos históricos. TBM Studio ofrece varios algoritmos de regresión múltiple:

|  |  |
| --- | --- |
| **Algoritmo** | **Descripción** |
| Regresión | Regresión lineal estándar para líneas de tendencia simples. |
| Regresión lineal múltiple | Regresión con varias variables independientes. |
| Regresión polinómica | Ajusta una curva polinómica para reflejar las tendencias no lineales. |
| Suavizado exponencial simple | Suaviza los datos para reducir el ruido y resaltar las tendencias. |
| Suavizado exponencial doble | Tiene en cuenta tanto el nivel como la tendencia de los datos. |
| Media móvil | Calcula promedios en intervalos de tiempo móviles. |

Nota: Para añadir una proyección a un gráfico de tendencias heredado, haz clic con el botón derecho del ratón en el gráfico y selecciona «Proyectar tendencia» en el menú emergente.

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
