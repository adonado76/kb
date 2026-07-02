---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Análisis financiero - Informe CapEx ( v107 )"
breadcrumb: []
source_path: "cost-transparency/reports-v107/itfmf-ct_financialreviewcapexv107.html"
images:
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_capexspendanalysis.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_opex.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_transactiondetail.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_variancedetail.png"
  - "resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_viewby.png"
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Análisis financiero - Informe CapEx ( v107 )

Se aplica a: Planificación y Costing Standard en TBM Studio 12.3 y posteriores, con Plantilla v107 y posteriores

## Casos de uso

- Seguimiento de los gastos de TI por CIO -1 a nivel ejecutivo, por propietario del centro de costes y por grupo de costes
- Analizar los detalles a nivel de transacción para comprender los impulsores del plan de desviación
- Identificar desviaciones significativas entre gastos y planes

El informe **Financial Review - CapEx** ofrece una visión ejecutiva de la variación global del presupuesto de CapEx y de los gastos de su organización en CapEx. El informe desglosa los costes de TI por grupo de costes y propietario para que pueda determinar qué propietarios de TI son responsables del mayor gasto en TI. Varios gráficos del informe también le ayudan a determinar si las desviaciones son reales o se deben a errores de categorización.

Utilice este informe para crear un informe ejecutivo que explique los gastos de TI CapEx y para realizar las revisiones financieras periódicas que son esenciales para gestionar eficazmente los gastos de TI. Los datos de este informe incluyen las partidas del libro mayor para que pueda ajustar los planes en función de las desviaciones.

Nota: El informe **"Financial Review" - CapEx** requiere la instalación del componente CTF - CapEx.

Este informe está diseñado para ser utilizado por las siguientes funciones:

- CIO -1 (Oficina TBM)
- Propietarios de centros de coste
- Analistas financieros informáticos

## Visualizar el informe

Para Costing Standard:

1. Inicie sesión en Apptio y vaya a **Costing Standard**.
2. En la página de **inicio**, haga clic en **Finanzas de TI** y se abrirá el informe **Revisión financiera**.
3. En la pestaña de recopilación de informes (elemento 1, abajo), haga clic en **Financial Review - CapEx**.

Para la planificación:

1. Inicie sesión en Apptio y vaya a **Planificación > Costing Standard**.
2. En la página de **inicio**, haga clic en **Finanzas de TI**. Se abre el informe **de revisión financiera**.
3. En la pestaña de recopilación de informes (elemento 1, abajo), haga clic en **Financial Review - CapEx**.

El informe contiene los siguientes elementos.

![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_opex.png)

(1) Recogida de informes
:   Esta colección de informes proporciona los detalles financieros de TI que necesita para revisar las desviaciones del gasto y la precisión de las previsiones:

    - [Informe financiero ( OpEx ) informe ( v107 )](itfmf-ct_financialreview107.html)
    - Financial Review - CapEx ( v107 ) (descrito en este artículo)
    - [Informe de análisis financiero ( v104 y posteriores)](../reports-v104/itfmf-ct_financialanalysis104.html)
    - [Informe de análisis de grupos de costes ( v104 y posteriores)](../reports-v104/itfmf-ct_costpoolanalysis104.html)

(2) Cortadoras
:   Utilice los cortadores locales y globales para refinar los datos de su informe. Los separadores de este informe le permiten ver sus datos de costes por región, grupo de cuentas y responsabilidad organizativa, incluido el centro de costes, el propietario del centro de costes y el propietario (por ejemplo, CIO -1)).

    Las siguientes funciones pueden utilizar los divisores de este informe para obtener una vista más personalizada:

    Controlador financiero de TI o CIO
    :   Sin configurar ningún cortador, puede ver el resumen de los gastos en todos los centros de coste de la organización. Puede desglosar los grupos de costes, los propietarios de los centros de costes y las cuentas individuales.

    Propietario del centro de costes o CIO -1
    :   Establezca los divisores **Centro de costes** o **Propietario del centro de costes** para filtrar sus áreas de responsabilidad.

    Analista financiero
    :   Establezca el rebanador **del centro de costes** para las áreas a las que presta asistencia, o establezca un grupo de cuentas específico para permitir un análisis detallado de los gastos por categorías en toda la organización.

(3) Indicadores clave de rendimiento
:   Los KPI proporcionan una visión de alto nivel de su gasto en CapEx :

    **CapEx** y **CapEx Presupuesto**
    :   Estos dos KPI muestran su presupuesto global de CapEx comparado con el de CapEx para el mes en curso. El porcentaje de varianza se muestra a la derecha.

    **CapEx YTD** y **CapEx Presupuesto YTD**
    :   Estos dos KPIs muestran su gasto en CapEx comparado con el presupuesto YTD. El porcentaje de varianza se muestra a la derecha.

    **CapEx** y **Presupuesto anual CapEx**
    :   Estos dos KPIs muestran su gasto anual en CapEx y el presupuesto YTD. El porcentaje de varianza se muestra a la derecha.

