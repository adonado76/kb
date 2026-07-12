---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Buenas prácticas: Previsión"
breadcrumb: []
source_path: "it-planning/planning/bp-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Buenas prácticas: Previsión

En una previsión, los meses históricos se sustituyen por los reales para ofrecer una visión única e híbrida de los resultados hasta la fecha y una perspectiva para el resto del año. Este documento abarca las mejores prácticas para la elaboración de previsiones, incluidos ejemplos y tareas específicas para crear previsiones.

Para obtener más información sobre el amplio flujo de trabajo de previsión en las aplicaciones de Apptio Planning , consulte [Planificación y previsión presupuestarias](budget-planning-forecasting.html).

## Ejemplo: Crear la primera previsión de 2018

En este ejemplo, asumimos una cadencia de previsión trimestral y un ejercicio fiscal alineado con el año natural.

Previamente, se creó un presupuesto definitivo denominado FY2018 Budget para FY18. Ya estamos en abril de 2018, así que es hora de crear la primera previsión trimestral de FY2018. Esta será la previsión Q2.Este ejemplo incluye las siguientes tareas:

- [Tarea 1: Validar los datos reales](#best_practices_forecasting__Validate-actuals)
- [Tarea 2 (opcional): Actualizar los objetivos del presupuesto base](#best_practices_forecasting__Update-baseline-budget)
- [Tarea 3: Crear un plan de previsiones](#best_practices_forecasting__forecast-plan)
- [Tarea 4: Habilitar las características del plan para la previsión](#best_practices_forecasting__features-4-forecast)
- [Tarea 5 (opcional): Actualizar la mano de obra, los contratos y los activos](#best_practices_forecasting__labor-contracts-assets)
- [Tarea 6: Permitir que los propietarios del presupuesto realicen actualizaciones](#best_practices_forecasting__budget-owners-updates)

## Tarea 1: Validar los datos reales

En Gestión de gastos, asegúrese de que los reales se cargan correctamente en enero de 2018, febrero de 2018 y marzo de 2018. Para más información, véase [Importar y publicar datos reales](import-publish-actuals.html).

## Tarea 2 (opcional): Actualizar los objetivos del presupuesto base

Los objetivos proporcionan la capacidad de almacenar un objetivo de fin de año OpEx, CapEx, y Headcount para cada Departamento. Los indicadores clave de rendimiento (KPI) y los gráficos de toda la aplicación permiten realizar cómodas comparaciones con los objetivos. Dado que los objetivos se copian en los nuevos planes, el almacenamiento de los importes presupuestarios aprobados como objetivos en el presupuesto base proporciona una forma sencilla de trasladarlos a los futuros planes de previsión. Véase [Fijar objetivos financieros](set-financial-targets.html).

## Tarea 3: Crear un plan de previsiones

Al crear una previsión, tenga en cuenta lo siguiente y consulte también [Crear un plan o una previsión](create-budget-plan.html) :

1. `Forecast Start Period` - Especifica el primer mes de la previsión que no contiene datos reales. Dado que la previsión Q2 tiene datos reales de enero, febrero y marzo, en este caso, fije el periodo de inicio de la previsión en abril.
2. `Baseline` - Especifica de qué plan se copiarán los datos del plan. Todos los datos (por ejemplo, Contratos, Activos, Mano de obra, Objetivos, Otros gastos, etc.), excepto los importes financieros de los meses reales, se copiarán del plan especificado en el nuevo plan. Dado que se trata de la primera previsión de FY2018, utilice el presupuesto de FY2018 como base de referencia.
3. `Summarize actuals down to the following dimensions and/or attributes` - Sólo las columnas marcadas se transferirán de la Gestión de gastos a la nueva previsión. Se recomienda comprobar la mayoría o todos estos valores para maximizar la granularidad de los datos reales en la nueva previsión. El siguiente ejemplo muestra cómo la selección de varias opciones para resumir afecta a la granularidad de los datos reales en la nueva previsión:
4. `Rolling forecasts` - Si se ha utilizado una previsión renovable, crear un plan a dos o tres años para garantizar que la previsión contiene de 4 a 6 trimestres futuros.
5. `Reference data usage` - La nueva previsión utilizará la última versión publicada de todas las dimensiones de los datos de referencia, por lo que:
   - Los datos reales introducidos en la previsión utilizarán los datos de referencia más recientes, independientemente de la versión utilizada en la Gestión de gastos.
   - Los datos del plan introducidos en la previsión a partir del plan base utilizarán los datos de referencia más recientes, independientemente de la versión del plan base.

## Tarea 4: Habilitar las características del plan para la previsión

Configure los controladores de desviación en la previsión con las siguientes opciones:

- `Compare Plan` - El presupuesto original, FY2018 Budget
- `Comparison Period` - Como se trata de la primera previsión del año, elija Q1 FY18

Cuando edite partidas, utilice la función Comparar accesos directos para añadir una comparación a FY2018 Presupuesto para que los usuarios puedan ver una comparación con el presupuesto original.

## Tarea 5 (opcional): Actualizar la mano de obra, los contratos y los activos

Podría ser más eficaz realizar algunas actualizaciones de las previsiones generales antes de abrir el plan a todos los propietarios del presupuesto.

1. Actualizaciones laborales
   - `Updates for new hires:`
     1. Añada las nuevas contrataciones a la pestaña Gastos > Mano de obra > Existentes.
     2. Elimine el recuento abierto lleno de la pestaña Gastos > Mano de obra > Planificado.
   - `Updates for delayed hires` - Actualice la fecha de inicio del recuento abierto en la pestaña Gastos > Mano de obra > Planificado.
   - `Updates for canceled hiring` - Actualice a 0 la cantidad de personal pendiente en la pestaña Gastos > Mano de obra > Planificado.
   - `Updates for employee departures` - Actualice la Fecha de finalización del empleado a la fecha de finalización en la pestaña Gastos > Mano de obra > Existente.
2. Actualización de activos
   - `Updates for new purchases:`
     1. Añada la compra real a la pestaña Gastos > Activos > Existentes.
     2. Elimine la compra planificada de la pestaña Gastos > Activos > Planificados.
   - `Updates for delayed purchases:`
     1. Actualice la Fecha de compra prevista (y la Fecha de puesta en servicio, si procede) con la fecha futura en la pestaña Gastos > Activos > Existentes.
   - `Updates for canceled purchases` - Actualice la compra planificada `Quantity` a 0 en la pestaña Gastos > Activos > Existentes.
3. Actualización de contratos
   - `Updates for delayed contracts:`
     1. Si la fecha de inicio del contrato se ha retrasado, actualice la Fecha de inicio prevista del contrato en la pestaña Gastos > Contratos.
     2. Si el contrato se inició a tiempo, pero la amortización/facturación se retrasó, actualice la Compensación de inicio de amortización del contrato existente en la pestaña Gastos > Contratos.
   - `Updates for canceled contracts` - Actualice el Importe previsto del contrato a 0 en la pestaña Gastos > Contratos.

Los propietarios del presupuesto también pueden realizar cualquiera de estas actualizaciones cuando se abre el plan.

## Tarea 6: Permitir que los propietarios del presupuesto realicen actualizaciones

Una vez abierta la previsión, los propietarios del presupuesto pueden realizar actualizaciones en los períodos futuros del plan, pero no en los períodos reales, que son de sólo lectura.

Utilice la función Comparar con el presupuesto original de FY19 para garantizar la alineación con el presupuesto de cada departamento, cuenta o grupo de costes, etc., al revisar y aprobar los cambios de los usuarios.

Nota: La función Comparar número de empleados actualmente está disponible solo en la página Resumen, pestaña Número de empleados.

## Crear previsiones posteriores para el año

Finalmente, llegará el momento de crear la segunda gran previsión trimestral del año. Se cargarán los datos reales de abril, mayo y junio, lo que permitirá crear la previsión Q3.

Las tareas son las mismas que con la primera previsión de año anterior, salvo la elección del plan base.

Para asegurarse de que incluye las actualizaciones realizadas en la Previsión Q2, utilice la Previsión Q2 como base de referencia para la Previsión Q3. Esto significa que todos los datos (excepto los importes financieros reales, que se cargan desde la Gestión de gastos ) se copiarán de la Previsión Q2 a la nueva Previsión Q3.

## Estrategias de análisis de desviaciones presupuestarias

Existen dos enfoques comunes (y varias variaciones) para realizar análisis de desviaciones en las previsiones a lo largo del año.

1. Análisis de la desviación con respecto a la previsión anterior
   - `Compare plan` - Q2 Pronóstico.
   - `Compare period` - Q2 ya que esos nuevos datos reales se comparan con las actualizaciones de las previsiones realizadas en Q2 Forecast.
   - `Evaluate year-end totals vs. the baseline budget` - Especifique un acceso directo de comparación del presupuesto FY2018.
2. Análisis de la desviación con respecto al presupuesto inicial
   - `Compare plan` - FY2018 Presupuesto.
   - `Compare period` - YTD ( Q1-Q2 ) porque el efecto acumulativo de todos los reales se está comparando con el presupuesto original.
   - `Evaluate year-end totals vs. the baseline budget` - Especifique un acceso directo de comparación del presupuesto FY2018.

## Revisiones mensuales

Muchas organizaciones realizan previsiones con una frecuencia mensual. Las organizaciones que realizan previsiones con una frecuencia trimestral pueden beneficiarse de una revisión mensual en cuanto estén disponibles los datos reales. Para ello, siga los pasos anteriores de creación de previsiones, omitiendo las tareas que considere oportunas y, a continuación, no abra el plan.
