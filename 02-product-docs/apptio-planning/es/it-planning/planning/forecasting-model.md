---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Modelos de previsión"
breadcrumb:
  - "Planning"
  - "Previsión inteligente"
source_path: "it-planning/planning/forecasting-model.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Modelos de previsión

La predicción inteligente evalúa automáticamente un conjunto diverso de modelos estadísticos para identificar el que mejor se adapta a sus datos. Estos modelos abarcan desde **métodos de suavizado adaptativo** hasta enfoques **basados en** **líneas de base** y regresión. El objetivo es capturar diferentes comportamientos de los datos, como tendencias de crecimiento, patrones estacionales repetitivos, volatilidad y relaciones lineales, para que el sistema pueda generar de forma coherente previsiones precisas y explicables en diversos escenarios empresariales.

La precisión de las previsiones suele mejorar cuando se dispone de más datos históricos, ya que los modelos pueden identificar mejor los patrones estacionales recurrentes, las tendencias a largo plazo y la variabilidad subyacente. Proporcionar un contexto histórico más rico permite al motor de predicción realizar predicciones más estables y fiables.

Modelos de previsión compatibles:

- **Los modelos Holt-Winters** son muy flexibles y se adaptan a las tendencias cambiantes y a los patrones estacionales.
- **Los modelos ingenuos** actúan como bases simples pero robustas, ideales para series volátiles o sin patrones.
- **Los modelos de regresión lineal** proporcionan estructura al aprender las relaciones lineales entre el tiempo (o los factores determinantes) y la métrica objetivo.

## Modelos de Holt-Winters

Estos modelos describen series temporales utilizando tres componentes adaptativos:

- **Error (E)** : cómo las nuevas observaciones ajustan el modelo (normalmente aditivo)
- **Tendencia (T)** : dirección del movimiento: Ninguna (N), Aditiva (A) o Aditiva amortiguada (Ad)
- **Estacionalidad (S)** – Ciclos repetitivos: Ninguno (N), Aditivo (A) o Multiplicativo (M)

Estos modelos son eficaces para la planificación financiera y la previsión operativa, ya que se actualizan automáticamente a medida que llegan nuevos datos y pueden representar de manera flexible una variedad de patrones del mundo real

## Variantes del modelo Holt-Winters

|  |  |  |  |  |
| --- | --- | --- | --- | --- |
| **Nombre del modelo** | **Notación ETS** | **Tipo de tendencia** | **Tipo de estacionalidad** | **Cuándo se utiliza** |
| Modelo de suavizado exponencial simple | ANN | Ninguna | Ninguna | Para datos estables sin tendencia ni estacionalidad. |
| Modelo de estacionalidad aditiva | ANA | Ninguna | Aditivo | Cuando los efectos estacionales son constantes en magnitud. |
| Modelo de estacionalidad multiplicativa | ANM | Ninguna | Multiplicativo | Cuando los efectos estacionales varían en proporción al nivel de datos. |
| Modelo de tendencia lineal de Holt | AAN | Aditivo | Ninguna | Cuando los datos tienen una tendencia lineal constante al alza o a la baja. |
| Modelo de tendencia amortiguada de Holt | AAdN | Amortiguación aditiva | Ninguna | Cuando la tendencia existe, pero se espera que se estabilice con el tiempo. |
| Modelo aditivo de Holt-Winters | AAA | Aditivo | Aditivo | Para tendencias + estacionalidad de magnitud constante. |
| Modelo multiplicativo de Holt-Winters | AAM | Aditivo | Multiplicativo | Para tendencias + variaciones estacionales proporcionales. |
| Modelo aditivo amortiguado de Holt-Winters | AAdA | Amortiguación aditiva | Aditivo | Cuando las tendencias se estabilizan y la estacionalidad es constante. |
| Modelo multiplicativo amortiguado de Holt-Winters | AAdM | Amortiguación aditiva | Multiplicativo | Cuando la tendencia se estabiliza y la estacionalidad se adapta a los datos. |

## Modelo de predicción ingenuo

El modelo ingenuo es el enfoque de previsión más sencillo: simplemente traslada el último valor histórico a los periodos futuros.

Para los planificadores financieros, este método resulta especialmente útil cuando:

- Los datos son volátiles, erráticos o difíciles de predecir
- Los resultados recientes son el mejor indicador del rendimiento futuro a corto plazo
- Necesitas una previsión de referencia clara para compararla con modelos más avanzados.

No requiere configuración y reacciona inmediatamente ante cambios repentinos, lo que lo convierte en un modelo fiable para realizar «estimaciones rápidas».

## Modelo de regresión lineal

El modelo de regresión lineal identifica una **tendencia lineal** en sus datos históricos y la extrapola al futuro.

Para escenarios de planificación financiera, este modelo resulta valioso cuando:

- Sus datos muestran una tendencia constante al alza o a la baja a lo largo del tiempo
- Usted desea previsiones que reflejen los factores impulsores previstos (por ejemplo, factores de crecimiento, eventos empresariales, hipótesis presupuestarias),
- Necesitas previsiones explicables, ya que la regresión muestra claramente cómo el tiempo o los factores influyen en los resultados.

Es un modelo práctico para los ciclos de presupuestación y planificación en los que el crecimiento, el declive o los factores operativos influyen en los valores futuros.

## Detalles estadísticos

Los detalles estadísticos proporcionan información técnica sobre cómo se generó la previsión y cuál es su fiabilidad. Estos detalles están destinados a los usuarios que desean comprender el comportamiento del modelo detrás de los valores previstos.

## Detalles de precisión

