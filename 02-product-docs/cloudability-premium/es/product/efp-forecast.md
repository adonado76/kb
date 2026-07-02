---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Previsión mejorada"
breadcrumb:
  - "Cloudability Premium"
  - "Plan"
source_path: "product/efp-forecast.html"
images:
  - "images/efp-minigraph.jpg"
  - "images/efp-model-settings.jpg"
  - "images/efp-save-budget.jpg"
  - "images/efp-settings.jpg"
  - "images/efp-summary.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Previsión mejorada

Utiliza la página «Previsión mejorada» para generar y analizar previsiones de gasto en la nube. Utiliza la función «Intelligent Forecasting» para generar previsiones a partir de datos históricos reales y ofrece controles flexibles para analizar los resultados por factor de gasto. Puede comparar modelos de previsión, comprobar la precisión de los modelos y ajustar la selección de modelos para cada partida de previsión. Esto ayuda a mejorar la precisión de las previsiones, hace que sean más fáciles de entender y te ofrece un mayor control cuando sea necesario.

Para obtener más información sobre cómo funciona la previsión inteligente, consulta [la sección «Previsión inteligente».](intelligent-forecasting.html)

La página «Previsión mejorada» incluye los siguientes elementos:

- **Resumen** : muestra los indicadores clave de rendimiento (KPI) y un gráfico resumen del gasto real y previsto, con la opción de comparar con el presupuesto
- **Detalles** : muestra los detalles de las partidas de la previsión en una tabla para su análisis por factor de gasto
- **Controles de previsión** : se utilizan para generar previsiones, guardar los resultados en un presupuesto y aplicar un presupuesto a efectos comparativos

A continuación se describe este componente con más detalle.

## Resumen

Selecciona la pestaña **«Resumen»** para consultar los resultados generales de la previsión.

![](../../../../03-media/cloudability-premium/images/efp-summary.jpg)

Indicadores clave de rendimiento (KPI)

Las fichas de KPI muestran los totales de los datos reales y las estimaciones que aparecen en el gráfico resumen, junto con un total independiente correspondiente al ejercicio fiscal actual. Si se aplica un presupuesto, también se muestra un indicador clave de rendimiento (KPI) de desviación presupuestaria.

Cuadro resumen

El cuadro resumen muestra:

- Datos reales de períodos históricos
- Estimaciones para los períodos previstos
- Importes presupuestarios, en caso de que se aplique un presupuesto

Desde este punto de vista, **los «datos reales»** son los importes de gasto registrados históricamente, mientras que **las «estimaciones»** son los importes de gasto futuros previstos que el motor de previsión inteligente genera a partir de dichos datos reales. En conjunto, conforman la **previsión** global.

Las estimaciones se muestran con un **intervalo de confianza** que refleja los valores máximo y mínimo para un período determinado. **El intervalo de confianza** se basa en un intervalo estadístico y puede ampliarse con el tiempo a medida que aumenta la incertidumbre a medida que nos adentramos en el horizonte de previsión.

El ejercicio fiscal actual aparece resaltado en el gráfico para que puedas ver claramente cómo el gasto real y el previsto contribuyen al total del ejercicio fiscal actual.

Puedes interactuar con el gráfico de varias formas:

- Pasa el cursor por encima de un punto de datos para ver los valores detallados.
- Haz clic en un elemento de la leyenda para ocultar o mostrar el elemento del gráfico asociado a él.
- Haz clic en el icono de ampliación, que tiene forma de doble flecha, para ampliar el gráfico a tamaño de página completa.

## Detalles

Selecciona la pestaña **«Detalles»** para revisar y analizar los detalles de las partidas de la previsión.

Los detalles de las partidas de la previsión se muestran en una tabla, en la que cada fila representa el gasto histórico y el gasto futuro estimado para una combinación única de valores seleccionados de los factores que determinan el gasto. Para cada partida, la tabla muestra también el modelo de previsión seleccionado y su puntuación de precisión. Puedes ordenar, filtrar y agrupar la tabla por factores de gasto y otros valores de la tabla para comparar resultados, centrarte en patrones de gasto específicos y analizar la previsión desde diferentes perspectivas. También puedes mostrar u ocultar columnas de la tabla utilizando el selector de columnas de la barra lateral de la tabla o desde el menú del encabezado de la columna.

