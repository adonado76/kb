---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Utilización de la visión general del Gestor de compromisos para armonizar la estrategia de compromiso en toda la organización"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Guía para la gestión de compromisos"
source_path: "product/using_commitment_manager_to_align_the_organization_on_commitment_strategy.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Utilización de la visión general del Gestor de compromisos para armonizar la estrategia de compromiso en toda la organización

## Finalidad

La página de resumen es la sección de orientación de los compromisos de « Cloudability ». Reúne la situación actual (resultados históricos) y las oportunidades futuras (recomendaciones basadas en modelos) en una visión global que abarca todos los servicios y proveedores. Desde esta página de inicio, los equipos pueden empezar a ponerse de acuerdo sobre una visión global del impacto que tiene actualmente la optimización en su cartera y dónde podrían encontrarse las oportunidades más inmediatas. El gráfico personalizado y los indicadores clave de rendimiento (KPI) estandarizados orientan directamente a los usuarios antes de profundizar en la cartera o las recomendaciones. Este documento contiene instrucciones sobre cómo utilizar esta página.

Nota: Estamos trabajando para que esta página permita generar informes que abarquen distintos proveedores y servicios. Por el momento, debido a cuestiones de rendimiento y a la falta de paridad en las funciones, nuestro objetivo inicial es ofrecer compatibilidad con « AWS » en una sola cuenta de usuario.

## Acceso y configuración básica

La página «Gestor de compromisos» se encuentra en la sección «Optimizar» del menú de navegación de la izquierda, debajo del panel de optimización, y a diferencia de las páginas de cartera y recomendaciones.

**Tipo de servicio**

Para empezar, el selector de tipo de servicio es un menú desplegable de selección múltiple que sirve para elegir qué uso del servicio desea analizar. Cuando se selecciona un servicio, solo se analiza y se muestra en el gráfico el *consumo facturable*. Esta es una página de resumen, por lo que cualquier análisis más detallado de su cartera o de las oportunidades por tipo de inversión deberá realizarse en las páginas de cartera y recomendaciones. Cabe destacar que las páginas agregadas a nivel de proveedor y de servicio garantizan que las recomendaciones ofrecidas sean mutuamente excluyentes entre sí.

Para obtener más información sobre este comportamiento, consulta la sección *«Tipo de recomendación»* más abajo.

**Cuenta**

El selector de cuentas determina qué cuentas analizará nuestro modelo. El selector refleja la estructura jerárquica de tus cuentas y permite seleccionar varias opciones. Al seleccionar una o varias cuentas de pago (Gestión, Suscripción, Facturación), el botón selecciona o deselecciona todas las cuentas vinculadas que aparecen debajo. Al seleccionar una o varias cuentas vinculadas específicas (miembro, suscripción, proyecto), el botón correspondiente selecciona o deselecciona la cuenta, al tiempo que muestra un estado de selección parcial en la cuenta del pagador. Por lo general, se recomienda elegir una opción de cuenta que se ajuste a las preferencias de uso compartido configuradas en la consola del proveedor.

Para obtener más información sobre la terminología de las cuentas, consulta «[Estructura de cuentas por proveedor](commitments_vendor_account_structure.html) ».

**Base de coste**

La página de resumen no ofrece la opción de seleccionar la base de coste; en su lugar, si se ha configurado la opción «Ajustado», el gráfico se mostrará en términos de «Ajustado».

Para obtener más información, consulta «[Cómo influyen los precios negociados en los compromisos](custom_pricing_factors_across_commitments.html) ».

**Período de análisis**

La selección del periodo de análisis en la página de resumen difiere de la de las páginas de recomendaciones de carteras en que el usuario selecciona un intervalo de meses. Es importante destacar que los usuarios pueden elegir opciones para el futuro. Por defecto, el periodo de análisis abarca un mes anterior y tres meses posteriores a la fecha de hoy. Si se considera que el mes actual forma parte del periodo prospectivo o «previsión», dado que aún no han transcurrido todos los días del mes, la selección del periodo de análisis permite elegir tanto un intervalo de meses como un solo mes. Para comprender cómo funcionan los KPI en relación con el periodo de análisis seleccionado, consulte las opciones de KPI en la sección siguiente.

**Tipo de recomendación**

Esta sección permite incluir o excluir del informe la recomendación relativa al servicio seleccionado. «Óptimo» se refiere al tipo de recomendación óptimo. Para obtener más información sobre el tipo de recomendación óptimo, consulta «[Tipo de recomendación](using_commitment_recommendations_to_analyze_savings_opportunities.html) ». En el caso de los gastos de servicios que puedan estar cubiertos por varios tipos de compromiso, se considerará que la recomendación aplicada se corresponde con el tipo de compromiso basado en el gasto. Por ejemplo. En el caso de los recursos de computación de « AWS », la recomendación que se ofrece en esta página se refiere a los planes de ahorro de computación.

## Configuración e interpretación de los KPI

