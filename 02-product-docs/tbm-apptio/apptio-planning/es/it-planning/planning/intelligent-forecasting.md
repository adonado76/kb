---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Descripción general de la previsión inteligente"
breadcrumb:
  - "Planning"
  - "Previsión inteligente"
source_path: "it-planning/planning/intelligent-forecasting.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Descripción general de la previsión inteligente

La función de previsión inteligente introduce técnicas avanzadas de previsión de series temporales en la planificación de e Apptio, lo que permite a los equipos elaborar previsiones más precisas y coherentes con menos esfuerzo manual. La función analiza los patrones históricos de gasto y aplica automáticamente el modelo más adecuado para cada partida.

**Características principales:**

- **Selección automatizada de modelos basada en tendencias históricas**

  El pronóstico inteligente analiza el patrón de series temporales de cada partida y selecciona automáticamente el modelo de pronóstico más adecuado.
- **Detección de valores atípicos para mejorar la precisión de las previsiones**

  Se detectan anomalías históricas, lo que permite a los usuarios ajustarlas, de modo que el modelo se entrena con datos más limpios y estables, lo que da lugar a resultados de previsión más fiables.
- **Previsiones más precisas y coherentes**

  La detección automatizada de patrones (tendencia, nivel, estacionalidad), el ajuste de parámetros y el suavizado optimizado producen una mayor precisión y reducen la variación de las previsiones entre los planificadores.
- **Mayor transparencia y control, con la posibilidad de revisar y perfeccionar los resultados.**

  Los planificadores pueden inspeccionar la configuración de los modelos, los parámetros de suavizado y las medidas de precisión estándar. Las previsiones son totalmente editables: los usuarios pueden aceptar, ajustar o anular los valores según sea necesario.

## Habilitar previsiones inteligentes

Nota: Para realizar estas tareas se requieren los roles de administrador o responsable del proceso presupuestario.

**Pasos para habilitar la previsión inteligente**

1. Vaya a **Configuración** **(icono de engranaje)** → **Perfil de la empresa**.
2. Asegúrese de que **la experiencia de la página Nuevos gastos (Beta)** esté habilitada primero; sin ella, no se puede utilizar la función de previsión inteligente. Para habilitar la función, siga estos pasos:
   - **Configuración general** → **Acceso y permisos** → Seleccionar **habilitar la nueva experiencia de la página de gastos (Beta)**
3. Seleccione **Previsión** → **Habilitar previsión inteligente.**
4. Haga clic en el botón **Guardar y salir.**

## Aplicar previsiones inteligentes

Nota: Para utilizar la función de previsión inteligente, es necesario disponer de un permiso de « *ITPPredictiveForecastingFeatureFullAccess* ». Los roles de administrador, responsable del proceso presupuestario y responsable del centro de costes ya cuentan con este permiso.

Los usuarios pueden crear o modificar previsiones definiendo los periodos de previsión y los datos históricos en el cuadro de diálogo **Previsión**.

1. Navega hasta la página **Gastos** y activa la opción **Nueva vista**.
2. Seleccione la pestaña «Gastos» (Resumen, Otros, Activos, Contratos, Mano de obra o Actividad laboral).
3. Ve a la pestaña «**Otros** ».
4. Seleccione uno o más elementos marcando la casilla situada junto a cada uno de ellos.
5. A continuación, seleccione **«Previsión»** en el menú contextual o haga clic en el botón «**Previsión** ».
6. En el cuadro de diálogo **Previsión**, seleccione el **intervalo de fechas histórico** seleccionando el **período inicial** y **el período final**. Estos datos se utilizarán para generar la previsión.
7. *Se requiere un mínimo de 3 meses de datos para ejecutar Intelligent Forecasting.*
8. En el mismo cuadro de diálogo, configure el **período de previsión** seleccionando el **período inicial** y **el período final**.
   - **El período de inicio de** la previsión se establece automáticamente por defecto en el mes inmediatamente posterior al período final histórico, pero se puede modificar.
   - **El período final del** pronóstico puede ser cualquier mes entre el período inicial del pronóstico y el período final del plan.
9. Para revisar la previsión generada, haga clic en **Vista previa**.
10. Puede cambiar entre los modelos de previsión para comparar los resultados y los detalles estadísticos.
11. Cuando esté satisfecho con la previsión, seleccione el modelo que desea aplicar y haga clic en «**Aplicar modelo seleccionado** » para actualizar las partidas seleccionadas.

## Tipos de gastos admitidos para la previsión inteligente

**Varios y resumen**

- Los demás gastos se pueden prever desde la pestaña **«Otros»** o desde la pestaña «**Resumen** ».
- Al aplicar una previsión, los valores financieros correspondientes se actualizan automáticamente.

**Trabajo y actividad laboral**

- Compatible con **el trabajo** y **la actividad laboral (horas)**.
- La vista previa de la previsión muestra:
- **Plantilla**
- **Horario** de la actividad laboral
- Al aplicar una previsión, se actualizan automáticamente tanto los datos financieros relativos a la mano de obra como los relativos a la actividad laboral.