Los valores estimados para períodos futuros se generan a partir de los valores históricos reales mediante el motor Intelligent Forecast, que evalúa múltiples modelos estadísticos de previsión y selecciona automáticamente el modelo que mejor se ajusta a la serie de datos introducida.

Para obtener más información sobre los modelos compatibles y la selección de modelos, consulta [«Intelligent Forecasting».](intelligent-forecasting.html)

![](../../../../03-media/cloudability-premium/images/efp-minigraph.jpg)

Minigráfico de la línea de previsión

Para examinar con más detalle una partida concreta de la previsión, haz clic en el icono de expansión situado junto a la fila para abrir su minigráfico.

Puedes interactuar con el minigráfico de forma similar a como lo harías con el gráfico resumen:

- Pasa el cursor por encima de los puntos de datos para ver los detalles.
- Oculta o muestra los elementos del gráfico haciendo clic en las entradas de la leyenda; por ejemplo, para ocultar el **rango** de confianza.

También puedes consultar los detalles del modelo de previsión utilizado para generar los valores de previsión, comparar los resultados de otros modelos y cambiar el modelo seleccionado.

Configuración del modelo

Haz clic en **«Configuración del modelo»** en el minigráfico para abrir la configuración del modelo de previsión correspondiente a la línea de previsión seleccionada.

La página «**Configuración del** modelo» muestra gráficos lineales con todos los resultados del modelo de previsión. Los modelos aparecen en el panel de selección ordenados de mayor a menor según su precisión. El modelo que se está aplicando actualmente aparece resaltado tanto en la visualización del gráfico como en la lista de modelos.

![Mostrar todos los resultados del modelo en un minigráfico](../../../../03-media/cloudability-premium/images/efp-model-settings.jpg)

Utiliza la lista **«Seleccionar modelo»** para obtener una vista previa y elegir otro modelo de previsión. Al seleccionar un modelo de la lista, se resalta la línea correspondiente en el gráfico y el panel de información se actualiza para mostrar los detalles de ese modelo.

Selecciona **«Actualizar»** para aplicar el modelo seleccionado. Cuando lo hagas, los valores de las partidas de la previsión se actualizarán utilizando los resultados de ese modelo.

Selecciona el «Modelo **recomendado**» para volver al modelo recomendado por el motor de previsión inteligente.

Para cerrar la página **«Configuración del modelo»** y volver a los detalles de las partidas de la previsión, selecciona **«Cancelar»** o pulsa **Esc**.

Exportar

Para exportar los detalles de las partidas de la previsión, abre el menú desplegable de la tabla (los tres puntos) y selecciona «**Exportar** ». El archivo de exportación se genera en formato « CSV ».

## Controles de previsión

La cabecera de la página incluye controles de previsión comunes a las pestañas **«Resumen»** y «**Detalles** ». Utiliza estos controles para generar una previsión, guardar los resultados en un presupuesto y aplicar un presupuesto ya existente a efectos comparativos.

Configuración de previsiones

Selecciona **«Configuración de previsiones»** para generar una nueva previsión. Al hacer esto, se abre un panel en el que puedes seleccionar los parámetros de previsión. Al hacer clic en **«Aplicar»**, se genera la previsión utilizando los parámetros seleccionados. Mientras se genera la previsión, aparece una barra de progreso. Una vez finalizada la generación, los resultados están disponibles tanto en la pestaña **«Resumen»** como en la pest **aña «Detalles** ».

![Panel de configuración de previsiones](../../../../03-media/cloudability-premium/images/efp-settings.jpg)

Los ajustes de previsión incluyen lo siguiente:

