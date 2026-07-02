---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "GCP Google Compute Engine (GCE) Grupos de instancias gestionadas (MIG)"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-for-gcp-gce-mig.html"
images:
  - "images/edit-icon.jpg"
  - "images/mig-help-image-2.jpg"
  - "images/mig-help-image2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GCP Google Compute Engine (GCE) Grupos de instancias gestionadas (MIG)

Puede utilizar el panel de control de ajuste de tamaño para ver las recomendaciones de optimización de recursos para los grupos de instancias administradas (MIG) Google Cloud Platform ( GCP ) Google Compute Engine (GCE). El cuadro de mandos muestra tanto las recomendaciones de ampliación como las de inactividad (finalización). Puede ver las recomendaciones en varias cuentas desde un único panel de control.

Más información sobre [el redimensionamiento en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Más información sobre [Autoscale Action for Rightsizing](rightsizing-autoscale-action.html)

Antes de empezar

Para ver el panel de control de GCE MIG de GCP, asegúrese de que se cumplan los siguientes requisitos:

- Has conectado Cloudability a las cuentas correctas de GCP.
- Está utilizando grupos de instancias administradas de GCP.

Más información sobre [Connect Google Cloud](../admin/connect-google-cloud.html)

Nota:

Actualmente, esta función tiene las siguientes limitaciones:

- Las recomendaciones MIG de la CME no están disponibles para los tipos de instancia mixtos. El cuadro de mandos muestra estos MIG sin recomendaciones aplicables.
- Las recomendaciones excluyen los casos puntuales. El panel de control sólo muestra instancias bajo demanda.

Acceda al panel de control GCE MIG de GCP.

Para acceder al panel de control de GCE MIG de GCP, abra la página de inicio de Cloudability y, en el menú de navegación de la izquierda, seleccione Optimizar > Ajustar el tamaño. En la página Rightsizing, seleccione la pestaña GCP y, a continuación, seleccione la subpestaña GCE MIG. ![gcp gce mig dashboard captura de pantalla](../../../../03-media/cloudability-premium/images/mig-help-image-2.jpg)

Personalizar el salpicadero

Puedes configurar las siguientes opciones para personalizar tu panel de control.

Especifique la base de costes

La base de costes determina cómo se calculan las recomendaciones. La base de costes puede ser a la carta o efectiva. Por defecto se selecciona la base de costes A la carta.

Nota:

Si su organización ha activado la fijación de precios personalizada en Cloudability, las tarifas personalizadas pertinentes se aplicarán a los cálculos de la base de costes.

- **Bajo Demanda** : La base de coste Bajo Demanda proporciona una comparación directa entre la instancia listada en la columna Actual y la instancia recomendada en la columna **Nueva** basada puramente en **Precios Bajo Demanda**. No incluye ningún impacto potencial de las Instancias Reservadas (IR) ni de los Planes de Ahorro (PA). Tenga en cuenta que los precios a la carta reflejarán cualquier acuerdo de precios personalizado que haya configurado en Cloudability
- **Efectivo** : La base de coste Efectivo tiene en cuenta el impacto histórico de las Instancias Reservadas (IR) y los Planes de Ahorro (PE) para calcular el coste del tipo de instancia actual durante el periodo del informe. Al igual que la métrica Coste (amortizado), incluye todos los costes iniciales y recurrentes asociados.

  n otras palabras, la base de coste efectivo muestra el coste efectivo de funcionamiento de su instancia actual. Las cifras de coste del nuevo tipo de instancia recomendado se basan en los precios a la carta. Esto se debe a que la nueva configuración puede no beneficiarse de los RI o los SP. Esta comparación es la opción más conservadora. Incluso si se aleja inadvertidamente de los RI o los SP, su nueva tarifa global seguirá siendo mejor. En consecuencia, el ahorro global notificado con esta metodología será a veces inferior. Se aplicarán precios personalizados a estas cifras, si procede.

Nota:

Utilice la base de costes a la carta si desea eliminar de su análisis la naturaleza impredecible de los descuentos basados en compromisos y maximizar el número de recomendaciones que se le proporcionan. Utilice la base Coste efectivo si prefiere basar sus recomendaciones en el Coste real histórico del funcionamiento de sus instancias y adoptar un enfoque conservador.

Seleccionar cuenta

Por defecto, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones de una cuenta concreta, seleccione el nombre de la cuenta en el desplegable Cuenta.

Especifique el plazo

Puede elegir entre revisar los gastos de los últimos 10 días o de los últimos 30 días. Por defecto, la opción Plazo está fijada en 10 días. Para la mayoría de los usuarios, 10 días es el periodo de tiempo recomendado porque captura las tendencias de rendimiento más recientes y es más predictivo del uso futuro de los recursos.

Aplicar opciones

También puede establecer opciones a nivel de página para incluir o excluir determinadas recomendaciones.

Aplicar filtros

Puede añadir filtros para incluir o excluir datos en función de una o varias condiciones.

Añadir un filtro

Para añadir un filtro:

1. Seleccione Añadir filtro en la barra de herramientas.
2. En el menú Añadir filtro, elija una dimensión.
3. Seleccione un Operador para proporcionar una condición lógica.
4. Elija un valor para afinar el filtro.
5. Seleccione Añadir filtro para aplicar el nuevo filtro a la página.

Seleccione el icono de filtro ![icono de edición](../../../../03-media/cloudability-premium/images/edit-icon.jpg) que aparece al pasar el ratón por encima de Filtros.

Aplicar filtros con enlaces

También puede añadir filtros seleccionando los valores hipervinculados en azul en la tabla principal. La regla de filtrado se aplica automáticamente al campo Filtros. Sólo puede seleccionar un valor o parámetro de cada columna a la vez.

Eliminar un filtro

Para quitar un filtro:

1. Seleccione el icono de filtro ![icono de edición](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. Seleccione X junto al filtro que desea eliminar.

Indicadores clave de rendimiento

Puede ver los siguientes Indicadores Clave de Rendimiento (KPI) en su panel de Rightsizing:

- **Total de gastos** : Muestra el total de gastos asignados actuales.
- **Ahorro estimado por inactividad** : Muestra el ahorro total estimado para todas las recomendaciones de **Terminar**.
- **Ahorro estimado de Rightsize** : Muestra el ahorro potencial total estimado que se puede conseguir con todas las recomendaciones de **Rightsize**.
- **Gastos optimizados estim** ados: Muestra el gasto total estimado después de aplicar las recomendaciones.

Nota:

Para la CME, los gastos se determinan en función de la utilización de las instancias.

Tabla de recomendaciones de redimensionamiento

El panel contiene una tabla de recomendaciones de dimensionamiento, que ofrece una visión general de todos sus recursos MIG de la CME. La tabla incluye las siguientes columnas:

Nota:

Por defecto, los datos se ordenan por la columna Ahorro de costes. Para cambiar el orden de clasificación, sólo tiene que seleccionar el nombre de la columna.

- Nombre del recurso: El nombre del recurso MIG.
- Nombre de cuenta: El nombre de la cuenta MIG
- Región : La región MIG.
- Fuente de datos: La fuente o APM que proporciona los datos.
- Número mínimo de instancias : El número mínimo de instancias observadas.
- Número máximo de instancias: El número máximo de instancias observadas.
- Ralentí: El tiempo pasado por debajo del 2% de CPU en una escala de 1-100.
- Coste: El coste total de todas las instancias en ejecución en el MIG
- Actual: El tipo de recurso MIG actual. (para MIG de tipo único)
- Nuevo: El tipo de recurso MIG más recomendado.
- Acción: Recomendación para el recurso. La recomendación puede ser una de las siguientes

  | Recomendación | Descripción |
  | --- | --- |
  | Terminar | Dar de baja su recurso porque está predominantemente ocioso. |
  | Autoescala | Configura el autoescalado para el recurso. |
  | Ninguna acción | Por defecto no se recomienda ninguna acción, pero en el panel de detalles puede haber recomendaciones adicionales con niveles de riesgo más altos. |
- Ahorro de costes : Importe estimado del ahorro de costes a 10 o 30 días.

Exportar recomendaciones a un archivo Excel

Para exportar las recomendaciones a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otros.

Detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, seleccione Ver detalles en el menú Más opciones (3 puntos).

La siguiente figura muestra un panel de detalles de la recomendación. ![Detalles de la recomendación de migración de GCP a GCE](../../../../03-media/cloudability-premium/images/mig-help-image2.jpg)

Además de la información proporcionada en el panel de detalles CME, el panel de detalles MIG muestra la siguiente información:

- **Recuento de instancias** : El recuento de instancias mínimo y máximo observado
- **Acción (Autoescala)** : Cuando la acción recomendada para un MIG es **Autoescalado**, la configuración de recuento de instancias mínima y máxima recomendada se muestra entre paréntesis junto al texto. Para obtener más información sobre cómo se utilizan las recomendaciones de autoescalado, consulta «[Acción de](rightsizing-autoscale-action.html) autoescalado para el redimensionamiento adecuado».
- **Riesgo** : Caracteriza la probabilidad de alcanzar los límites de capacidad para una recomendación dada, basándose en el escalado a un mayor número de instancias con menor capacidad individual.

Nota:

- Las métricas de disco no se utilizan para las recomendaciones de autoescalado.
- En el caso de los MIG basados en GPU, sólo se admiten los MIG homogéneos basados en máquinas a2.

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
