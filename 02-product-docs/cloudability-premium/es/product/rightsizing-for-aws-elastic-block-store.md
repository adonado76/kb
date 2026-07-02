---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "AWS EBS"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-for-aws-elastic-block-store.html"
images:
  - "images/ebs-details-final.jpg"
  - "images/ebs-final.jpg"
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS EBS

Puede utilizar el Rightsizing dashboard para ver las recomendaciones de optimización de recursos para Amazon Web Services ( AWS ) Elastic Block Store ( EBS ). El cuadro de mandos muestra tanto las recomendaciones de ampliación como las de inactividad (finalización). Puede ver las recomendaciones en varias cuentas desde un único panel de control.

[Redimensionamiento en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

Antes de empezar

Para ver el panel de control de AWS EC2 EBS, asegúrese de haber conectado Cloudability a las cuentas correctas de AWS.

[Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-standard-enterprise-home.html)

Acceda al panel de control de AWS EC2 EBS.

Para acceder al panel de control de AWS EC2 EBS, abra la página de inicio de Cloudability y, en el menú de navegación de la izquierda, seleccione Optimizar > Redimensionar. En la página Rightsizing, seleccione la pestaña AWS y, a continuación, seleccione la subpestaña EBS.

![Captura de pantalla del panel de control de AWS EBS « ec2 »](../../../../03-media/cloudability-premium/images/ebs-final.jpg)

Personalizar el salpicadero

Puedes configurar las siguientes opciones para personalizar tu panel de control.

Nota:

Sólo se admite la base de costes a la carta para EBS.

La base de costos bajo demanda proporciona una comparación directa entre la instancia que aparece en la columna Actual y la instancia recomendada en la columna Nueva basándose únicamente en el precio bajo demanda. No incluye ningún impacto potencial de las Instancias Reservadas (IR) ni de los Planes de Ahorro (PA). Tenga en cuenta que los precios a la carta reflejarán cualquier acuerdo de precios personalizado que haya configurado en Cloudability.

Seleccionar cuenta

Por defecto, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones de una cuenta concreta, seleccione el nombre de la cuenta en el desplegable Cuenta.

Especifique el plazo

Puede elegir revisar los gastos de los últimos 10 días o de los últimos 30 días. Por defecto, la opción Plazo está fijada en 10 días. Para la mayoría de los usuarios, 10 días es el periodo de tiempo recomendado porque captura las tendencias de rendimiento más recientes y es más predictivo del uso futuro de los recursos.

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

1. Seleccione el icono de filtro ![Icono Notas](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Seleccione X junto al filtro que desea eliminar.

Indicadores clave de rendimiento

Puede ver los siguientes Indicadores Clave de Rendimiento (KPI) en su panel de Rightsizing:

- Total de gastos : Muestra el total de gastos asignados actuales.
- Ahorro estimado en inactividad : Muestra el ahorro total estimado para todas las recomendaciones de Terminar.
- Ahorro estimado por ajuste de tamaño : muestra el ahorro potencial total estimado que se puede lograr con todas las recomendaciones de ajuste de tamaño.
- Gasto optimizado estimado : Muestra el gasto total estimado después de aplicar las recomendaciones.

Tabla de recomendaciones de redimensionamiento

El cuadro de mandos contiene una tabla de recomendaciones de dimensionamiento, que ofrece una visión general de los recursos de EC2 EBS. La tabla incluye las siguientes columnas:

Nota:

Por defecto, los datos se ordenan por la columna Ahorro de costes. Para cambiar el orden de clasificación, sólo tiene que seleccionar el nombre de la columna.

- ID del recurso : El ID del volumen.
- Nombre del recurso : El nombre del volumen.
- Nombre de la cuenta : El nombre de la cuenta AWS.
- Idle : El porcentaje de horas con cero IOPS.
- Estado : El estado puede ser Attached, Unattached, o Deleted.
- Coste : Coste total del volumen.
- Tipo : Tipo de volumen.
- Tamaño : El tamaño del volumen (en GiB ).
- Nuevo tipo : El tipo de volumen más recomendado.
- Nuevo tipo : El tipo de volumen más recomendado.
- Nuevo tamaño : El tamaño de volumen más recomendado (en GiB ).
- Acción : Recomendación para el recurso. La recomendación puede ser una de las siguientes

| Recomendación | Descripción |
| --- | --- |
| Redimensionar | Cambia el tamaño al tipo de recurso especificado en la columna Nuevo. |
| Terminar | Dar de baja su recurso porque está predominantemente ocioso. |
| Ninguna acción | Por defecto no se recomienda ninguna acción, pero en el panel de detalles puede haber recomendaciones adicionales con niveles de riesgo más altos. |

Ahorro de costes : Importe estimado del ahorro de costes a 10 o 30 días.

Exportar recomendaciones a un archivo Excel

Para exportar las recomendaciones a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otros.

Detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, seleccione Ver detalles en el menú Más opciones (3 puntos).

La siguiente figura muestra un panel de detalles de la recomendación.

![Icono Notas](../../../../03-media/cloudability-premium/images/ebs-details-final.jpg)

El panel de detalles de EBS muestra la siguiente información:

- Última fecha de facturación : La última fecha para la que están disponibles los datos de costes.
- Last Attached Date : La última fecha en la que se adjuntó el estado del volumen.
- Último ID adjunto : El último ID de instancia al que se adjuntó el volumen.
- Tipo : El tipo de volumen.
- Tamaño : El tamaño del volumen.
- Rendimiento : El rendimiento máximo de volumen.
- IOPS : El volumen máximo de IOPS.
- Riesgo (bajo recomendaciones) : Caracteriza la probabilidad de alcanzar los límites de capacidad para una recomendación determinada.
- Métricas de utilización : Las métricas de utilización mostradas para los volúmenes de EBS se basan en los siguientes parámetros.

| Parámetro | Descripción |
| --- | --- |
| Rendimiento (MB/S) | Throughput Max (línea azul) : El máximo MB/S de throughput utilizado en la hora indicada.  Capacidad (línea roja) : La capacidad de caudal en MB/S en la hora indicada.  Recomendado (línea discontinua amarilla) : La capacidad de caudal recomendada en MB/S en la hora indicada. |
| IOPS (recuento) | IOPS Max (línea azul) : El máximo de IOPS utilizadas en la hora indicada.  Capacidad (línea roja) : La capacidad de IOPS en la hora indicada.  Recomendado (línea discontinua amarilla) : La capacidad de IOPS recomendada en la hora indicada. |

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
