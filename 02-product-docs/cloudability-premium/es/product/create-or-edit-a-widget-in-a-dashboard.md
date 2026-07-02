---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Crear o editar un widget en un panel de control"
breadcrumb:
  - "Cloudability Premium"
  - "Trabajar con cuadros de mando e informes"
  - "Cloudability Paneles de control"
  - "Ver y configurar paneles de control"
source_path: "product/create-or-edit-a-widget-in-a-dashboard.html"
images:
  - "images/create-widget.png"
  - "images/date-picker.png"
  - "images/dimension-picker.png"
  - "images/filters.png"
  - "images/widget-range.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Crear o editar un widget en un panel de control

Los widgets son los componentes básicos de los paneles de control de Cloudability. Cada widget se configura por separado y puede tener una finalidad diferente. Esta página explica los pasos de configuración y las opciones disponibles para los usuarios al crear o editar widgets en los paneles de control de Cloudability.

Hay varios tipos diferentes de widgets que se pueden añadir a un panel de control. Los tipos de widgets disponibles son:

- Gráfico
- Estimación
- Dimensionamiento correcto
- Gráfico circular
- Número
- Tabla

![](../../../../03-media/cloudability-premium/images/create-widget.png)

Existen ciertas diferencias entre cada tipo de widget y cada widget se describe detalladamente en su propia página del Centro de ayuda. Hay ciertas opciones de configuración comunes que se comparten entre todos los tipos de widgets, con la excepción de los widgets «Estimación» y «Redimensionamiento».

**Configuración del intervalo de fechas**

[ADVERTENCIA: La configuración del intervalo de fechas no está disponible para los tipos de widgets «Estimación» y «Redimensionamiento».]

Cada widget se puede configurar para mostrar los datos de un intervalo de tiempo determinado. El intervalo de fechas aplicado a un widget se muestra en la parte superior del panel del widget, tanto en el modo de edición como al visualizar un panel de control en el que se utiliza un widget. Puede ser un intervalo de fechas relativo (como «Últimos 7 días» o «Último mes») o un intervalo de fechas estático y absoluto (por ejemplo, «16 de julio de 2025 - 24 de julio de 2025»).

![](../../../../03-media/cloudability-premium/images/widget-range.png)

El intervalo de fechas se puede configurar utilizando el selector modal de intervalos de fechas al editar un widget:

![](../../../../03-media/cloudability-premium/images/date-picker.png)

Hay varios intervalos de fechas preconfigurados entre los que elegir:

- Ayer
- Hoy (UTC)
- Esta semana
- Semana pasada
- Este mes
- Último mes
- Este trimestre
- Último trimestre
- Este año
- Último año
- Últimos 7 días
- Últimos 14 días
- Últimos 30 días
- Últimos 60 días
- Últimos 90 días

Todos los rangos preconfigurados son «relativos», lo que significa que el rango de fechas se actualizará automáticamente a medida que pase el tiempo. Por ejemplo, «Últimos 7 días» se convertirá en «1 de junio de 2025 - 7 de junio de 2025» el 7 de junio, pero se actualizará a «2 de junio de 2025 - 8 de junio de 2025» el 8 de junio.

Los usuarios también pueden seleccionar un intervalo de fechas personalizado eligiendo «Personalizado» en el menú desplegable o seleccionando el intervalo de fechas deseado mediante la interfaz del calendario. Los intervalos de fechas «personalizados» pueden ser estáticos, lo que significa que no cambiarán con el paso del tiempo, o pueden configurarse como «continuos», lo que significa que se ajustarán un día cada día.

Otra opción para configurar el intervalo de fechas es «Fecha de inicio personalizada hasta la fecha». Con esta opción, los usuarios pueden definir el inicio del intervalo de fechas, y el final del intervalo de fechas siempre será la fecha actual (la de hoy).

Por último, los widgets se pueden configurar para incluir un intervalo de fechas «Comparar». Con estas opciones, los widgets mostrarán dos valores (o dos series de datos): uno de cada uno de los intervalos de fechas seleccionados. Esto permite comparar fácilmente dos periodos distintos, por ejemplo, para comprender rápidamente la diferencia en el coste de dos meses consecutivos. Al utilizar esta opción, los widgets de tabla también mostrarán el cambio «neto» entre dos rangos de fechas o la diferencia «porcentual». El widget Número mostrará la diferencia en «porcentaje» entre dos intervalos de fechas.

**Configuración de filtros en Widgets**

[ADVERTENCIA: La configuración de filtros no está disponible para los tipos de widgets «Estimación» y «Redimensionamiento».]

Para cada widget, los usuarios pueden optar por reducir el conjunto de datos para excluir los costes que no sean relevantes para un caso de uso determinado. Por ejemplo, los usuarios pueden optar por excluir o incluir los costes de un proveedor de servicios en la nube concreto.

Los filtros se pueden configurar para que coincidan con una dimensión o métrica seleccionada. Esto incluye métricas empresariales, dimensiones empresariales, grupos de cuentas o etiquetas.

![](../../../../03-media/cloudability-premium/images/dimension-picker.png)

Para configurar un filtro, los usuarios deben seleccionar una medida que se utilizará para evaluar, utilizando el menú desplegable «Medida».

A continuación, se debe seleccionar un operador de filtro, utilizando una de las opciones disponibles en la lista:

- es igual a
- no es igual a
- menor que
- mayor que
- menor o igual que
- mayor o igual que
- contiene
- no contiene

Por último, los usuarios deben seleccionar un valor para la condición del filtro. Puede ser un número (para filtros basados en métricas), un valor de texto o una fecha. Para las dimensiones, la función « Cloudability » (Seleccionar valores) permite seleccionar valores de la lista de valores disponibles en el conjunto de datos del usuario. Además, para introducir un gran número de valores en un filtro, los usuarios pueden copiar y pegar una lista de valores separados por comas en el campo de entrada de texto del filtro.

[ADVERTENCIA]

Cuando se utiliza la condición de coincidencia «igual» o «no igual», las siguientes entradas se tratan de forma equivalente:

«Único», «cargo único», «cargo único», «cargo único», «cargo único»

«Cargo recurrente», «cargo-recurrente», «recurrente», «cargo\_recurrente»

Se pueden crear múltiples filtros para un solo widget.

Los filtros aplicados a la misma medida se crearán utilizando la condición lógica «O», mientras que la condición «Y» se utilizará entre diferentes medidas. Por ejemplo:

![](../../../../03-media/cloudability-premium/images/filters.png)

- **[Widget de gráfico](../product/chart-widget.html)**
- **[Widget de estimación](../product/estimate-widget.html)**
- **[Widget de redimensionamiento](../product/rightsizing-widget.html)**
- **[Widget de tarta](../product/pie-widget.html)**
- **[Widget de números](../product/number-widget.html)**
- **[Widget de tabla](../product/table-widget.html)**
- **[Widget de texto](../product/text-widget.html)**

**Tema principal:** [Ver y configurar paneles de control](../product/view-and-configure-dashboards.html)
