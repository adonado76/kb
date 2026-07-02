---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos superpuestos"
breadcrumb: []
source_path: "studio/reports/overlay-charts.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep303.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos superpuestos

**Se aplica a** : TBM Studio 12.0 y posteriores

Un gráfico superpuesto muestra dos series de datos en un mismo gráfico. Por ejemplo, puede mostrar el presupuesto y los datos reales en un gráfico, o la capacidad de almacenamiento disponible y la capacidad de almacenamiento utilizada en un gráfico. En la siguiente imagen se muestra un ejemplo de gráfico superpuesto:

![ejemplo de gráfico superpuesto](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep303.png)

## Columnas y líneas

En un gráfico superpuesto, los datos pueden mostrarse mediante columnas, barras apiladas y líneas.

Para seleccionar columnas o líneas para el gráfico base, seleccione la pestaña **Superposición** y seleccione una opción. Las columnas pueden ser una barra separada para cada valor o apiladas.

## Cortadoras

Las rebanadoras se aplican tanto a los gráficos superpuestos como a los demás tipos de gráficos.

## Crear un gráfico superpuesto

1. En la pestaña **Informe**, haga clic en **Superponer**. Aparecerá el cuadro de diálogo **Configuración de componentes ad hoc**.
2. Haga clic en la pestaña **Superposición**.
3. Para añadir la primera serie de datos, haga clic en **Editar capa base**.
4. Para definir las etiquetas que aparecen en el eje x, arrastre un campo al área **Eje**.
5. Para definir el elemento que se representará gráficamente, arrastre un campo al área **Valores**.
6. Dé formato a los datos mostrados haciendo clic en una opción de Visualización de capas.
7. Para añadir la segunda serie de datos, haga clic en Editar Capa 1 y repita los pasos 4-6 anteriores.
8. Si necesita simplificar el gráfico, añada un filtro.

Ahora el gráfico debería estar completo.

## Ordenar

Puede ordenar los datos utilizando sólo la capa base.

1. Haga clic en **Editar capa base**.
2. Haga clic en **Ordenar**.

## Navegar (Drill)

La navegación se realiza mediante la opción **Taladro**.

## Activar la navegación

Activa los elementos del gráfico como enlaces para la navegación.

## Utilización por brocas métricas

Cuando se activa la navegación, los segmentos circulares y las barras de los gráficos de barras están disponibles para el desglose.

Al marcar la opción **Utilizar desgloses por métricas** se activa el desglose de las cifras que aparecen en los sectores circulares y en las barras de los diagramas de barras.

## Navegar

Introduzca el nombre de un informe personalizado para desglosarlo. El informe debe ser hijo del informe actual. Si se rellena este campo, todos los enlaces no métricos del gráfico llevarán al informe designado.
