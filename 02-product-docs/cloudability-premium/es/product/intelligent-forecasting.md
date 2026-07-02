---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Previsión inteligente"
breadcrumb:
  - "Cloudability Premium"
  - "Plan"
  - "Previsión mejorada"
source_path: "product/intelligent-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Previsión inteligente

## Visión general

Funciones como la «Página de previsiones mejorada» y « Cloudability Financial Planning » utilizan el «Motor de previsiones inteligente» para generar previsiones a partir de series temporales históricas. El motor de previsión inteligente evalúa múltiples modelos de previsión para identificar el que mejor se ajusta a cada serie temporal histórica. Estos modelos están diseñados para reflejar diferentes tipos de comportamiento en las series temporales, como valores estables, crecimiento o disminución lineales, patrones estacionales recurrentes y cambios en la variabilidad a lo largo del tiempo. Al ser compatible con múltiples tipos de modelos, el motor puede generar previsiones más precisas, comprensibles y adaptables a distintos escenarios.

Por lo general, la precisión de las previsiones mejora cuando se dispone de más datos históricos, ya que los modelos pueden identificar mejor los patrones estacionales recurrentes, las tendencias a largo plazo y la variabilidad subyacente. Un conjunto de datos históricos más amplio proporciona al motor más contexto para seleccionar el modelo más adecuado y generar una previsión más estable.

El motor de previsión inteligente admite varios tipos de modelos de previsión, entre los que se incluyen el modelo de referencia, la tendencia lineal, la media móvil y determinados modelos ETS. Estos modelos están diseñados para ajustarse a diferentes patrones históricos en los datos y utilizan diferentes configuraciones o parámetros en función de su funcionamiento.

El motor de previsión inteligente aplica todos los tipos de modelos compatibles a cada parámetro de previsión y selecciona el modelo que mejor se adapta a la tendencia histórica de ese parámetro.

