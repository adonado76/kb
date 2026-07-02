---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "GCP Google Disco persistente (GPD)"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-for-gpd.html"
images:
  - "images/edit-icon.jpg"
  - "images/rightsizing-gcp-gpd-details.jpg"
  - "images/rightsizing-gcp-gpd.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Google Disco persistente (GPD)

Puede utilizar el Rightsizing dashboard para ver las recomendaciones de optimización de recursos para Google Persistent Disk (GPD) resources. El cuadro de mandos muestra las recomendaciones de redimensionamiento, finalización y no actuación.

[Redimensionamiento en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Antes de empezar

Para ver el cuadro de mandos GPD, asegúrese de que se cumplen los siguientes requisitos:

Habilite los permisos correctos. Vaya a Configuración > Credenciales de proveedores > GCP y asegúrese de que la columna Funciones avanzadas tenga una marca de verificación verde para cada proyecto.

Instale el [agente Cloud Monitoring](https://cloud.google.com/compute/docs/instances/apply-sizing-recommendations-for-instances?_ga=2.131490120.-69202228.1597361838#using_the_monitoring_agent_for_more_precise_recommendations "(se abre en una pestaña o una ventana nueva)") para mejorar la calidad de las recomendaciones. Esto es opcional pero recomendable.

Acceder al salpicadero de GPD

Para acceder al panel de control de GPD, abra la página de inicio Cloudability y, en el menú de navegación de la izquierda, seleccione Optimizar > Redimensionamiento. En la página Rightsizing, seleccione la pestaña GCP y, a continuación, seleccione la subpestaña GPD para ver las recomendaciones para un disco persistente Google.

![captura de pantalla del cuadro de mandos de gpd](../../../../03-media/cloudability-premium/images/rightsizing-gcp-gpd.jpg)

Personalizar el salpicadero

Puedes configurar las siguientes opciones para personalizar tu panel de control.

Todos los costes de GPD se muestran actualmente utilizando la Base de Costes a la Demanda.

La base de costos bajo demanda proporciona una comparación directa entre el recurso enumerado en la columna Actual y el recurso recomendado en la columna Nuevo basándose únicamente en el precio bajo demanda. No incluye ningún impacto potencial de los Descuentos por Uso Comprometido.

Seleccionar cuenta

Por defecto, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones de una cuenta concreta, seleccione el nombre de la cuenta en el desplegable Cuenta.

Especifique el plazo

Puede elegir entre revisar los gastos de los últimos 10 días o de los últimos 30 días. Por defecto, la opción Plazo está fijada en 10 días. Para la mayoría de los usuarios, 10 días es el periodo de tiempo recomendado porque captura las tendencias de rendimiento más recientes y es más predictivo del uso futuro de los recursos.

Aplicar filtros

Puede añadir filtros para incluir o excluir datos en función de una o varias condiciones.

Añadir un filtro

Para añadir un filtro:

1. Seleccione Añadir filtro en la barra de herramientas.
2. En el menú Añadir filtro, elija una dimensión.
3. Seleccione un Operador para proporcionar una condición lógica.
4. Elija un valor para afinar el filtro.
5. Seleccione Añadir filtro para aplicar el nuevo filtro a la página.

Aplicar filtros con enlaces

También puede añadir filtros seleccionando los valores hipervinculados en azul en la tabla principal. La regla de filtrado se aplica automáticamente al campo Filtros. Sólo puede seleccionar un valor o parámetro de cada columna a la vez.

Eliminar un filtro

Para quitar un filtro:

1. Seleccione el icono de filtro ![icono de edición](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. Seleccione X junto al filtro que desea eliminar.

Indicadores clave de rendimiento

Puede ver los siguientes Indicadores Clave de Rendimiento (KPI) en su panel de Rightsizing:

- Total de gastos: Muestra el total de gastos asignados actuales.
- Ahorro estimado por inactividad : Muestra el ahorro total estimado para todas las recomendaciones de Terminar
- Ahorro estimado de Rightsize : Muestra el ahorro potencial total estimado que se puede conseguir con todas las recomendaciones de Rightsize.
- Gastos optimizados estim ados: Muestra el gasto total estimado después de aplicar las recomendaciones.

Tabla de recomendaciones de redimensionamiento

El cuadro de mandos contiene una tabla de recomendaciones de dimensionamiento, que proporciona una visión general de sus recursos GPD. La tabla incluye las siguientes columnas:

Nota:

Por defecto, los datos se ordenan por la columna Ahorro de costes. Para cambiar el orden de clasificación, sólo tiene que seleccionar el nombre de la columna.

- ID del recurso : ID del recurso.
- Nombre del recurso : El nombre del recurso GPD.
- Nombre de la cuenta : El nombre de la cuenta GPD.
- Fuente de datos : La fuente de datos de la CME.
- Idle : El porcentaje de horas con cero IOPS.
- Estado : El estado puede ser Adjunto, No Adjunto o Eliminado.
- Coste : Coste total del recurso CME para el calendario seleccionado.
- Tipo :Tipo de recurso GPD actual.
- Tamaño :El tipo de recurso GPD actual.
- Nuevo tipo : El tipo de recurso GPD más recomendado.
- Nuevo tamaño : El tamaño de recurso GPD más recomendado (en GiB ).
- Acción : Recomendación para el recurso. La recomendación puede ser una de las siguientes

  | Recomendación | Descripción |
  | --- | --- |
  | Redimensionar | Cambia el tamaño al tipo de recurso especificado en la columna Nuevo. |
  | Terminar | Dar de baja su recurso porque está predominantemente ocioso. |
  | Ninguna acción | Por defecto no se recomienda ninguna acción, pero en el panel de detalles puede haber recomendaciones adicionales con niveles de riesgo más altos. |
- Ahorro de costes : La cantidad estimada de ahorro de costes a 10 o 30 días.

Exportar recomendaciones a un archivo Excel

Para exportar las recomendaciones a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otros.

Detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, seleccione Ver detalles en el menú Más opciones (3 puntos).

La siguiente figura muestra un panel de detalles de la recomendación.

![pantalla de detalles de la recomendación](../../../../03-media/cloudability-premium/images/rightsizing-gcp-gpd-details.jpg)

Para ver descripciones de las dimensiones y métricas de costos, consulte [Glosario de dimensiones y métricas de costos](glossary-of-cost-dimensions-and-metrics.html).

Para ver los detalles de la dimensión y las métricas de utilización, consulte [el Glosario de dimensiones y métricas de utilización](glossary-of-utilization-dimensions-and-metrics.html).

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
