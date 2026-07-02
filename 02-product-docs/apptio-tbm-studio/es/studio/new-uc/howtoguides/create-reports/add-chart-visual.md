---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir gráficos y visualizaciones"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Conceptos básicos sobre los informes"
source_path: "studio/new-uc/howtoguides/create-reports/add-chart-visual.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir gráficos y visualizaciones

**Objetivo:** Añadir gráficos para visualizar patrones, tendencias y comparaciones de datos

**Cuándo utilizarlo:** cuando quieras comunicar información de forma rápida, mostrar tendencias a lo largo del tiempo, comparar categorías o resaltar proporciones

**Duración estimada:** 10-15 minutos

## Elegir el tipo de gráfico adecuado

Antes de añadir un gráfico, piensa en qué quieres contar:

|  |  |  |
| --- | --- | --- |
| **Tipo de gráfico** | **Ideal para** | **Ejemplo de caso de uso** |
| **Barra (horizontal)** | Comparación de categorías con nombres largos | Costes por nombre de la aplicación |
| **Columna (vertical)** | Comparación de categorías | Costes por unidad de negocio |
| **Tarta/Buñuelo** | Expresión de proporciones (partes de un todo) | Distribución presupuestaria entre departamentos |
| **Línea/Tendencia** | Mostrar la evolución a lo largo del tiempo | Evolución mensual de los costes |
| **Cascada** | Análisis de varianza | Variación interanual de los costes |

## Pautas para elegir los tipos de gráficos:

- **Utiliza gráficos de barras o de columnas** cuando compares elementos independientes (centros de datos, unidades de negocio, proveedores)
- **Utiliza gráficos de líneas** cuando tengas datos de series temporales y quieras mostrar tendencias
- **Utiliza los gráficos circulares con moderación** : funcionan mejor con entre 3 y 7 categorías y solo con valores positivos
- **Utiliza gráficos apilados** cuando necesites mostrar tanto los totales como los desgloses
- **Utiliza gráficos en cascada** para el análisis de variaciones o para mostrar el efecto acumulativo de valores secuenciales

## Pasos

1. Abre tu informe y **échale un vistazo**.
2. Haz clic en la pestaña **«Informe»** y, a continuación, haz clic en «**Gráfico** ». Aparece un gráfico de marcador de posición (por defecto, una barra horizontal) y se abre el panel «Configuración de componentes ad hoc».
3. Selecciona un **objeto de modelo** en el menú desplegable situado en la parte superior del panel de configuración.
4. Arrastra un campo de dimensión al área de **la leyenda**. Por ejemplo, arrastra «Centro de datos» para crear barras para cada centro de datos.
5. Arrastra una métrica al área «**Valores** ». Por ejemplo, arrastra «Coste» para calcular los costes.
6. (Opcional) Para los gráficos de tendencias, arrastra un campo de tiempo al área **de** los ejes.
7. Para cambiar el tipo de gráfico, haz clic en la pestaña **«Ad Hoc»** y selecciona un estilo de gráfico en la sección **«Visualizar»** (de barras, de columnas, de barras/columnas apiladas, circular o de líneas).

## Resultados previstos

- El gráfico muestra tus datos de forma visual
- Al pasar el cursor por encima de los elementos del gráfico, aparecen ventanas emergentes con los valores
- Al hacer clic en los elementos de la leyenda, se oculta o se muestra esa serie

## Errores habituales

- **Gráficos circulares con números negativos:** los gráficos circulares no pueden mostrar valores negativos. Si tus datos pueden contener valores negativos, utiliza mejor un gráfico de barras.
- **Demasiados elementos en la leyenda:** los gráficos con más de 7-10 series resultan difíciles de leer. Utiliza los filtros o cambia a la vista de tabla.
- **Faltan datos de la tendencia:** si el gráfico de tendencias no se ve bien, comprueba que el campo «Tiempo» se encuentre en el área «Ejes», y no en la «Leyenda».

**Tema principal:** [Conceptos básicos de los informes](../../../../studio/new-uc/howtoguides/create-reports/report-basic.html)
