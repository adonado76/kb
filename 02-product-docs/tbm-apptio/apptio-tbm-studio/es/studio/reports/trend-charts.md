---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos de tendencias"
breadcrumb: []
source_path: "studio/reports/trend-charts.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu557.png"
  - "resources/images/studio_images/studioimages/studio/stu558.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos de tendencias

**Se aplica a** : TBM Studio 12.0 y posteriores

Un gráfico de tendencias muestra un valor a medida que cambia con el tiempo. Por ejemplo, podría establecer la tendencia de los costes de los centros de datos de los últimos cuatro trimestres como se muestra en la siguiente imagen. Se crean tablas basadas en gráficos de tendencias. Para crear un gráfico de tendencias, arrastre un campo de tiempo al área **Eje** del cuadro de diálogo **Configuración de componentes ad hoc**.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu557.png)

## Crear un gráfico de tendencias

1. Seleccione el icono **Gráfico** en el **Informe**.
2. En el cuadro de diálogo **Configuración de componentes ad hoc**, arrastre los campos a las áreas correspondientes.
3. Arrastre un campo de tiempo al área Eje.

   El gráfico mostrado en la imagen anterior se creó utilizando los campos que se muestran en la siguiente imagen:

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu558.png)
4. Para establecer el número de periodos mostrados en el gráfico de tendencias, haga clic con el botón derecho del ratón en el valor del área **Eje** y seleccione una de las opciones:
   - **Este trimestre** - Muestra los tres meses del trimestre fiscal actual.
   - **Este semestre** - Muestra los seis meses del semestre fiscal actual.
   - **Este año** - Muestra los 12 meses del ejercicio en curso.
   - **Rango** - Muestra un cuadro de diálogo en el que puede establecer el número de meses que se mostrarán retrocediendo y avanzando en el tiempo desde el mes actual

## Bloquear el periodo de tiempo

Por defecto, los gráficos de tendencias muestran la tendencia hacia delante y hacia atrás en relación con el periodo de tiempo seleccionado. Si desea bloquear el gráfico de tendencias a un período de tiempo específico, establezca el período de tiempo utilizando el campo **Período de tiempo de los datos** en la pestaña **Avanzado** del cuadro de diálogo **Propiedades**.

Por ejemplo, suponga que su año fiscal va de enero a diciembre y desea que un gráfico de tendencias muestre los datos del año fiscal independientemente del periodo seleccionado en ese momento. El **período de tiempo de la fecha** debe ser **el inicio del ejercicio fiscal en curso**.
