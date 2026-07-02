---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Supervisar los indicadores clave de rendimiento en el cuadro de mandos"
breadcrumb: []
source_path: "it-planning/planning/monitor-key-performance.html"
images:
  - "resources/planning_images/itp_annual-vendor-spend.png"
  - "resources/planning_images/itp_executive-dashboard_elements.png"
  - "resources/planning_images/itp_it-spend-trend_chart.png"
  - "resources/planning_images/itp_it-spend-variance.png"
  - "resources/planning_images/itp_it-trend-spend_department-name.png"
  - "resources/planning_images/itp_uncommitted-spend.png"
  - "resources/planning_images/itp_uncommitted-spend_donut-detail.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Supervisar los indicadores clave de rendimiento en el cuadro de mandos

El cuadro de mandos ofrece una visión rápida pero completa de los principales indicadores de rendimiento del plan. En concreto, el cuadro de mandos muestra los resultados reales comparados con el presupuesto, y las previsiones actuales comparadas con el presupuesto del año y del año hasta la fecha. Esta visión consolidada resume los elementos clave y el estado actual de la planificación.

Nota: El panel de control debe estar visible en la interfaz. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning."). Una vez hecho esto, todos los usuarios podrán acceder al panel de control. El contenido del Cuadro de mandos es limitado. Sin embargo, se basa en los permisos de rol del usuario.

El contenido del panel de control se rellena con el plan seleccionado. Las comparaciones, cuando están disponibles, son contra el plan seleccionado Comparar con:.

## Abrir el cuadro de mandos

1. En los menús de plan de la parte superior derecha, seleccione un plan, una categoría de objeto de coste y un objeto de coste o grupo de objetos de coste.

   [Más información sobre la navegación en Planificación](navigate-apptio-planning.html)
2. Vaya a Planning > Panel de control.

## Elementos del cuadro de mandos

Indicadores clave de rendimiento (KPI ): los tres KPI siguientes aparecen en la parte superior del panel de control. Sólo se incluyen los valores de tipo de transacción directa. La desviación se calcula con respecto a un objetivo, si se ha fijado. Véase [Fijar objetivos financieros](set-financial-targets.html). Los indicadores clave de rendimiento son los siguientes

- OpEx Total para el año del plan
- CapEx Total para el año del plan
- Plantilla media para el año del plan

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_executive-dashboard_elements.png)

Tendencia del gasto en TI: gráficos del plan seleccionado y los datos reales disponibles del año en curso comparados con el plan de comparación seleccionado. Utilice el filtro rápido para alternar entre los valores Todos, OpEx, y CapEx.

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_it-spend-trend_chart.png)

SUGERENCIA : Haga clic en una barra para ver los detalles de la partida. Los KPI pueden mostrarse por meses, trimestres y años, y descargarse.

Desviación de gastos de TI - Gráficos de los factores de desviación descubiertos por los propietarios de centros de coste e identificados como parte del análisis de desviaciones. El resumen por impulsor de desviación se realiza en cascada desde el presupuesto original hasta los datos reales. Se puede desglosar utilizando el control de árbol, de forma similar a otros gráficos de planificación. Utilice el botón Descargar para exportar un archivo.csv con toda la información capturada sobre el conductor de varianza, incluidas las entradas de texto libre.

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_it-spend-variance.png)

Plan anual de mano de obra - Gráfica de los efectivos de mano de obra identificados en el plan seleccionado frente a una línea de tendencia del plan Comparar con:. Puede agrupar o pivotar los datos por múltiples dimensiones, como Centro de coste > Código, o Departamento > Código.

Consejo: Puede hacer clic en una barra para ver los detalles de la partida y descargar los datos.

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_it-trend-spend_department-name.png)

Gastos no comprometidos - Muestra el ahorro potencial en períodos futuros por categoría de gastos en gráficos de donut. El cálculo se basa en la fecha de entrada por defecto Commit After:

- Para un plan de previsiones, la fecha de entrada es el primer día del mes de inicio de las previsiones si ese día se encuentra en el primer año del plan. De lo contrario, se trata como un plan presupuestario.
- Para un plan presupuestario, la fecha de hoy si se trata del primer año del plan. En caso contrario, el primer día del primer año del plan.

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_uncommitted-spend.png)

Los cálculos para cada valor de la tabla de donativos son los siguientes: los valores de Fecha de inicio para cada elemento de la siguiente lista se encuentran en la pestaña correspondiente de la página Gastos.

Por ejemplo, la Fecha de Inicio de la Partida de Mano de Obra se encuentra en la vista de Gastos, pestaña Mano de Obra. Si la Experiencia de Planificación Laboral Racionalizada está activada en el Perfil de la Empresa, los valores se pueden encontrar en la página de Gastos, pestaña Actividades. Véase [Editar el perfil de la empresa](edit-company-profile.html "El Perfil de Empresa permite a los usuarios Administradores y Propietarios de Procesos Presupuestarios configurar los parámetros de la aplicación para personalizar la visualización, activar o desactivar funciones y definir el comportamiento del flujo de trabajo en Apptio Planning.").

- Gastos de mano de obra no comprometidos - Suma de las partidas financieras en las que la fecha de inicio de la partida de mano de obra es mayor o igual que la fecha de entrada.
- Gastos de contratos no comprometidos - Suma de las partidas financieras en las que la fecha de inicio de la partida contractual es mayor o igual que la fecha de entrada. Tenga en cuenta que actualmente se excluye la gestión sofisticada de las prórrogas de contratos y que los contratos que se prorrogan más allá de su fecha de finalización indicada se consideran comprometidos.
- Gastos de activos no comprometidos - Suma de las partidas financieras en las que la fecha de compra de la partida de activos es mayor o igual que la fecha de entrada.

Haga clic en un valor de rebanada de donut para visualizar una tabla detallada de partidas asociada a ese valor. Estos detalles le permiten identificar oportunidades específicas de ahorro de costes dentro de su plan.

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_uncommitted-spend_donut-detail.png)

Gastos anuales de proveedor - Muestra los gastos de proveedor planificados (donde el valor de proveedor no es nulo), comparando el plan seleccionado con el plan Comparar con:. Seleccionado Grupo Por se muestra en cascada en el gráfico Cascada de comparar a seleccionado.

![imagen](../../../../../03-media/apptio-planning/resources/planning_images/itp_annual-vendor-spend.png)
