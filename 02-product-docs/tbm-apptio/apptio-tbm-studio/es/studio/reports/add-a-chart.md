---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir un gráfico"
breadcrumb: []
source_path: "studio/reports/add-a-chart.html"
images:
  - "resources/images/studio_images/studioimages/reports/rep199.png"
  - "resources/images/studio_images/studioimages/studio/stu521.png"
  - "resources/images/studio_images/studioimages/studio/stu522.png"
  - "resources/images/studio_images/studioimages/studio/stu524.png"
  - "resources/images/studio_images/studioimages/studio/stu525.png"
  - "resources/images/studio_images/studioimages/studio/stu618.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir un gráfico

**Se aplica a** : TBM Studio 12.0 y posteriores

Al añadir un gráfico por primera vez, el formato predeterminado es un gráfico de barras horizontales como el que se muestra en la siguiente imagen. Después de crear el gráfico inicial, puede cambiar el tipo de gráfico.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu521.png)

## Añadir un gráfico a un informe

1. Visualizar el informe.
2. En la pestaña **Informe**, haga clic en el icono **Gráfico**. El panel de **Configuración de Componentes Ad Hoc** aparece como se muestra en la siguiente imagen. Su aspecto variará en función de sus conjuntos de datos.

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu522.png)
3. Utilice el panel **Configuración de componentes ad hoc** para construir el gráfico.
4. Los gráficos se construyen abriendo las perspectivas **Tablas**, **Cálculos**, **Tiempo** y otras en el panel **Explorador de proyectos** y arrastrando los campos a las cuatro áreas del panel **Configuración de componentes**.

## Cambiar el tipo de gráfico

Por defecto, la aplicación construye un gráfico de barras horizontales. Puede cambiar el tipo de gráfico seleccionando el gráfico, seleccionando la pestaña **Ad Hoc** y, a continuación, seleccionando uno de los tipos de gráfico de la sección **Visualizar** que se muestra en la siguiente imagen:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu618.png)

## Etiquetas de los ejes X e Y acortadas

Las etiquetas que aparecen en los ejes x e y tienen una longitud máxima de 20 caracteres. Si una etiqueta supera esta longitud, se eliminan los caracteres de la mitad de la etiqueta. Por ejemplo, suponga que tiene la siguiente serie de etiquetas:

> aaaa bbbb cccc dddd eeee ffff 0001
>
> aaaa bbbb cccc dddd eeee ffff 0002
>
> aaaa bbbb cccc dddd eeee ffff 0003
>
> aaaa bbbb cccc dddd eeee ffff 0004
>
> aaaa bbbb cccc dddd eeee ffff 0005

Si los utiliza en un gráfico, aparecerán de la siguiente manera:

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/reports/rep199.png)

## Construir un gráfico de ejemplo

En este ejemplo, construiremos el gráfico de barras que se muestra en la siguiente imagen. Se basa en datos del Centro de Datos.

![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu524.png)

Para construir el gráfico:

1. Haga clic en **Gráfico** en la pestaña **Informe**.
2. En el panel **Configuración de componentes**, seleccione **Centros de datos** como tabla modelada.
3. Haga clic en la perspectiva **Tablas**, abra la tabla Centros de datos y arrastre **Centro de datos** al área **Leyenda**.
4. Haga clic en la perspectiva **Cálculos** y arrastre **Coste** al área **Valores**.
5. Seleccione la perspectiva **Tiempo** y arrastre Cuartos al área **Eje**. El cuadro de diálogo **Configuración de componentes ad hoc** debería parecerse ahora a la siguiente imagen:

   ![imagen](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu525.png)
6. Para cambiar a las barras verticales, seleccione la pestaña **Ad Hoc** y, a continuación, el icono **Columna**.
