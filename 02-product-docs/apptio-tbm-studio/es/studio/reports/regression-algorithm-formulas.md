---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Fórmulas del algoritmo de regresión"
breadcrumb: []
source_path: "studio/reports/regression-algorithm-formulas.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Fórmulas del algoritmo de regresión

**Se aplica a** : TBM Studio 12.0 y posteriores

Una característica útil de los gráficos de tendencias es la posibilidad de añadir proyecciones a los gráficos. La aplicación ofrece una serie de algoritmos de regresión que pueden aplicarse a las proyecciones. Los algoritmos son:

- Regresión
- Regresión lineal múltiple
- Regresión polinómica
- Suavizado exponencial simple
- Suavizado exponencial doble
- Media móvil

Los algoritmos de la aplicación se basan en algoritmos de regresión estándar de Java OpenForecast. Las descripciones que figuran a continuación proceden de la documentación de Java: [OpenForecast](http://openforecast.sourceforge.net/docs/) "(se abre en una pestaña o una ventana nueva)").

## Regresión

Implementa un modelo de regresión lineal de una sola variable. Un modelo de regresión lineal de una sola variable intenta básicamente trazar una línea recta a través de los puntos de datos. Esta recta se define por su gradiente o pendiente, y el punto en el que intercepta el eje x (es decir, donde la variable independiente tiene, quizá sólo teóricamente, un valor cero). Matemáticamente, suponiendo que la variable independiente es x y la variable dependiente es y, entonces esta línea se puede representar como:

> ```
> y = intercept +
>           slope * x
> ```

## Regresión lineal múltiple

Implementa un modelo de regresión lineal de múltiples variables. Un modelo de regresión lineal de variables múltiples intenta esencialmente colocar un hiperplano a través de los puntos de datos. Matemáticamente, suponiendo que las variables independientes son xi y la variable dependiente es y, entonces este hiperplano se puede representar como:

> ```
> y = a0 + a1*x1 +
>           a2*x2 + a3*x3 +
> ```

...donde ai son los coeficientes de la regresión. El coeficiente a0 también se denomina intercepto. Si todas las xi fueran cero (teóricamente al menos), es el valor previsto de la dependentVariable, y.

## Regresión polinómica

Implementa un modelo de regresión polinómica de una sola variable. Un modelo de regresión polinómica de una sola variable intenta básicamente trazar una línea polinómica (una curva, si lo prefiere) a través de los puntos de datos. Matemáticamente, suponiendo que la variable independiente es x y la variable dependiente es y, entonces esta línea se puede representar como:

> ```
> y = a0 + a1*x +
>           a2*x2 + a3*x3 + ... + am*xm
> ```

## Alisamiento exponencial simple

Un modelo de previsión de suavizado exponencial simple es un modelo muy popular utilizado para producir una serie temporal suavizada. Mientras que en los modelos simples de Media Móvil las observaciones pasadas se ponderan por igual, el Suavizado Exponencial asigna ponderaciones exponencialmente decrecientes a medida que las observaciones se hacen más antiguas.

En otras palabras, las observaciones recientes tienen relativamente más peso en las previsiones que las observaciones más antiguas.

En el caso de las medias móviles, las ponderaciones asignadas a las observaciones son las mismas e iguales a 1/N. Sin embargo, en el suavizado exponencial simple, se utiliza un parámetro de suavizado o una constante de suavizado para determinar las ponderaciones asignadas a las observaciones.

Este sencillo modelo de suavización exponencial comienza estableciendo la previsión para el segundo periodo igual a la observación del primer periodo.

## Alisamiento exponencial doble

El suavizado exponencial doble (también conocido como suavizado exponencial Holt) es un perfeccionamiento del popular modelo de suavizado exponencial simple, pero añade otro componente, que tiene en cuenta cualquier tendencia en los datos. Los modelos de suavización exponencial simple funcionan mejor con datos en los que no hay componentes de tendencia o estacionalidad. Cuando los datos muestran una tendencia creciente o decreciente a lo largo del tiempo, las previsiones de suavizado exponencial simple tienden a quedarse atrás con respecto a las observaciones. El suavizado exponencial doble está diseñado para tratar este tipo de series de datos teniendo en cuenta cualquier tendencia en los datos.

Obsérvese que el suavizado exponencial doble sigue sin tener en cuenta la estacionalidad. Para obtener mejores previsiones suavizadas exponencialmente utilizando datos en los que se espera o se sabe que hay una variación estacional en los datos, utilice el suavizado exponencial triple.

Al igual que en la suavización exponencial simple, en los modelos de suavización exponencial doble, las observaciones pasadas reciben ponderaciones exponencialmente menores a medida que las observaciones envejecen. En otras palabras, las observaciones recientes tienen relativamente más peso en las previsiones que las observaciones más antiguas.

Hay dos ecuaciones asociadas al Suavizado Exponencial Doble:

> ```
> ft =
>           a.Yt+(1-a)(ft-1+bt-1)
> ```
>
> `bt = g.(ft-ft-1)+(1-g).bt-1`

donde:

- Yt es el valor observado en el momento t.
- ft es la previsión en el momento t.
- bt es la pendiente estimada en el momento t.
- a, que representa alfa, es la primera constante de suavizado, utilizada para suavizar las observaciones.
- g, que representa la gamma, es la segunda constante de suavizado, utilizada para suavizar la tendencia.

Para inicializar el modelo de suavizado exponencial doble, f1 se fija en Y1, y la pendiente inicial b1 se fija en la diferencia entre las dos primeras observaciones; es decir, Y2-Y1.

## Alisamiento exponencial triple

El alisamiento exponencial triple (también conocido como método Winters) es un perfeccionamiento del popular modelo de alisamiento exponencial doble, pero añade otro componente que tiene en cuenta cualquier estacionalidad (o periodicidad) de los datos.

Los modelos de suavización exponencial simple funcionan mejor con datos en los que no hay componentes de tendencia o estacionalidad. Cuando los datos muestran una tendencia creciente o decreciente a lo largo del tiempo, las previsiones de suavizado exponencial simple tienden a quedarse atrás con respecto a las observaciones. El suavizado exponencial doble está diseñado para tratar este tipo de series de datos teniendo en cuenta cualquier tendencia en los datos. Sin embargo, ninguno de estos modelos de suavizado exponencial tiene en cuenta la estacionalidad de los datos.

Para obtener mejores previsiones suavizadas exponencialmente de datos en los que se espera o se sabe que hay una variación estacional en los datos, utilice el suavizado exponencial triple.

Al igual que en la suavización exponencial simple, en los modelos de suavización exponencial triple, las observaciones pasadas reciben ponderaciones exponencialmente menores a medida que las observaciones envejecen. En otras palabras, las observaciones recientes tienen relativamente más peso en las previsiones que las observaciones más antiguas. Esto es válido para todos los términos implicados. A saber, el nivel de base Lt, la tendencia Tt, así como el índice de estacionalidad st.

Hay cuatro ecuaciones asociadas al Suavizado Exponencial Triple:

> ```
> Lt =
>           a.(xt/st-c)+(1-a).(Lt-1+Tt-1)
> ```
>
> ```
> Tt = b.(Lt-Lt-1)+(1-b).Tt-1
> st =
>           g.(xt/Lt)+(1-g).st-c
> ```
>
> `ft,k = (Lt+k.Tt).st+k-c`

donde:

- Lt es la estimación del valor base en el momento t. Es decir, la estimación para el momento t tras eliminar los efectos de la estacionalidad y la tendencia.
- a, que representa alfa, es la primera constante de suavizado, utilizada para suavizar Lt.
- xt es el valor observado en el momento t.
- st es el índice estacional en el momento t.
- c es el número de periodos del patrón estacional. Por ejemplo, c=4 para datos trimestrales, o c=12 para datos mensuales.
- Tt es la tendencia estimada en el momento t.
- b, que representa beta, es la segunda constante de suavización, utilizada para suavizar las estimaciones de tendencia.
- g, que representa la gamma, es la tercera constante de suavizado, utilizada para suavizar las estimaciones de estacionalidad.
- ft,k es la previsión al final del periodo t para el periodo t+k.

Hay varias formas de obtener valores iniciales para el modelo de suavización exponencial triple. El planteamiento aplicado aquí utiliza los dos primeros años (o ciclos completos) de datos para obtener los valores iniciales de Lt, Tt y st. Por lo tanto, se necesitan al menos dos ciclos completos de datos para inicializar el modelo. Para obtener los mejores resultados, se recomienda disponer de más datos (lo ideal sería un mínimo de 4 o 5 ciclos completos). Esto da al modelo la oportunidad de adaptarse mejor a los datos, en lugar de depender de obtener (adivinar) buenas estimaciones de las condiciones iniciales.

## Media móvil

Un modelo de previsión de media móvil se basa en una serie temporal construida artificialmente en la que el valor de un periodo determinado se sustituye por la media de ese valor y los valores de un cierto número de periodos anteriores y posteriores. Como habrá adivinado por la descripción, este modelo se adapta mejor a los datos de series temporales, es decir, a los datos que cambian con el tiempo.

Dado que el valor previsto para un periodo determinado es una media de los periodos anteriores, la previsión siempre parecerá ir por detrás de los aumentos o disminuciones de los valores observados (dependientes). Por ejemplo, si una serie de datos tiene una tendencia al alza notable, una previsión de media móvil proporcionará generalmente una subestimación de los valores de la variable dependiente.

El método de la media móvil tiene la ventaja sobre otros modelos de previsión de que suaviza los máximos y mínimos (o valles) en un conjunto de observaciones. Sin embargo, también tiene varios inconvenientes. En concreto, este modelo no produce una ecuación real. Por lo tanto, no es del todo útil como herramienta de previsión a medio-largo plazo. Sólo puede utilizarse con fiabilidad para prever uno o dos periodos en el futuro.

El modelo de media móvil es un caso especial de la media móvil ponderada más general. En la media móvil simple, todas las ponderaciones son iguales.
