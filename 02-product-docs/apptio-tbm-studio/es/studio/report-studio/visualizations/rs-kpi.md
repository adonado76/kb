---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "ICR"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Visualizaciones"
source_path: "studio/report-studio/visualizations/rs-kpi.html"
images:
  - "resources/images/studio_images/rs-kpi.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# ICR

El componente KPI (indicador clave de rendimiento) se utiliza para resaltar métricas importantes en un informe. Ayuda a los usuarios a comprender rápidamente las métricas clave de un vistazo

## Cuándo utilizar un KPI

Utilice un componente KPI cuando desee:

- Mostrar las métricas de forma destacada
- Destacar el rendimiento, los totales o los resultados clave
- Destacar los valores críticos en un informe

## Añadir un KPI al informe

1. Añadir un KPI desde el panel Visualizaciones de la barra de herramientas
2. Haga clic en el KPI para habilitar los paneles Datos y Formato.
3. Panel de datos
   1. Seleccione el objeto modelo en la lista desplegable
   2. Métrica principal: arrastre o añada una métrica principal
   3. Tipo de comparación: la métrica principal se puede comparar con lo siguiente:
      1. Ninguna – No hay comparación.
      2. Métrica de comparación: elija una métrica secundaria para compararla con la métrica principal
      3. Período anterior: elija comparar con el período anterior de la métrica principal
   4. Métrica de comparación: arrastre o añada una métrica secundaria para comparar
   5. Filtros: arrastre o añada los criterios de filtrado
4. Panel de formato
   1. Propiedades generales: consulte [Propiedades de los componentes.](../components/components.html#abt-comp__comprop)
   2. Propiedades específicas de los KPI
      1. Tendencia
         1. Elija el color para las tendencias positivas, negativas y neutras
         2. Elija el indicador que represente la tendencia (flecha y valor)
         3. Selecciona el tamaño del indicador de tendencia
      2. Métrica primaria/comparativa
         1. Edite las siguientes propiedades, según sea necesario para el nombre y el valor de la métrica primaria
         2. Tamaño y estilo de letra (negrita, cursiva, subrayado)
         3. Color del texto del título (con opción para restablecer el color)
      3. Notaciones abreviadas: acortar los valores de las métricas primarias y secundarias.

Ejemplo: Componente KPI

![Imagen del componente KPI](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/rs-kpi.png)

Nota: KPI admite fórmulas personalizadas y dimensiones de fórmulas. Para obtener más información, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas dimensiones de fórmula) le permiten definir nuevas dimensiones calculadas utilizando campos existentes en su modelo de datos. Esto permite realizar análisis más profundos y obtener información más detallada sin necesidad de realizar cambios en el conjunto de datos o el esquema subyacentes.")
