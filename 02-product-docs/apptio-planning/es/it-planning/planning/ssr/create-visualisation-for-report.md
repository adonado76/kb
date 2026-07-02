---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Crear una visualización para un informe"
breadcrumb: []
source_path: "it-planning/planning/ssr/create-visualisation-for-report.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Crear una visualización para un informe

Complete los siguientes pasos para crear una visualización en Apptio BI utilizando datos de Planning. Puede personalizar la visualización de varias formas, como seleccionar el tipo de visualización (gráfico de barras, gráfico de líneas, etc.), filtrar los datos y seleccionar un periodo de tiempo.

Para más información, consulte [Crear informes personalizados](../../../apptio_bi/self-service-reporting_user_guide/create-a-self-service-report.html).

## Procedimiento

1. En Enhanced Access Administration, abra Apptio BI.

   Si es la primera vez que abre Apptio BI, verá una pantalla de introducción

   ![Apptio pantalla de introducción](../../../resources/images/it%20planning_images/pastedimage_22.png)
2. Seleccione Crear nuevo informe.
3. Seleccione Añadir visualización en la esquina superior derecha.

   Se abre la página Añadir visualización.
4. En la sección Fuentes de datos y medidas, seleccione una fuente de datos para la visualización.

   Las siguientes fuentes de datos son exclusivas de ITP y corresponden a diferentes fichas de gastos.

   Para ver los datos de la pestaña Otros gastos, seleccione la fuente de datos Planning Financial y filtre por la dimensión "Tipo de partida" igual al valor "Otros".

   | Origen de datos | Pestaña de gastos ITP asociados | Subpestaña de gastos ITP asociados |
   | --- | --- | --- |
   | Planificación de activos | Activos | Existente, previsto |
   | Planificación Resumen financiero | Todos | Planning |
   | Contrato de planificación | Contratos | Planificación Resumen financiero |
   | Planificación del trabajo | Trabajo | Existente, previsto |
   | Actividad laboral | Trabajo | Existente, previsto |
5. En la sección Nombre del plan, seleccione el plan que desea utilizar para su visualización.

   Se enumeran todos los planes activos en Planning . Los planes archivados o eliminados no aparecerán.
6. Seleccione las dimensiones y métricas que desea utilizar.

   Para más información, [consulte](it-planning-data-self-service-reporting.html "Apptio BI permite a los usuarios crear y compartir sus propios informes personalizados utilizando datos de diversas aplicaciones, incluida Planificación. Con los datos de Planificación disponibles en Apptio BI, los usuarios pueden ahora crear un informe personalizado que resuma los datos de mano de obra, activos, contratos y financieros del departamento de Planificación.")
7. Seleccione un tipo de visualización.
8. Seleccione un intervalo de fechas.

   Se puede mostrar el plan de hasta 1 año a la vez. Planning incluyen las siguientes opciones, además de las opciones estándar de Apptio BI :
   - Año siguiente
   - # Años en el futuro, donde # es el número de años en el futuro para un plan con varios años, hasta un máximo de 7 años. Por ejemplo, si el año actual es 2020 y el plan comienza en 2020 y dura 7 años, entonces el intervalo de fechas incluiría "2 Años Futuros" para mostrar 2022’s plan, "3 Años Futuros" para mostrar 2023’s plan,.... "7 años en el futuro" para mostrar el plan 2027’s.
   - Nota: En la fuente de datos ITP Labor, sólo se admiten las opciones Este mes y Último mes para los siguientes tipos de visualización: KPI, Barra, Tarta.
9. En Ver por, seleccione un marco temporal.

   En la fuente de datos ITP Labor, sólo se admite la opción Vista mensual por.
10. Opcional: Seleccione un filtro.

    En la fuente de datos Planning Labor, puede utilizar la dimensión "Is Existing Resource" para filtrar y ver sólo los datos de la subpestaña de mano de obra existente (=true) vs planificada (=false).
11. Opcional: Edite el nombre de la visualización.

    Como práctica recomendada, añada la fuente de datos como prefijo al nombre de la visualización.
12. Cuando haya terminado, haga clic en Guardar informe.

    Después de guardar la visualización, verá el informe que contiene la visualización. Añada visualizaciones adicionales según sea necesario. También puede compartir el informe con otros miembros de su organización. Para obtener información sobre cómo compartir, consulte [Gestionar informes](../../../apptio_bi/self-service-reporting_user_guide/manage-self-service-reports.html).

    Nota:

    La opción Comparar con no está disponible actualmente.

    Para mostrar cada partida en Apptio BI tal y como aparece en Planning, añada una columna con un valor único a la visualización (por ejemplo: el nombre del empleado en la fuente de datos Labor).

    El importe de la mano de obra no está disponible a través de la fuente de datos de mano de obra Planning . Para ver el importe de mano de obra, seleccione Planning Financials como fuente de datos y, a continuación, filtre por el valor de Tipo de partida de Mano de obra.

## Ejemplo

La siguiente información es un ejemplo de configuración utilizada para crear una visualización de tabla utilizando Planning Financials como fuente de datos. Tenga en cuenta que las opciones necesarias cambian en función del tipo de visualización.![Ejemplo de configuración utilizada para crear una visualización de tabla utilizando Planning Financials como fuente de datos](../../../resources/images/it%20planning_images/pastedimage_1.png)