[Más información sobre cómo funciona la previsión inteligente](#topic__operation)

## Tipos de modelos de predicción

| Tipo de modelo | Descripción |
| --- | --- |
| **Línea base** | El modelo de referencia, también conocido como **«ingenuo»**, utiliza el valor histórico más reciente como simple previsión, sin modelar explícitamente la tendencia ni la estacionalidad. Es más adecuado para patrones relativamente estables en los que los datos históricos recientes constituyen un indicador razonable de los valores futuros a corto plazo. Dado que no tiene en cuenta patrones más complejos, puede resultar menos preciso cuando los valores aumentan o disminuyen de forma constante, o siguen ciclos estacionales recurrentes. |
| **Tendencia lineal** | El modelo de tendencia lineal ajusta una línea recta a los valores históricos y extrapola esa tendencia hacia el futuro. Es ideal para datos que aumentan o disminuyen de forma constante con el paso del tiempo. Dado que no tiene en cuenta los patrones estacionales recurrentes, puede resultar menos preciso cuando los valores varían según patrones cíclicos mensuales, trimestrales, diarios o de otro tipo. |
| **Media móvil** | El modelo de media móvil pronostica los valores futuros calculando la media de un número determinado de los últimos periodos históricos. Por ejemplo, una media móvil de tres períodos utiliza la media de los tres períodos más recientes para generar la previsión. Este modelo resulta útil cuando los datos contienen ruido y es necesario suavizar las fluctuaciones a corto plazo. Dado que suaviza los datos históricos recientes, tiende a reaccionar con mayor lentitud ante los cambios y puede subestimar los valores al alza o sobreestimar los valores a la baja. |
| **Modelos ETS** | ETS son las siglas de «**Error, Tendencia y Estacionalidad** ». Los modelos ETS constituyen una familia de modelos de suavizado exponencial en los que cada modelo se define por la forma de sus componentes de error, tendencia y estacionalidad. En notación estándar, un modelo ETS se escribe como **ETS (Error, Tendencia, Estacionalidad)**. Por ejemplo, ETS(A,A,N) representa un modelo con error aditivo, tendencia aditiva y sin estacionalidad.  En la notación abreviada que se utiliza aquí:   - **A** = aditivo - **Ad** = tendencia aditiva amortiguada - **N** = ninguno - **M** = multiplicativo |

Entre los modelos basados en ETS compatibles se incluyen los siguientes:

| Acrónimo de ETS | Nombre descriptivo | Descripción técnica |
| --- | --- | --- |
| ANN | Suavizado exponencial simple | Modela el error aditivo sin tendencia ni estacionalidad |
| AAN | La tendencia lineal de Holt | Modela un error aditivo con tendencia aditiva y sin estacionalidad |
| ANA | Suavizado exponencial con estacionalidad aditiva | Modela el error aditivo sin tendencia y la estacionalidad aditiva |
| ANM | Suavizado exponencial con estacionalidad multiplicativa | Modela un error aditivo sin tendencia y una estacionalidad multiplicativa |
| AAdN | La tendencia amortiguada de Holt | Modela un error aditivo con una tendencia aditiva amortiguada y sin estacionalidad |
| AAA | Aditivo Holt-Winters | Modela el error aditivo con tendencia aditiva y estacionalidad aditiva |
| AAM | Multiplicativo de Holt-Winters | Modela el error aditivo con una tendencia aditiva y una estacionalidad multiplicativa |
| AAdA | Curva de Holt-Winters con tendencia amortiguada | Modela el error aditivo con una tendencia aditiva amortiguada y una estacionalidad aditiva |
| AAdM | Modelo multiplicativo de Holt-Winters con tendencia amortiguada | Modela el error aditivo con una tendencia aditiva amortiguada y una estacionalidad multiplicativa |

Los modelos ETS resultan útiles cuando los patrones de los datos son más complejos y pueden incluir cambios de tendencia sostenidos, comportamientos estacionales recurrentes o ambos. Dado que los modelos ETS incluyen parámetros adicionales, a menudo pueden ajustar patrones complejos de series temporales con mayor precisión que los modelos más simples, siempre que se disponga de suficientes datos históricos para estimar dichos parámetros de forma fiable. Cada variante del ETS representa una hipótesis estructural diferente sobre el comportamiento de la serie temporal, y el Motor de Previsión Inteligente evalúa estas variantes para determinar qué estructura se ajusta mejor al patrón histórico observado.

## Comparación de modelos de predicción

| Familia de modelos | Nombre de modelo | Parámetros del modelo | Ideal para | Limitación principal |
| --- | --- | --- | --- | --- |
| Modelos de referencia | Ingenuo | Ninguna | Datos estables en los que el historial reciente constituye un indicador razonable de los valores futuros a corto plazo | Menos preciso cuando los valores presentan una tendencia sostenida o patrones estacionales recurrentes |
| Modelos de tendencias | Tendencia lineal | Pendiente e intersección | Datos que aumentan o disminuyen de forma constante con el paso del tiempo | Menos preciso cuando los valores presentan patrones estacionales recurrentes |
| Modelos de promediado | Media móvil | Longitud de la ventana | Datos ruidosos en los que resulta útil el suavizado a corto plazo | Tiende a dar un retraso cuando los valores suben o bajan rápidamente |
| Modelos ETS | Suavizado exponencial simple (ANN) | α | Datos estables con una tendencia o variación estacional limitada | Menos preciso cuando los valores presentan una tendencia sostenida o patrones estacionales recurrentes |
| Modelos ETS | Tendencia lineal de Holt (AAN) | α, β | Datos que muestran una tendencia constante al alza o a la baja, pero sin un patrón estacional repetitivo | Menos preciso cuando los valores presentan patrones estacionales recurrentes |
| Modelos ETS | Suavizado exponencial con estacionalidad aditiva (ANA) | α, γ | Datos con patrones estacionales recurrentes, pero con un nivel general relativamente estable | Menos preciso cuando los valores presentan una tendencia al alza o a la baja sostenida |
| Modelos ETS | Suavizado exponencial con estacionalidad multiplicativa (ANM) | α, γ | Datos con patrones estacionales recurrentes cuyo volumen aumenta o disminuye con el nivel general | Menos preciso cuando los valores presentan una tendencia al alza o a la baja sostenida |
| Modelos ETS | La tendencia amortiguada de Holt ( AAdN ) | α, β, φ | Datos cuya tendencia se prevé que se modere con el tiempo | Menos preciso cuando los valores presentan patrones estacionales recurrentes |
| Modelos ETS | Aditivo Holt-Winters (AAA) | α, β, γ | Datos con tendencias y patrones estacionales cuyo volumen se mantiene relativamente constante a lo largo del tiempo | Menos adecuado cuando los efectos estacionales aumentan o disminuyen con el nivel general |
| Modelos ETS | Modelo multiplicativo de Holt-Winters (AAM) | α, β, γ | Datos con tendencias y patrones estacionales cuyo volumen aumenta o disminuye con el nivel general | Menos preciso cuando los valores son bajos o varían considerablemente de un periodo a otro |
| Modelos ETS | AAdA | α, β, γ, φ | Datos con patrones estacionales y una tendencia que se prevé que se modere con el tiempo | Requiere datos históricos suficientes para estimar esos parámetros de forma fiable |
| Modelos ETS | Modelo multiplicativo de Holt-Winters con tendencia amortiguada ( AAdM ) | α, β, γ, φ | Datos con patrones estacionales cuyo volumen aumenta o disminuye en función del nivel general y cuya tendencia se prevé que se modere con el tiempo | Menos preciso cuando los valores son bajos o varían considerablemente de un periodo a otro |

## Parámetros del modelo de predicción

Los distintos tipos de modelos de predicción utilizan diferentes ajustes o parámetros.

| **Parámetro** | **Utilizados en** | **Significado** |
| --- | --- | --- |
| Ninguna | Línea base | El modelo de referencia no utiliza parámetros de previsión configurables |
| Inclinación | Tendencia lineal | Define la tasa de aumento o disminución de la línea de tendencia ajustada |
| Interceptación | Tendencia lineal | Define el punto de inicio de la línea de tendencia ajustada |
| Longitud de la ventana | Media móvil | Define el número de períodos históricos que se incluyen en la media móvil |
| α (alfa) | Todos los modelos de ETS | **Suavizado del nivel** : controla la rapidez con la que el modelo actualiza el nivel estimado, o valor de referencia, en función de los nuevos datos reales |
| β (beta) | Modelos ETS con tendencia | **Suavizado de tendencias** : controla la rapidez con la que el modelo actualiza la tendencia estimada en función de los nuevos datos reales |
| γ (gamma) | Modelos ETS con estacionalidad | **Suavizado estacional** : controla la rapidez con la que el modelo actualiza el patrón estacional estimado basándose en los nuevos datos reales |
| φ (fi) | Modelos ETS de tendencia amortiguada | **Amortiguación de la tendencia** : controla el grado de amortiguación de la tendencia proyectada a lo largo del tiempo |

En los modelos ETS, la notación ETS describe la estructura del modelo, mientras que los parámetros de suavizado controlan la forma en que el modelo actualiza sus **componentes de estado** internos a lo largo del tiempo. Estos componentes de estado incluyen **el nivel**, **la tendencia** y **la estacionalidad**. Estos componentes de estado difieren del componente **de error** del ETS, que describe la forma de los residuos —las diferencias entre los valores observados y los valores generados por el modelo durante el proceso de ajuste—.

Estos parámetros influyen en la capacidad de respuesta de la previsión ante nuevos valores observados y en la precisión con la que el modelo puede representar el nivel, la tendencia y la estacionalidad de los datos históricos.

**Cómo interpretar los parámetros de suavizado del ETS**

**El parámetro «Alpha» (suavizado del nivel)** determina el peso que se otorga al valor más reciente a la hora de estimar el nivel general de los datos.

- Un valor de alfa más bajo implica un suavizado más intenso; el modelo se basa en mayor medida en los datos históricos a más largo plazo
- Cuanto mayor sea el alfa, menor será el suavizado; el modelo reacciona con mayor intensidad a los cambios recientes
- Alfa = 1: solo se utiliza el último dato para actualizar el nivel

**El parámetro beta (suavizado de la tendencia)** determina la rapidez con la que el modelo actualiza su estimación de la tendencia a lo largo del tiempo.

- Se comporta de manera similar al alfa, pero se aplica específicamente al componente de tendencia
- Un beta más alto hace que el modelo sea más sensible a los cambios recientes en la tendencia
- Un beta más bajo hace que la estimación de la tendencia sea más estable

**Gamma (suavizado estacional)** controla cómo el modelo actualiza los patrones estacionales, como la estacionalidad mensual o trimestral.

- Se comporta de manera similar a alfa, pero se aplica al componente estacional
- Un valor gamma más alto ajusta la estacionalidad de forma más marcada basándose en los últimos periodos
- Un valor de gamma más bajo suaviza los efectos estacionales a lo largo de un historial más extenso

**Phi (amortiguación de la tendencia)** determina en qué medida el modelo reduce el efecto de la tendencia a lo largo del tiempo.

- Un valor más alto de phi hace que el efecto de la tendencia se mantenga más fuerte durante más tiempo
- Un valor más bajo de phi reduce el efecto de la tendencia más rápidamente
- Phi se utiliza únicamente en modelos de tendencia amortiguada.

## Indicadores de tendencias y estacionalidad

Los resultados del modelo ETS también pueden incluir indicadores **de intensidad de la tendencia**, **intensidad de la estacionalidad** y **período estacional**. Estos valores ayudan a mostrar en qué medida los componentes de tendencia y estacionales contribuyen a la precisión del modelo y con qué frecuencia se repiten los patrones estacionales.

| **Indicador** | **Rango** | **Descripción** | **Interpretación habitual** |
| --- | --- | --- | --- |
| Intensidad de la tendencia | 0.0 a 1.0 | Indica en qué medida el componente de tendencia mejora la precisión del modelo. Se calcula comparando el modelo original con el mismo modelo sin la tendencia. | - 0.0 = sin tendencia significativa - 0.0-0.3 = tendencia débil - 0.0-0.3 = tendencia débil - 0.7-1.0 = tendencia marcada |
| Intensidad de la estacionalidad | 0.0 a 1.0 | Indica en qué medida el componente estacional mejora la precisión del modelo. Se calcula comparando el modelo original con el mismo modelo sin el componente estacional. | - 0.0 = sin patrón estacional - 0.0 = sin patrón estacional - 0.3-0.7 = estacionalidad moderada - 0.7-1.0 = patrones estacionales marcados y constantes |
| Periodo estacional | Número entero positivo | Indica el número de periodos temporales que abarca un ciclo estacional completo y que utiliza el modelo. Por ejemplo, un valor de 12 representa un ciclo anual en datos mensuales, mientras que un valor de 7 representa un ciclo semanal en datos diarios. | Los valores más altos indican un ciclo de repetición más largo. |

Estos indicadores pueden ayudar a explicar por qué se eligió un modelo que incluye la tendencia o la estacionalidad. Unos valores más altos de «Fuerza de la tendencia» y «Fuerza de la estacionalidad» indican que el componente correspondiente contribuye de manera más significativa a la precisión de la previsión, mientras que el «Período estacional» indica la duración del ciclo repetitivo identificado en los datos.

## Cómo funciona la previsión inteligente

Cuando el motor de previsión inteligente genera una previsión, no se basa en un único modelo ni en valores de parámetros fijos. En cambio, adapta cada modelo compatible al patrón histórico de la variable objeto de la previsión, determinando los valores, ajustes o parámetros del modelo necesarios para ajustarse mejor a ese patrón. Este proceso de ajuste tiene lugar antes de que el motor evalúe los resultados de los modelos y seleccione el que ofrece mejores resultados.

Algunos modelos utilizan estructuras relativamente sencillas. Por ejemplo, un modelo de media móvil utiliza una longitud de ventana, mientras que un modelo de tendencia lineal utiliza la pendiente y la intersección ajustadas de la línea de tendencia histórica. Los modelos ETS son más adaptativos y utilizan uno o varios parámetros de suavizado, como alfa (α), beta (β), gamma (γ) y phi (φ), dependiendo de si el modelo incluye el nivel, la tendencia, la estacionalidad o la tendencia amortiguada.

En el caso de esos modelos ETS, el motor de previsión inteligente utiliza un proceso iterativo para calcular los valores de los parámetros que mejor se ajustan al patrón observado en los datos históricos del elemento objeto de la previsión.

Unos valores de los parámetros más altos o más bajos modifican la capacidad de respuesta del modelo ante nuevos valores observados. Por ejemplo, un valor alfa más alto hace que el nivel estimado reaccione más rápidamente a los cambios recientes en los datos, mientras que un valor alfa más bajo hace que el nivel cambie de forma más gradual.

Una vez seleccionados los valores óptimos de los parámetros para cada modelo, el motor de previsión inteligente evalúa los modelos para determinar cuál ofrece mejores resultados en comparación con los datos históricos. Mediante un enfoque de aprendizaje automático, aplica cada modelo a una parte anterior de los datos históricos, compara los valores previstos resultantes para una parte posterior de la misma serie con los valores observados conocidos y calcula el error porcentual absoluto medio simétrico (SMAPE). A continuación, convierte ese resultado en una puntuación de precisión y selecciona el modelo con la puntuación de precisión más alta.

Un modelo más sencillo, como el modelo de referencia o la media móvil, puede ofrecer mejores resultados en el caso de un patrón estable, mientras que un modelo ETS más avanzado puede funcionar mejor con datos que incluyan una tendencia, estacionalidad o ambas cosas. Al evaluar los modelos candidatos con una parte conocida de la serie de datos de entrada y puntuarlos de forma sistemática, el motor puede seleccionar el modelo que tenga más probabilidades de generar la previsión futura más precisa para ese artículo.

**Por qué es importante**

El motor de predicción inteligente genera predicciones que se adaptan a diferentes tipos de comportamiento de las series temporales. Un patrón estable puede representarse mejor mediante un modelo más sencillo, mientras que un patrón más dinámico o estacional puede requerir un modelo con parámetros de tendencia y estacionales ajustados a ese historial específico. Un patrón también puede comenzar siendo estable y evolucionar con el tiempo hasta convertirse en uno que requiera un modelo más complejo.

Dado que el motor de previsión inteligente selecciona tanto el modelo con mejor rendimiento como los valores de los parámetros que mejor se ajustan al patrón histórico, puede generar previsiones adaptadas a cada elemento de previsión, en lugar de basarse en un único enfoque fijo para todos los datos.

**Tema principal:** [Previsión mejorada](../product/efp-forecast.html)