| Valor | Descripción |
| --- | --- |
| Métrica de costes | Métrica de costes para la previsión. Entre las opciones disponibles se incluyen las métricas de costes estándar de « Cloudability » y cualquier métrica de costes personalizada. |
| Comienzo de los datos reales | Selecciona el primer mes de datos históricos reales que se incluirán en la serie de datos de entrada de la previsión. Esto define el periodo de referencia que utiliza el motor de previsión. Puedes elegir cualquier mes de inicio, pero debe ser, como mínimo, 12 meses anterior al mes actual.  El periodo inicial seleccionado puede influir en la detección de la estacionalidad. Aunque no es obligatorio, utilizar el inicio de un ejercicio fiscal o de un trimestre fiscal puede ayudar a ajustar los patrones de gasto recurrentes a tu calendario fiscal. En general, cuantos más datos históricos se disponga, mayor será la precisión de las previsiones. |
| Duración | Selecciona hasta qué punto en el futuro quieres hacer la previsión. Las opciones incluyen la elaboración de previsiones hasta el final del ejercicio fiscal actual, hasta el final del próximo ejercicio fiscal o para períodos fijos, como 12, 18 o 24 meses. |
| Gastos excluidos | Si lo deseas, puedes excluir **los créditos**, **los cargos únicos** o ambos del cálculo de la previsión. |
| Factores determinantes del gasto | Selecciona las dimensiones que se utilizarán para desglosar la previsión en partidas detalladas. Entre las opciones disponibles se incluyen dimensiones de « Cloudability », como «Business Dimensions», «Tags», «Account Groups» y «Vendor». Cada combinación única de valores de dimensión seleccionados se convierte en una partida de la tabla de detalles de la previsión. |

Nota: La tabla de detalles de la previsión admite hasta 1.000 elementos. Si la previsión genera más de 1.000 líneas de detalle, la tabla muestra las primeras 1.000 partidas, además de una fila **denominada «Otros»** que contiene la suma de las partidas restantes.

Guardar la previsión como presupuesto

Utiliza **la opción «Guardar»** para crear un presupuesto a partir de la previsión actual. Esto abre el panel «**Guardar presupuesto** », que ya contiene los valores previstos, los cuales se pueden modificar antes de guardarlos.

![Panel de ahorro presupuestario](../../../../03-media/cloudability-premium/images/efp-save-budget.jpg)

El panel «Guardar presupuesto» muestra la vista y la métrica de coste utilizadas para el nuevo presupuesto, junto con los valores por defecto de los campos obligatorios: nombre del presupuesto, período de inicio del presupuesto y duración.

Al elaborar un presupuesto a partir de la previsión actual:

- El indicador de costes presupuestarios coincide con la previsión y no se puede modificar
- Los períodos históricos se rellenan con datos reales
- los períodos futuros se rellenan con estimaciones
- los periodos que se encuentran fuera del rango de previsión actual se establecen en cero

Los presupuestos creados desde la página «Previsión mejorada» se ajustan a los límites del ejercicio fiscal. El inicio del presupuesto puede corresponder al año en curso, al anterior o al siguiente, y la duración puede oscilar entre 1 y 3 años.

Puedes modificar los importes que aparecen por defecto antes de guardar. Haz doble clic en una celda para introducir un nuevo valor. Los valores introducidos en períodos de resumen, como los totales trimestrales o anuales, se distribuyen automáticamente entre los períodos incluidos.

Una vez guardado, el presupuesto se puede gestionar desde la página «Presupuestos». Consulta [la sección «Presupuestos»](bf-budgets.html) para obtener más información.

Establecer un presupuesto

Utiliza el selector **de presupuesto** para aplicar un presupuesto ya existente al resumen de previsiones. Cuando se aplica un presupuesto, los importes presupuestados se muestran en forma de gráfico de barras superpuesto al gráfico de resumen, lo que permite visualizar cómo se comparan los valores reales y estimados con el presupuesto. También se ha añadido un indicador clave de rendimiento (KPI) de desviación presupuestaria.

- **[Previsión inteligente](../product/intelligent-forecasting.html)**
