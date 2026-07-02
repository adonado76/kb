---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Fijo /var iable informes y asignaciones"
breadcrumb: []
source_path: "cost-transparency/reports-v103/fixedvariablereportingallocations-6558.html"
images:
  - "resources/images/ct_images/6558_10.png"
  - "resources/images/ct_images/6558_11.png"
  - "resources/images/ct_images/6558_2.png"
  - "resources/images/ct_images/6558_3.png"
  - "resources/images/ct_images/6558_4.png"
  - "resources/images/ct_images/6558_5.png"
  - "resources/images/ct_images/6558_6.png"
  - "resources/images/ct_images/6558_7.png"
  - "resources/images/ct_images/6558_8.png"
  - "resources/images/ct_images/6558_9.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Fijo /var iable informes y asignaciones

Se aplica a : v12+

## Visión general

Intentar averiguar a qué se deben sus costes fijos o variables:

- ¿no parece correcto?
- ¿Demasiado bajo?

¿Te estás haciendo alguna de estas preguntas?

- ¿Cómo se calculan los costes fijos y variables?
- ¿Cómo puedo conseguir dólares en los modelos Fijo o Variable?
- ¿Cómo me aseguro de que los costes Fijos y Variables fluyen a través de sus modelos?
- ¿Cómo puedo influir directamente en el importe que aparece en el informe Fijo/Variable?

Este tema le mostrará cómo se configuran los costes Fijos y Variables en Costing Standard y dónde puede buscar para editar estos costes.

## ¿Cómo se crean los costes fijos y variables?

Los costes Fijos y Variables se crean a partir de los modelos Fijo y Variable, que se ejecutan en paralelo al modelo de Costes.

Modelo fijo
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_2.png)

Modelo variable
:   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_3.png)

## ¿Cómo puedo conseguir dólares en los modelos fijo y variable?

Para asegurarse de que hay valores rellenados tanto en el modelo Fijo como en el Variable, siga estos pasos.

1. Haga clic en la tabla **Fuente de costes**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_4.png)
2. Seleccione la métrica **Fija** o **Variable** en el menú desplegable.

   Desplegable fijo
   :   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_5.png)

   Variable desplegable
   :   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_6.png)
3. Haga clic en el controlador **OpEx Fixed**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_7.png)
4. Haga clic en el menú desplegable **Añadir a**.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_8.png)
5. Asegúrese de que el botón **Fijo** está seleccionado.

   ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_9.png)

Siga los pasos anteriores para comprobar los modelos Fijo y Variable si está ejecutando Coste a través de Apptio. Además, debería comprobar los modelos Fijo y Variable para cada métrica de informe adicional: CapEx, Presupuesto y Previsión.

## ¿Cómo puedo asegurarme de que los costes fijos y variables fluyen a través del modelo?

Para asegurarse de que los costes Fijos y Variables funcionan correctamente y fluyen los dólares, tendrá que activar la asignación de Fijos y Variables. Para ello, seleccione el botón Fijo y Variable en la ventana desplegable Asignar línea de asignación. Realice esta selección para todas las líneas de asignación que conducen a las torres de recursos de TI.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_10.png)

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6558_11.png)

## ¿Cómo puedo influir directamente en el importe que aparece en los informes de App Dev?

Para afectar al importe en dólares que está vinculado al informe Fijo/Variable, tendrá que seleccionar los botones Fijo y Variable para las líneas de asignación. Por ejemplo: si está intentando indicar el desglose Fijo/Variable en el nivel Mano de obra, entonces tanto el botón Fijo como el Variable tendrán que estar seleccionados en todas las líneas de asignación que fluyen al objeto Mano de obra. Si está intentando indicar el desglose Fijo/Variable en el nivel de torre de recursos de TI, deberá seleccionar los botones Fijo y Variable en todas las líneas de asignación que fluyen al objeto de torre de recursos de TI.

## Puntos de partida clave

- Todas las líneas de asignación situadas por debajo de las torres de recursos informáticos deben tener seleccionados los botones Fijo y Variable.
- Sólo las líneas de imputación que fluyen directamente hacia el objeto sobre el que se informa, y que también tienen seleccionados los botones Fijo y Variable, se mostrarán como costes Fijos/Variables en el informe.
- Para afectar directamente a los importes visualizados en los informes Fijo/Variable, deberán ajustarse las líneas de imputación que ruedan al objeto sobre el que se está informando.

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
