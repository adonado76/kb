---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Informes y asignaciones de App Dev"
breadcrumb: []
source_path: "cost-transparency/reports-v103/appdevreportingallocations-6560.html"
images:
  - "resources/images/ct_images/6560_10.png"
  - "resources/images/ct_images/6560_11.png"
  - "resources/images/ct_images/6560_2.png"
  - "resources/images/ct_images/6560_3.png"
  - "resources/images/ct_images/6560_4.png"
  - "resources/images/ct_images/6560_5.png"
  - "resources/images/ct_images/6560_6.png"
  - "resources/images/ct_images/6560_7.png"
  - "resources/images/ct_images/6560_8.png"
  - "resources/images/ct_images/6560_9.png"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Informes y asignaciones de App Dev

Se aplica a : v12+

## Visión general

Intentando averiguar a qué se deben los costes de desarrollo de tu aplicación:

- ¿No parece correcto?
- ¿Demasiado bajo?
- ¿No se rellena?

¿Te estás haciendo las preguntas:

- ¿Cómo se calculan los costes de App Dev?
- ¿Qué es App Dev\_Cost y App Dev\_CapEx?
- ¿Cómo introduzco dólares en el modelo App Dev\_Cost?
- ¿Cómo me aseguro de que los costes de desarrollo de aplicaciones fluyen a través del modelo?
- ¿Cómo puedo influir directamente en el importe que aparece en los informes de App Dev?

La siguiente información le explica cómo se configuran los costes de desarrollo de aplicaciones en TBM Studio v12 y cómo puede editar estos costes.

## ¿Cómo se generan los costes de desarrollo de aplicaciones?

Los costes de App Dev se crean a partir de la métrica App Dev, que se calcula sumando los valores App Dev\_Cost y App Dev\_CapEx.

![desarrollo de aplicaciones](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_2.png)

## ¿Qué es App Dev\_Cost y App Dev\_CapEx?

Tanto App Dev\_Cost como App Dev\_CapEx son modelos out-of-the-box que funcionan en paralelo al modelo out-of-the-box Cost.

![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_3.png)

## ¿Cómo introduzco dólares en el modelo App Dev\_Cost?

Hay que seguir algunos pasos para asegurarse de que se rellenan valores en el modelo App Dev\_Cost:

1. Haga clic en la tabla **Fuente de costes**.

   ![fuente de costes](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_4.png)
2. Seleccione la métrica **App Dev\_Cost** en el menú desplegable **Modelo**.

   ![coste de desarrollo de la aplicación](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_5.png)
3. Haga clic en el controlador **OpEx Variable**.

   ![variable ope](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_6.png)
4. Haga clic en el menú desplegable **Añadir a**.

   ![tat a imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_7.png)
5. Asegúrese de que el botón **App Dev\_Cost** está seleccionado.

   ![coste de desarrollo de la aplicación](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_8.png)

Deberá añadir el botón App Dev\_Cost a todos los controladores utilizados en su modelo de costes. Los controladores son: OpEx Variable, OpEx Fijo, CapEx Variable y CapEx Fijo.

## ¿Cómo me aseguro de que los costes de desarrollo de aplicaciones fluyen a través del modelo?

Para asegurarse de que el modelo App Dev\_Cost funciona correctamente y de que fluyen los dólares, tendrá que activar la asignación App Dev\_Cost. Para ello, seleccione el botón App Dev\_Cost en la ventana desplegable "Asignar" de la línea de asignación. Esta selección deberá realizarse en todas las líneas de asignación que conducen a las torres de recursos informáticos.

![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_9.png)

![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_10.png)

## ¿Cómo puedo influir directamente en el importe que aparece en los informes de App Dev?

Para afectar al importe en dólares que está vinculado a los informes de desarrollo de aplicaciones, tendrá que seleccionar el botón App Dev\_Cost para las líneas de asignación que salen de las torres de recursos de TI que se ocupan de los costes de desarrollo de aplicaciones. Por ejemplo, si desea que todos los costes de la subtorre de recursos de TI de desarrollo de aplicaciones se muestren en los informes de desarrollo de aplicaciones, seleccione el botón App Dev\_Cost para la línea de asignación entre torres de recursos de TI y aplicaciones.

![imagen](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/6560_11.png)

Los informes de desarrollo de aplicaciones sólo mostrarán el coste de las líneas de asignación que tengan seleccionado el botón App Dev\_Cost. Apptio no alineará ningún coste a App Dev si el botón App Dev\_Cost no está seleccionado en la línea de asignación que fluye al Objeto Aplicaciones.

## Puntos de partida clave

- Cualquier línea de asignación por debajo de IT Resource Towers tendrá que tener seleccionado el botón App Dev\_Cost.
- Sólo las líneas de asignación que fluyen directamente al objeto Aplicaciones y tienen el botón App Dev\_Cost seleccionado, se mostrarán como costes de App Dev en los informes.
- El importe que aparece en los informes App Dev es la suma total de todas las líneas de Asignación que fluyen directamente al objeto Aplicaciones con el botón App Dev\_Cost seleccionado.