**Opciones de KPI - Tipo**

Esta opción sirve para configurar los indicadores clave de rendimiento (KPI). La opción «Estándar», que es la predeterminada, muestra dos valores por cada KPI que indican el primer y el último periodo seleccionados. Por lo tanto, esta norma te permite comparar los indicadores clave de rendimiento (KPI) en dos momentos distintos. «Total» calcula simplemente el KPI para todo el periodo de análisis seleccionado. «Promedio» muestra el promedio correspondiente al periodo de análisis seleccionado para el nivel de detalle del KPI elegido.

**Opciones de KPI: nivel de detalle**

Esta selección determina si la granularidad de los KPI se basa en la semana o en el mes. Además del tipo de KPI, el usuario dispone de la flexibilidad necesaria para analizar el rendimiento real y previsto a lo largo del tiempo.

**Opciones de KPI: comparación**

Esta selección añadirá un KPI de comparación cuando se elija el tipo de opción «KPI estándar» o «KPI medio». Utiliza el botón de alternancia que aparece al lado para configurar el indicador clave de rendimiento (KPI) de comparación, de modo que admita métodos de comparación tanto de variación absoluta como porcentual.

**Más opciones: nivel de detalle de los costes**

Actualmente, solo ofrecemos datos diarios en el gráfico. Por lo tanto, cada barra del gráfico representa el coste de un día

**Más opciones - Tipo de coste**

Admitimos el «coste real» y el «equivalente bajo demanda» (ODE). Cuando se selecciona «coste real» (opción predeterminada), todos los valores del gráfico se expresan en términos del coste pagado o que se prevé pagar. Cuando se selecciona ODE, todos los valores se expresan en términos de ODE, por lo que tanto la recomendación como el coste del compromiso existente se transforman a términos de ODE. Ten en cuenta que, cuando se selecciona «ODE» como tipo de coste, el gráfico de barras coincide con el del uso de ODE, ya que todos los costes mostrados se expresan en términos de «bajo demanda».

A continuación se muestran algunos ejemplos de cómo configurar el KPI para un caso de uso concreto.

**Ejemplo 1**

Caso de uso: «Hoy es 1 de julio de 2026 y me gustaría saber cómo ha evolucionado mi cartera a lo largo del primer semestre del año»

Configuración: Selecciona «Todos los servicios» y un pagador específico; selecciona un periodo de análisis comprendido entre enero de 2026 y junio de 2026; selecciona «Desactivado» como tipo de recomendación; selecciona «Estándar» como tipo de opciones de KPI, «Mes» como granularidad y «Activado» como opción de comparación.

Interpretación: El KPI marcado con la anotación amarilla corresponde al mes de enero. El indicador clave de rendimiento (KPI) en color morado corresponde al mes de junio. El indicador de rendimiento clave (KPI) de referencia para cada KPI individual representará la variación porcentual entre enero y junio. Esta configuración se puede utilizar para cualquier combinación de varios meses, por lo que permite comparar dos meses o semanas del pasado, dos meses o semanas del futuro, o el pasado con el futuro. En la interfaz de usuario, el pasado se denomina explícitamente «real», mientras que el futuro se denomina explícitamente «previsión».

**Ejemplo 2**

Caso de uso: «Hoy es 1 de julio de 2026. Me gustaría saber cuál sería mi ahorro neto y mi cobertura para todo el año en caso de que no realizara ninguna compra más»

Configuración: Selecciona «Todos los servicios» y un pagador específico; selecciona un periodo de análisis comprendido entre enero de 2026 y diciembre de 2026; selecciona «Desactivado» como tipo de recomendación; selecciona «Total» como tipo de opciones de KPI.

Interpretación: A partir de ahora habrá un único valor por cada KPI\*. A partir de ahora, los KPI mostrarán los valores correspondientes a todo el periodo seleccionado.

\*El coste restante también se incluye en el indicador clave de rendimiento (KPI) de costes.

**Ejemplo 3**

Caso de uso: «Hoy es 15 de julio de 2026; me gustaría conocer el valor de las oportunidades de compromiso inmediatas para el próximo mes». «Me gustaría ver esto en comparación con el mes anterior»

Configuración: Selecciona «Todos los servicios» y un pagador específico; selecciona un periodo de análisis comprendido entre junio de 2026 y agosto de 2026; selecciona «Óptima» como tipo de recomendación; selecciona «Estándar» como tipo de opciones de KPI, «Mes» como granularidad y activa la opción de comparación.

Interpretación: El indicador clave de rendimiento (KPI) marcado con la anotación amarilla corresponde al rendimiento real observado en junio. El indicador clave de rendimiento (KPI) en color morado corresponde al rendimiento previsto, una vez descontada la recomendación óptima de agosto. El indicador de rendimiento clave (KPI) comparativo para cada KPI individual representará la variación porcentual entre junio y agosto.

**Tema principal:** [Guía para la gestión de compromisos](../product/guide_to_commitment_management.html)