Estas métricas miden la desviación de las predicciones con respecto a la parte de prueba de sus datos históricos. Los números más bajos son mejores para todas las métricas de error.

|  |  |  |  |
| --- | --- | --- | --- |
| **Métrica** | **Rango** | **Descripción** | **Cómo usar/Interpretar** |
| **MAE** (Error absoluto medio) | De 0 a cualquier número positivo | La diferencia media entre los valores previstos por el modelo y los valores reales históricos. | Un MAE más bajo indica que el modelo se mantiene más cercano a los patrones históricos. Útil para comprender la coherencia general de las predicciones. |
| **MAPE** (Error porcentual absoluto medio) | 0.0 a cualquier número positivo (expresado como porcentaje) | El error medio de predicción expresado como porcentaje de los valores históricos. | Ayuda a comparar la precisión entre elementos con diferentes escalas. Rangos de interpretación típicos:  • **0-10 %:** Muy preciso  • **10-20 %:** Bueno  • **20-50 %:** Aceptable  • **50 %+:** Baja precisión  Nota: No es fiable cuando los valores históricos son muy pequeños o iguales a cero. |
| **MASE** (Error absoluto medio escalado) | 0.0 a cualquier número positivo, o **«infinito»** | Compara el error de su modelo con una previsión de referencia simple que repite el último valor histórico. | Rangos de interpretación típicos:  - **Menos que 1.0** **:** el modelo funciona mejor que la línea de base - **Igual a 1.0** : Funciona igual que la línea de base - **Más que « 1.0** **»:** el rendimiento inicial es mejor - **Infinito:** todos los valores históricos son constantes; la línea de base es la más adecuada |
| **RMSE** (Error cuadrático medio) | De 0 a cualquier número positivo | Similar al MAE, pero da más peso a los errores más grandes (grandes fallos). | - RMSE cercano al MAE → los errores de predicción son estables y consistentes - RMSE mucho más alto que MAE → los datos tienen picos o errores grandes ocasionales |
| **Puntuación de precisión** | 0 a 100 (escala porcentual) | Una puntuación combinada que refleja la precisión general del modelo basada en múltiples métricas de error. Las puntuaciones más altas indican un mejor rendimiento del modelo en comparación con las alternativas. | Rangos de interpretación típicos:  - **90-100 %:** Excelente - Previsión muy fiable - **75-89 %:** Bueno - Previsión fiable - **60-74 %:** Aceptable. Usar con precaución - **Por debajo del 60 %:** Deficiente: es posible que la previsión no sea fiable |

Utilice las siguientes directrices para identificar rápidamente qué modelo proporciona los resultados más fiables.

- **Puntuación de precisión:** los valores más altos indican una mayor precisión general.
- **MAPE:** Los valores más bajos son mejores.
- **MASE:** Los valores más bajos son mejores (lo ideal es que **sean inferiores a 1.0** ).
- **MAE / RMSE:** Los valores más bajos indican que el modelo se aproxima más a sus datos históricos.

## Parámetros

Los parámetros determinan en qué medida el modelo se basa en valores recientes frente a tendencias a largo plazo y patrones estacionales.

**Alfa (suavizado de nivel)**

Controla la importancia que se le da al valor más reciente al estimar el nivel general de los datos.

- **Alfa más bajo** → suavizado más intenso; el modelo se basa más en el historial a largo plazo.
- **Alfa más alto** → suavizado más ligero; el modelo reacciona con mayor intensidad a los cambios recientes.
- **Alfa = 1** → solo se utiliza el último punto de datos para el nivel.

**Beta (suavización de tendencias)**

Controla la rapidez con la que el modelo actualiza su estimación de la tendencia a lo largo del tiempo.

- Se comporta de manera similar a Alpha, pero afecta específicamente al componente de tendencia.
- Un beta más alto hace que el modelo responda mejor a los cambios recientes en la tendencia; un beta más bajo lo estabiliza.

**Gamma (suavizado estacional)**

Controla cómo el modelo actualiza los patrones estacionales (por ejemplo, la estacionalidad trimestral o mensual).

- Similar en comportamiento a Alpha, pero aplicado al componente estacional.
- Un gamma más alto actualiza la estacionalidad basándose en períodos recientes; un gamma más bajo suaviza los efectos estacionales a lo largo de un historial más extenso.

## Tendencia y estacionalidad

Estos indicadores muestran en qué medida la tendencia y la estacionalidad influyen en la precisión del modelo. Te ayudan a identificar si los datos contienen movimientos significativos al alza o a la baja, o patrones repetitivos a lo largo del tiempo.

|  |  |  |  |
| --- | --- | --- | --- |
| **Métrica** | **Rango** | **Descripción** | **Cómo usar/Interpretar** |
| Fuerza de la tendencia | 0.0 a 1.0 | Indica en qué medida el componente de tendencia mejora la precisión del modelo. Calculado comparando el modelo original con el mismo modelo sin la tendencia. | Rangos de interpretación típicos: • **0.0:** No hay una tendencia significativa  • **0.0 — 0.3:** Tendencia débil  • **0.3 – 0.7:** Tendencia moderada  • **0.7 – 1.0:** Fuerte tendencia; |
| Fortaleza estacional | 0.0 a 1.0 | Indica en qué medida el componente estacional mejora la precisión del modelo. Calculado comparando el modelo original con el mismo modelo sin el componente estacional. | Rangos de interpretación típicos: • **0.0:** Sin patrón estacional  • **0.0 – 0.3:** Estacionalidad débil  • **0.3 – 0.7:** Estacionalidad moderada  • **0.7 – 1.0:** Patrones estacionales fuertes y consistentes |
