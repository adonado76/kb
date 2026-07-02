---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Asignar valor en un modelo"
breadcrumb: []
source_path: "studio/model_studio/allocate-value-in-model.html"
images:
  - "resources/images/studio_images/studioimages/studio/stu573.png"
  - "resources/images/studio_images/studioimages/studio/stu578.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Asignar valor en un modelo

**Se aplica a** : TBM Studio 12.0 y posteriores

Una de las características más potentes de TBM Studio son los esquemas de asignación utilizados para modelizar el flujo de dinero y otras métricas de una tabla de un modelo a otras tablas. Los modelos permiten relacionar gastos, activos y mano de obra con aplicaciones, plataformas y transacciones. El resultado es una información estadística y de costes detallada para TI y las unidades de negocio a las que presta servicio.

## Diagrama de Sankey

Las asignaciones se muestran en un diagrama de Sankey como el de la siguiente imagen. La anchura de las líneas de asignación en el diagrama es proporcional al valor.

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu573.png)

## Tablas y asignaciones

En un modelo, una tabla contiene datos asociados a un elemento de la organización. Algunos ejemplos son los servidores, las redes, el libro mayor, las instalaciones, los centros de datos, el correo electrónico, SAP y las unidades de negocio. Una tabla agrupa los datos para su análisis. En un modelo, las tablas se muestran como rectángulos. En el modelo de costes mostrado en la imagen anterior, la tabla **Cost Source Actuals** es la tabla fuente. Deriva su valor de los controladores de dos unidades basados en columnas de la tabla **Cost Source Actuals** : **OpEx Variable** y **OpEx Fijo**. Asigna valor a tres tablas de destino: **Datos reales de mano de obra**, **Datos reales de instalaciones** y **Datos reales de activos fijos**. Las tablas de destino podrían entonces asignar su valor a otras tablas, como se muestra en la siguiente imagen:

![](../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/studioimages/studio/stu578.png)

Asignar valor:

1. Comprueba las tablas de origen y destino.
2. Haga clic en la tabla de origen en el **Explorador de proyectos**.
3. Haga clic en el paso **Modelo** del proceso de transformación.
4. En el diagrama de Sankey, haga clic en **Añadir asignación** bajo el encabezado **Asignaciones**.
5. Si hay más de una métrica, en la sección **Asignar** haga clic en las métricas a las que se aplicará la asignación.
6. En la sección **Utilización**, seleccione el tipo de asignación (véase [Tipos de asignación](#Allocatevalueinamodel__Allocationtypes) para una descripción de cada uno).
7. En la sección **Para**, seleccione la tabla de destino.
8. Según el tipo de asignación, complete la información restante.

## Tipos de asignación

Existen cinco tipos de asignaciones: **Valor ponderado**, **Consumo**, **Valor estándar**, **Fórmula** y **Recursión**. Cada tipo de asignación se describe en los subtemas siguientes.

- [Asignaciones de valor ponderado](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-weighted-value-allocations "(se abre en una pestaña o una ventana nueva)")
- [Asignaciones de consumo](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-consumption-allocations "(se abre en una pestaña o una ventana nueva)")
- [Asignaciones de valor estándar](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-standard-value-allocations "(se abre en una pestaña o una ventana nueva)")
- [Asignaciones basadas en fórmulas](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-formula-allocations "(se abre en una pestaña o una ventana nueva)")
- [Asignaciones de recursión](https://www.ibm.com/docs/en/apptio-commercial/tbm-studio/saas?topic=metrics-recursion-allocations "(se abre en una pestaña o una ventana nueva)")
