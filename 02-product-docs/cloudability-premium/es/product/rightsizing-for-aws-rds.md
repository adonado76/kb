---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "AWS RDS"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-for-aws-rds.html"
images:
  - "images/aws-rds-dashboard.jpg"
  - "images/edit-icon.jpg"
  - "images/rightsizing-aws-rds.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS RDS

Puede utilizar el Rightsizing dashboard para ver las recomendaciones de optimización de recursos para Amazon Web Services ( AWS ) Relational Database Service ( RDS ). El cuadro de mandos muestra tanto las recomendaciones de ampliación como las de inactividad (finalización). Puede ver las recomendaciones en varias cuentas desde un único panel de control.

[Redimensionamiento en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Antes de empezar

Para ver el panel de control de AWS RDS, asegúrese de haber conectado Cloudability a las cuentas correctas de AWS.

[Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-standard-enterprise-home.html)

Acceda al panel de control de AWS RDS.

Para acceder al panel de control de AWS RDS, abra la página de inicio de Cloudability y, en el menú de navegación de la izquierda, seleccione Optimizar > Redimensionar. En la página Rightsizing, seleccione la pestaña AWS y, a continuación, seleccione la subpestaña RDS.

![AWS RDS captura de pantalla](../../../../03-media/cloudability-premium/images/aws-rds-dashboard.jpg)

Personalizar el salpicadero

Puedes configurar las siguientes opciones para personalizar tu panel de control.

Especifique la base de costes

La base de costes determina cómo se calculan las recomendaciones. La base de costes puede ser a la carta o efectiva. Por defecto se selecciona la base de costes A la carta.

Nota:

Si su organización ha activado la fijación de precios personalizada en Cloudability, las tarifas personalizadas pertinentes se aplicarán a los cálculos de la base de costes.

- Bajo Demanda : La base de costes Bajo Demanda proporciona una comparación directa entre la instancia listada en la columna Actual y la instancia recomendada en la columna Nueva basada puramente en Precios Bajo Demanda. No incluye ningún impacto potencial de las Instancias Reservadas (IR) ni de los Planes de Ahorro (PA). Tenga en cuenta que los precios a la carta reflejarán cualquier acuerdo de precios personalizado que haya configurado en Cloudability.
- Efectivo : La base de coste Efectivo tiene en cuenta el impacto histórico de las Instancias Reservadas (IR) y los Planes de Ahorro (PE) para calcular el coste del tipo de instancia actual durante el periodo del informe. Al igual que la métrica Coste (amortizado), incluye todos los costes iniciales y recurrentes asociados.   
   En otras palabras, la base de coste efectivo muestra el coste efectivo de funcionamiento de su instancia actual. Las cifras de coste del nuevo tipo de instancia recomendado se basan en los precios a la carta. Esto se debe a que la nueva configuración puede no beneficiarse de los RI o los SP. Esta comparación es la opción más conservadora. Incluso si se aleja inadvertidamente de los RI o los SP, su nueva tarifa global seguirá siendo mejor. En consecuencia, el ahorro global notificado con esta metodología será a veces inferior. Se aplicarán precios personalizados a estas cifras, si procede.

Nota:

Utilice la base de costes a la carta si desea eliminar de su análisis la naturaleza impredecible de los descuentos basados en compromisos y maximizar el número de recomendaciones que se le proporcionan. Utilice la base Coste efectivo si prefiere basar sus recomendaciones en el Coste real histórico del funcionamiento de sus instancias y adoptar un enfoque conservador.

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

- Seleccione el icono de filtro ![icono de edición](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
- Seleccione X junto al filtro que desea eliminar.

Indicadores clave de rendimiento

Puede ver los siguientes Indicadores Clave de Rendimiento (KPI) en su panel de Rightsizing:

- Total de gastos : Muestra el total de gastos asignados actuales.
- Ahorro estimado por inactividad : Muestra el ahorro total estimado para todas las recomendaciones de Terminar.
- Ahorro estimado de Rightsize : Muestra el ahorro potencial total estimado que se puede conseguir con todas las recomendaciones de Rightsize.
- Gasto optimizado estimado : Muestra el gasto total estimado después de aplicar las recomendaciones.

Tabla de recomendaciones de redimensionamiento

El cuadro de mandos contiene una tabla de recomendaciones de dimensionamiento, que ofrece una visión general de los recursos de RDS para los que se han identificado recomendaciones. La tabla incluye las siguientes columnas:

Nota:

Por defecto, los datos se ordenan por la columna Ahorro de costes. Para cambiar el orden de clasificación, sólo tiene que seleccionar el nombre de la columna.

- ID de cluster : El ID del clúster.
- Nombre del recurso : El nombre de la instancia.
- Motor : El motor de la base de datos.
- Rol : El papel de IAM.
- Nombre de cuenta : El nombre de la cuenta AWS.
- En reposo : Basado en el número de conexiones/sesiones activas de la base de datos en un momento dado.
- Coste : El coste total de la instancia.
- Actual : El tipo de instancia actual.
- Nuevo : El tipo de instancia más recomendado.
- Acción : Recomendación para el recurso. La recomendación puede ser una de las siguientes

| Recomendación | Descripción |
| --- | --- |
| Dimensionar correctamente | Cambia el tamaño al tipo de recurso especificado en la columna Nuevo. |
| Terminar | Dar de baja su recurso porque está predominantemente ocioso. |
| Ninguna acción | Por defecto no se recomienda ninguna acción, pero en el panel de detalles puede haber recomendaciones adicionales con niveles de riesgo más altos. |

Ahorro de costes : Importe estimado del ahorro de costes a 10 o 30 días.

Exportar recomendaciones a un archivo Excel

Para exportar las recomendaciones a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otros.

Detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, seleccione Ver detalles en el menú Más opciones (3 puntos).

La siguiente figura muestra un panel de detalles de la recomendación.

![AWS RDS Detalles de la recomendación: captura de pantalla](../../../../03-media/cloudability-premium/images/rightsizing-aws-rds.jpg)

Para ver descripciones de las dimensiones y métricas de costos, consulte [Glosario de dimensiones y métricas de costos](glossary-of-cost-dimensions-and-metrics.html).

Para ver los detalles de la dimensión y las métricas de utilización, consulte [el Glosario de dimensiones y métricas de utilización](glossary-of-utilization-dimensions-and-metrics.html).

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
