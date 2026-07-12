---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Analizar un plan"
breadcrumb:
  - "Planning"
  - "Análisis e informes"
source_path: "it-planning/planning/analyze-plan-forecast.html"
images:
  - "resources/images/it_planning_images/filters.png"
  - "resources/images/it_planning_images/spnd-trnd.png"
  - "resources/images/it_planning_images/spnd-wf.png"
  - "resources/images/it_planning_images/tree-map.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Analizar un plan

La página Resumen proporciona visualizaciones interactivas de su plan, mostrando los gastos directos e indirectos y, si están activados, los gastos laborales del proyecto vinculados a los datos de plantilla. Utilice esta página para explorar el rendimiento financiero, identificar tendencias y descubrir desviaciones.

## Abrir la página de resumen

1. Seleccione un **plan** en el menú de planes
2. Navegue hasta **Planificación** **→ Resumen**
3. Elija la vista adecuada:
   1. Ficha **financiera** : para ver resúmenes financieros
   2. Pestaña **Headcount** - para ver los resúmenes de mano de obra y ETC

## Filtrar y configurar la vista

Utilice los desplegables **Departamento**, **Proyecto** e **Intervalo de fechas** para controlar el alcance de lo que se muestra.

Puede afinar aún más la vista utilizando las siguientes opciones:

1. **Agrupar por** - Pivote los análisis por una dimensión o atributo específico (por ejemplo, Departamento, Categoría de cuenta, Proveedor).
2. **Comparar con** - Seleccione **Objetivos**, **Reales** u otro **Plan** para permitir comparaciones de desviaciones en los gráficos Desglose de gastos (mapa de árbol) y Cascada de gastos. Comparar con objetivos sólo está disponible cuando la opción Agrupar por está configurada como Código de departamento o Nombre de departamento.
3. **Filtros** - Aplique filtros adicionales para acotar los datos analizados.
4. **Todos / OpEx / CapEx** - Filtre los resultados por tipo de gasto.
5. **Disposición** - Cambia la disposición de los gráficos para adaptarla a tu vista de análisis preferida.

Nota: Los filtros afectan a los gráficos y tablas, pero no ajustan los KPI.

![imagen de filtros](../../../../../03-media/apptio-planning/resources/images/it_planning_images/filters.png)

## Comprender los elementos visuales clave

*Desglose de gastos - Gráfico de árbol*

Muestra la representación proporcional de los gastos por la dimensión seleccionada **Agrupar por**.

- Los bloques están codificados por colores según el estado de la varianza (por debajo del objetivo = azul, por encima del objetivo = naranja).
- Haga clic en un bloque para cargar información más detallada en el gráfico Tendencia del gasto.
- Haga clic en **Voltear comparación** (icono de flecha) para invertir la dirección de la variación.

![imagen del organigrama de gastos](../../../../../03-media/apptio-planning/resources/images/it_planning_images/tree-map.png)

*Gráfico de tendencia del gasto*

Muestra las tendencias a lo largo del tiempo para el grupo seleccionado o el plan general.

- Utilice el **selector de dimensión** para desglosar aún más los gastos del período seleccionado por otra dimensión.
- Utilice el **selector de periodos de tiempo** para cambiar entre puntos de análisis (Meses, Trimestres, Años).
- Incluye una superposición de los datos reales si se han importado y están disponibles (sólo vista de meses).
- Haga clic en el **botón de descarga** para exportar los detalles del gráfico a csv.

![imagen del gráfico de tendencias de gastos](../../../../../03-media/apptio-planning/resources/images/it_planning_images/spnd-trnd.png)

*Gráfico de cascada de gastos*

Si ha seleccionado un plan de comparación, un objetivo o datos reales, la cascada muestra las "ventajas y desventajas" de la variación.

- La barra de la izquierda es su plan actual; la de la derecha es el comparador (plan, objetivo, real).
- Las barras están codificadas por colores según el estado de la varianza (por debajo del objetivo = azul, por encima del objetivo = naranja).
- Haga clic en **Voltear comparación** (icono de flecha) para invertir la dirección de la variación.
- Haga clic en el **botón de descarga** para exportar los detalles del gráfico a csv.

![imagen del gráfico de gastos en cascada](../../../../../03-media/apptio-planning/resources/images/it_planning_images/spnd-wf.png)