(4) CapEx Variación presupuestaria
:   Utilice este gráfico y esta tabla para ver su desviación presupuestaria en CapEx en función del grupo de costes, el grupo de cuentas, el propietario, el propietario del centro de costes o el ID del centro de costes. Puede utilizar esta información para ver los gastos superiores o inferiores a los previstos por categoría e identificar las fuentes de mayor desviación o excepción con respecto al plan. Esta información le ayudará a priorizar dónde buscar oportunidades de reducción.

    Seleccione una métrica (grupo de costes, grupo de cuentas, propietario, propietario del centro de costes o ID del centro de costes) de la lista **Ver por** para rellenar los gráficos **Top Over Budget YTD** y **Top Under Budget YTD** con los elementos de la categoría con la mayor desviación presupuestaria respecto al plan YTD.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_viewby.png)

    Haga clic en una barra de cualquiera de los gráficos para abrir un cuadro de diálogo **Detalle de la desviación** que muestra CapEx gastos, presupuesto, desviación y porcentaje de desviación para la métrica seleccionada. Utilice las opciones de la parte superior de la página para alternar entre periodos de tiempo.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_variancedetail.png)

    Haga clic en un código de cuenta para ver los detalles de la transacción desde su fuente financiera de registro (como su libro mayor).

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_transactiondetail.png)

    La tabla **Detalles** le permite ver un resumen del presupuesto, la desviación y el porcentaje de desviación de CapEx para todos los elementos de la métrica seleccionada en función de los periodos de tiempo que seleccione encima de la tabla.

    Preguntas contestadas:

    - ¿Dónde hay desviaciones significativas entre el gasto y el plan?
    - ¿Qué centros de coste están generando desviaciones entre los gastos y el plan y quién es responsable de cada centro de coste?
    - ¿La desviación es real o se debe a una categorización errónea de un gasto?

(5) CapEx Variación de las previsiones
:   Seleccione una métrica (grupo de costos, grupo de cuentas, propietario, propietario del centro de costos o ID del centro de costos) de la lista **Ver por** para completar los gráficos **Pronóstico superior hasta la fecha** y **Pronóstico inferior hasta la fecha** con los elementos con la mayor variación del pronóstico con respecto al plan hasta la fecha.

    Haga clic en una barra de cualquiera de los gráficos para abrir un cuadro de diálogo **Detalle de la des** viación que muestra CapEx gastos, previsiones, desviación prevista y porcentaje de desviación para la métrica seleccionada. Utilice las opciones de la parte superior de la página para seleccionar un periodo de tiempo.

    Haga clic en un código de cuenta de la columna izquierda para ver los detalles de la transacción desde su fuente financiera de registro (como su libro mayor).

    La tabla **Detalles** permite ver un resumen de la previsión CapEx, la desviación de la previsión y el porcentaje de desviación de la previsión para todos los artículos de la métrica seleccionada en función de los periodos de tiempo que seleccione encima de la tabla.

    Preguntas contestadas:

    - ¿A qué se destina la mayor parte de nuestro gasto en TI? ¿Por pool de costes? ¿Por propietario de TI (por ejemplo, CIO-1 )? ¿Por propietario del centro de coste?
    - ¿Dónde se han producido cambios significativos en los gastos de un periodo a otro?
    - ¿Cuáles son las partidas de gastos que contribuyen al coste de una función informática?

(6) Análisis de gastos
:   Seleccione una métrica (grupo de costos, grupo de cuentas, propietario, propietario del centro de costos o ID del centro de costos) de la lista **Ver por** para completar los gráficos **Pronóstico superior hasta la fecha** y **Pronóstico inferior hasta la fecha** con los elementos con la mayor variación del pronóstico con respecto al plan hasta la fecha.

    ![](../../../../../03-media/apptio-costing-standard/resources/images/ct_images/itfmf-ct_images/itfmf-ct_financialreview_capexspendanalysis.png)

    Haga clic en una barra del gráfico para abrir un cuadro de diálogo **Detalle de la des** viación que muestra CapEx gastos, previsiones, desviación prevista y porcentaje de desviación para la métrica seleccionada. Utilice las opciones de la parte superior de la página para seleccionar un periodo de tiempo.

    Haga clic en un código de cuenta de la columna izquierda para ver los detalles de la transacción desde su fuente financiera de registro (como su libro mayor).

    La tabla **Detalles** permite ver un resumen de la previsión CapEx, la desviación de la previsión y el porcentaje de desviación de la previsión para todos los artículos de la métrica seleccionada en función de los periodos de tiempo que seleccione encima de la tabla.

    Preguntas contestadas:

    - ¿A qué se destina la mayor parte de nuestro gasto en TI? ¿Por pool de costes? ¿Por propietario de TI (por ejemplo, CIO-1 )? ¿Por propietario del centro de coste?
    - ¿Dónde se han producido cambios significativos en los gastos de un periodo a otro?
    - ¿Cuáles son las partidas de gastos que contribuyen al coste de una función informática?

(7) Perspectivas financieras
:   Utilice la pestaña **Perspectivas del** ejercicio para consultar el presupuesto, la previsión y la variación de gastos del ejercicio en CapEx.

    Haga clic en cualquier elemento de la columna izquierda para ver los detalles de la transacción desde su fuente financiera de registro (como su libro mayor).

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
