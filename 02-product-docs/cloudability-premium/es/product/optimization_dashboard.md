---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Panel de optimización"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
source_path: "product/optimization_dashboard.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Panel de optimización

## Centro de optimización

El panel de optimización ofrece una vista centralizada de todas las iniciativas y perspectivas relacionadas con la optimización. Este centro de mando de optimización proporciona

- Una visión prospectiva de las oportunidades de ahorro en Compromisos y Redimensionamiento
- Una visión retrospectiva del impacto de estas iniciativas y del ahorro que han supuesto los Compromisos y la Reducción de Dimensiones

## Oportunidades

La página de oportunidades muestra tanto las oportunidades de optimización de recursos (basadas en las recomendaciones de Rightsizing de Cloudability ) como las de compromisos (basadas en las recomendaciones de compromisos de Cloudability ).

## Oportunidades de optimización de recursos

Información resumida de la superficie de optimización de recursos de sus recomendaciones de dimensionamiento, sujeta a las selecciones de Preferencias realizadas en la página Preferencias de dimensionamiento: Panel de control.

La optimización de recursos proporciona una visibilidad de alto nivel sobre el total de oportunidades y proporciona enlaces para acceder a más información de las recomendaciones de rightsizing en Cloudability.

Además de las propias oportunidades, el panel de optimización ofrece una puntuación COIN para contextualizarlas.

**Puntuación COIN:** COIN (o Índice de Optimización de Costes) es un método que proporciona contexto en torno a una oportunidad de optimización.

Se calcula **como** COIN = 100\*(1 – (Oportunidad de optimización/Gasto)), por lo que un COIN de 100 implicaría un gasto sin oportunidades disponibles.

Donde:

- **Oportunidad de optimización:** es la suma de los ahorros disponibles por el ajuste adecuado, sujetos a las preferencias seleccionadas, la vista y los filtros aplicados.

- **Gasto:** se refiere al gasto relevante y optimizable medido por la métrica de coste relevante basada en su selección de preferencias. Cuando se selecciona la base de coste bajo demanda en la página de preferencias, la puntuación COIN se calculará utilizando el gasto como medida en el coste (lista). Cuando se selecciona la base de coste efectiva, la puntuación COIN se calculará utilizando el coste (amortizado ajustado) o el coste (amortizado), dependiendo de la disponibilidad de las métricas. Cuando el gasto amortizado ajustado no está disponible, el cálculo utiliza la métrica Coste (amortizado).

El COIN, tal y como se calcula en este cuadro de mando, se limita a los servicios admitidos en el motor de asignación de derechos de Cloudability, por lo que el gasto en servicios no admitidos en el motor de asignación de derechos de Cloudability no se incluye en el cálculo del COIN.

**Preferencias**

Las recomendaciones de optimización de la carga de trabajo que se muestran como parte del panel de optimización se pueden controlar a través de las preferencias. La página de preferencias (que se encuentra *en* Configuración > Preferencias de ajuste de tamaño > Panel de control) ofrece las siguientes opciones y se aplica a nivel de toda la organización.

**Base** de costes efectiva frente a base de costes bajo demanda: la base de costes deseada para el conjunto de recomendaciones mostrado. Aunque no todos los tipos de recomendaciones tienen una base de coste «efectiva», cuando se selecciona la base de coste efectiva: La base de coste efectiva se mostrará cuando sea relevante y se proporcionará la base de coste bajo demanda para seguir ofreciendo una visión completa de sus oportunidades de optimización.

Esta selección también influye en los costes que se utilizan para contextualizar las oportunidades en sus cálculos COIN. Cuando se selecciona la base de coste bajo demanda, la puntuación COIN se calculará utilizando el coste (lista). Cuando se selecciona la base de coste efectiva, la puntuación COIN se calculará utilizando el coste (amortizado ajustado) o el coste (amortizado), dependiendo de la disponibilidad de las métricas.

**Recomendaciones avanzadas frente a básicas:** esta configuración solo está disponible para los clientes de Cloudability Premium y permite a las organizaciones elegir si desean que el panel de control se rellene con las recomendaciones de optimización generadas por Cloudability (visibles en la pestaña «Básico» de la página de optimización) o con las recomendaciones generadas por el potente motor de optimización de Turbonomic (visibles en la pestaña «Avanzado»)

**Recomendaciones básicas Preferencias** : esta sección permite a la organización personalizar aún más el conjunto de recomendaciones básicas cuando se selecciona la opción anterior. Las recomendaciones avanzadas se pueden perfeccionar mediante políticas en lugar de estas preferencias a nivel del panel de control.