**Contratos y activos**

- Compatible con **contratos de amortización manual** y **activos de depreciación manual**.
- La función de previsión está **desactivada** para las filas de contratos y activos no compatibles.
- Al aplicar una previsión, se actualizan los datos financieros tanto de los contratos como de los activos.

**Notas importantes**

- La función de previsión inteligente **no** está disponible para:
- Líneas externas
- Estados financieros generados
- Gastos presentados
- Datos reales
- Está previsto que en una futura versión se incluya la compatibilidad con el uso **de datos reales como datos históricos** para la elaboración de previsiones.
- También está previsto incluir en una futura versión la compatibilidad con **la previsión inteligente para los gastos agrupados**.

## Revisión e interpretación de la vista previa de la previsión

Nota: Para utilizar la función de previsión inteligente, es necesario disponer de un permiso de « *ITPPredictiveForecastingFeatureFullAccess* ». Los roles de administrador, responsable del proceso presupuestario y responsable del centro de costes ya cuentan con este permiso.

La vista previa de la previsión muestra cómo serán los resultados de la previsión, basándose en los datos introducidos. Esto le brinda la oportunidad de analizar y trabajar con los datos de previsión proyectados antes de aplicarlos, lo que le ayuda a tomar decisiones más informadas.

1. La vista previa del pronóstico está disponible después de hacer clic en el botón **Vista previa** del cuadro de diálogo **Pronóstico**.
2. **El gráfico de vista previa** muestra la visualización de los datos históricos seguidos de los datos previstos, que se representan como una línea punteada.
3. **El gráfico de vista previa** muestra los valores previstos, así como un intervalo de confianza que indica los límites superior e inferior dentro de un área sombreada.
4. La puntuación **de precisión de predicción** muestra la precisión general de la previsión, indicando en qué medida las predicciones del modelo coinciden con los datos históricos.
5. Haga clic en la pestaña **Detalles estadísticos** para revisar los detalles del pronóstico.

Para obtener más información sobre los modelos y los detalles estadísticos, consulte «[Modelos de previsión](forecasting-model.html "La previsión inteligente evalúa automáticamente un conjunto diverso de modelos estadísticos para identificar el que mejor se adapta a sus datos. Estos modelos abarcan desde métodos de suavizado adaptativo hasta enfoques basados en líneas de base y regresión. El objetivo es capturar diferentes comportamientos de los datos, como tendencias de crecimiento, patrones estacionales repetitivos, volatilidad y relaciones lineales, para que el sistema pueda generar de forma coherente previsiones precisas y explicables en diversos escenarios empresariales.") »

## Identificación y ajuste de valores atípicos en las previsiones

Nota: Para utilizar la función de previsión inteligente, es necesario disponer de un permiso de « *ITPPredictiveForecastingFeatureFullAccess* ». Los roles de administrador, responsable del proceso presupuestario y responsable del centro de costes ya cuentan con este permiso.

**Valores atípicos**

Un valor atípico es cualquier punto de datos dentro del **último 20 % de sus valores históricos** que se encuentra **fuera del rango de confianza del modelo** para ese momento. Estos puntos indican momentos en los que el valor real se desvió más de lo esperado de los patrones típicos en los datos.

Durante la previsión, se evalúan y comparan múltiples modelos. Aunque no se muestran los intervalos de confianza del ajuste del modelo para los puntos históricos, cada valor ajustado tiene un rango de confianza estimado, similar a los intervalos que se muestran para la previsión.

La mayoría de los puntos históricos suelen coincidir estrechamente con los valores estimados por el modelo. Sin embargo, cuando un punto se encuentra notablemente fuera del rango de confianza esperado, se identifica como un valor atípico. Esto indica que el valor histórico fue inusualmente alto o bajo en comparación con lo que anticipaba el modelo.

Los valores atípicos pueden producirse debido a acontecimientos puntuales, picos o caídas inusuales en el gasto o anomalías en la introducción de datos. Resaltarlos te ayuda a comprender qué valores históricos pueden estar contribuyendo a un comportamiento inesperado del modelo o a una menor precisión de las previsiones.

**Ajuste de valores atípicos**

1. Cuando Intelligent Forecasting identifica valores atípicos en sus datos históricos, puede verlos en la vista previa de la previsión y se activa el botón Valores atípicos detectados.
2. Haga clic en el botón **«Valores atípicos detectados»** en la vista previa. Se abre el panel **Detectar valores** atípicos.
3. Haga clic en **Ajustar valores atípicos** para actualizar la previsión y ver el impacto del ajuste.
4. Cuando se detectan múltiples valores atípicos, se ajustan secuencialmente desde el principio del conjunto de datos. Esto significa que cada valor atípico ajustado se aplica al cálculo del ajuste para el valor atípico posterior, lo que da como resultado una previsión más precisa.
5. Cuando esté satisfecho con la previsión, haga clic en **«Aplicar modelo seleccionado»** para actualizar las partidas seleccionadas.