- **Período retrospectivo de 10 o 30 días: los usuarios pueden seleccionar si desean ver recomendaciones basadas en la utilización de recursos durante los últimos 10 días o los últimos 30 días.**
- **Incluir recomendaciones pospuestas:** las organizaciones pueden optar por ver el panorama completo de oportunidades (incluidas aquellas que han decidido «posponer» y que quizá no sean viables a corto plazo) o centrarse en las oportunidades más viables excluyendo las recomendaciones pospuestas.
- **Las claves de etiqueta o dimensiones** empresariales están presentes en los menús desplegables «dividir por» de cada widget.

## Oportunidades de compromiso

La sección de oportunidades de compromiso ofrece una visión general de los ahorros disponibles a través de descuentos basados en el compromiso.

Nota: Las oportunidades de compromiso son por defecto de 3 años y los descuentos asociados en este momento.

Al igual que la optimización de recursos, también está disponible una puntuación COIN basada en la optimización de tarifas.

## Ahorro obtenido

El ahorro realizado muestra el impacto de las actividades de ahorro de costes, tanto en los recursos como en las actividades de reducción de derechos.

Un intervalo de fechas seleccionable en la parte superior de la página de ahorro realizado permite a los usuarios personalizar el intervalo de fechas.

- Para los ahorros de recursos realizados, el intervalo de fechas seleccionado filtra la fecha de la acción (cuando Cloudability detecta un cambio en la configuración de los recursos), de modo que sólo el impacto de las acciones
- Para los ahorros de compromiso realizados, el intervalo de fechas seleccionado proporciona una ventana de información para los ahorros logrados durante ese intervalo. Debido a que los diferentes proveedores proporcionan diferentes niveles de datos:
- Para los ahorros por compromiso de AWS y Azure : los ahorros obtenidos para el rango seleccionado se calculan en función de la diferencia entre lo que habría pagado (el coste equivalente bajo demanda del uso de recursos) menos lo que pagó realmente (coste (amortizado ajustado) que incluye los compromisos).
- Para los ahorros de compromiso de GCP : los ahorros se informan desde la cartera de compromisos.

Además de por fecha, las páginas de ahorro realizado pueden filtrarse por servicio, cuenta, grupo de cuentas o región.

**Recurso**

El ahorro de Recursos Realizados se construye sobre la funcionalidad Rightsizing ROI, mostrando el impacto de las recomendaciones y acciones rastreadas en Rightsizing ROI.

**Compromiso**

Superficies de ahorro realizado por compromiso: información resumida sobre el ahorro obtenido comparando el coste real del uso basado en la cobertura del compromiso y los descuentos en relación con los precios a la carta

## Explorador COIN

La tercera pestaña del panel de optimización ofrece una experiencia de generación de informes dinámica para la puntuación COIN con el nivel de detalle deseado. Los usuarios pueden seleccionar los campos deseados, incluyendo etiquetas o asignaciones comerciales, para ver y comparar sus puntuaciones COIN

El cálculo COIN y las métricas utilizadas se describen anteriormente y son coherentes entre la pestaña Oportunidad y la pestaña Explorador.

COIN Explorer permite a los usuarios seleccionar dinámicamente el período de revisión o la base de coste (anulando la página de preferencias) y respeta la preferencia seleccionada para incluir o excluir recomendaciones pospuestas o la fuente de la recomendación (cuando sea relevante).

## Temas adicionales

**Permisos**

El panel de control Optimización no tiene permisos independientes asociados. La información de este conjunto de funciones se basa en funciones que abarcan el dimensionamiento de derechos, el ROI del dimensionamiento de derechos y los compromisos, junto con los datos de costes subyacentes. Para utilizar eficazmente esta funcionalidad, necesita los permisos asociados a esas funciones subyacentes.

**Cómo funcionan las vistas**

Las vistas funcionarán de forma diferente con las distintas partes del cuadro de mando de Optimización en función de cómo funcionen las vistas con los datos subyacentes.

Por ejemplo, las vistas basadas en dimensiones de negocio se pueden utilizar con el panel de optimización, pero como estas vistas no se admiten en las páginas de recomendaciones de compromiso o cartera, no se rellenarán los aspectos de las páginas de oportunidades de compromiso y ahorros realizados.

**Exportación de datos**

Los datos del panel de optimización se pueden extraer directamente de las API de origen ( E.g., el redimensionamiento, los compromisos o los puntos finales de costes), pero no hay API disponibles para la puntuación COIN precalculada.

Los datos de COIN Explorer se pueden exportar a csv con la granularidad deseada en la página de COIN Explorer.
