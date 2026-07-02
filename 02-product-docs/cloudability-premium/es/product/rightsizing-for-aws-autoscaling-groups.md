---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "AWS EC2 Grupo de autoescalado (ASG)"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/rightsizing-for-aws-autoscaling-groups.html"
images:
  - "images/edit-icon.jpg"
  - "images/recommendations-aws-autoscaling.jpg"
  - "images/rightsizing-aws-ec2_asg_dashboard.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# AWS EC2 Grupo de autoescalado (ASG)

Puede utilizar el Rightsizing dashboard para ver las recomendaciones de optimización de recursos para Amazon Web Services ( AWS ) Elastic Compute Cloud ( EC2 ) Auto Scaling Groups (ASG). El cuadro de mandos muestra tanto las recomendaciones de ampliación como las de inactividad (finalización). Puede ver las recomendaciones en varias cuentas desde un único panel de control.

[Redimensionamiento en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

[Acción de autoescalado para redimensionamiento](rightsizing-autoscale-action.html)

Antes de empezar

Para ver el panel de control de ASG de AWS EC2, asegúrese de que se cumplan los siguientes requisitos:

Ha conectado Cloudability a las cuentas AWS correctas.

Está utilizando AWS AutoScaling Grupos.

La etiqueta aws:autoscaling:groupName está incluida en los archivos del Informe de Costes y Usos (CUR) proporcionados a Apptio y los archivos actualizados han sido ingestados.

[Conexión con AWS - Guía de integración de clientes](../admin/aws-credentialing-standard-enterprise-home.html)

Nota:

Actualmente, esta función tiene la siguiente limitación:

- Las recomendaciones excluyen los casos puntuales. El panel de control sólo muestra instancias bajo demanda.

Acceda al panel de control ASG de AWS EC2.

Para acceder al panel de control de ASG de AWS EC2, abra la página de inicio de Cloudability y, en el menú de navegación de la izquierda, seleccione Optimizar > Redimensionar. En la página Rightsizing, seleccione la pestaña AWS y, a continuación, seleccione la subpestaña EC2 ASG.

![aws ec2 asg dashboard captura de pantalla](../../../../03-media/cloudability-premium/images/rightsizing-aws-ec2_asg_dashboard.jpg)

Personalizar el salpicadero

Puedes configurar las siguientes opciones para personalizar tu panel de control.

Especifique la base de costes

La base de costes determina cómo se calculan las recomendaciones. La base de costes puede ser a la carta o efectiva. Por defecto se selecciona la base de costes A la carta.

Nota:

[Consulte](../chatbot/custom-discounts-enterprise-discount.html) para saber más.

- Bajo Demanda: La base de costes Bajo Demanda proporciona una comparación directa entre la instancia listada en la columna Actual y la instancia recomendada en la columna Nueva basada puramente en Precios Bajo Demanda. No incluye ningún impacto potencial de las Instancias Reservadas (IR) ni de los Planes de Ahorro (PA). Tenga en cuenta que los precios a la carta reflejarán cualquier acuerdo de precios personalizado que haya configurado en Cloudability.
- Efectivo: La base de coste Efectivo tiene en cuenta el impacto histórico de las Instancias Reservadas (IR) y los Planes de Ahorro (PE) para calcular el coste del tipo de instancia actual durante el periodo del informe. Al igual que la métrica Coste (amortizado), incluye todos los costes iniciales y recurrentes asociados.   
   En otras palabras, la base de coste efectivo muestra el coste efectivo de funcionamiento de su instancia actual. Las cifras de coste para el tipo de instancia recomendada Nuevo se basan en los precios bajo demanda. Esto se debe a que la nueva configuración puede no beneficiarse de los RI o los SP. Esta comparación es la opción más conservadora. Incluso si se aleja inadvertidamente de los RI o los SP, su nueva tarifa global seguirá siendo mejor. En consecuencia, el ahorro global notificado con esta metodología será a veces inferior. Se aplicarán precios personalizados a estas cifras, si procede.

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

1. Seleccione el icono de filtro ![icono de edición](../../../../03-media/cloudability-premium/images/edit-icon.jpg) .
2. Seleccione X junto al filtro que desea eliminar.

Indicadores clave de rendimiento

Puede ver los siguientes Indicadores Clave de Rendimiento (KPI) en su panel de Rightsizing:

- Total de gastos : Muestra el total de gastos asignados actuales.
- Ahorro estimado en inactividad : Muestra el ahorro total estimado para todas las recomendaciones de Terminar.
- Ahorro estimado de Rightsize : muestra el ahorro potencial total estimado que se puede lograr con todas las recomendaciones de Rightsize.
- Gasto optimizado estimado : Muestra el gasto total estimado después de aplicar las recomendaciones.

Nota:

En EC2, los gastos vienen determinados por el uso de las instancias.

Tabla de recomendaciones de redimensionamiento

El panel de control contiene una tabla de recomendaciones de dimensionamiento, que proporciona una visión general de todos sus recursos ASG de EC2. La tabla incluye las siguientes columnas:

Nota:

Por defecto, los datos se ordenan por la columna Ahorro de costes. Para cambiar el orden de clasificación, sólo tiene que seleccionar el nombre de la columna.

- ID del recurso: El ID de la cuenta más el nombre del ASG.
- Nombre del recurso : El nombre del ASG.
- Nombre de la cuenta : El nombre de la cuenta AWS.
- Fuente de datos : La fuente o APM (como Cloudwatch) que proporciona los datos.
- Min Instance Count : El número mínimo de instancias observadas.
- Max Instance Count : El número máximo de instancias observadas.
- Idle : El tiempo que pasa por debajo del 2% de CPU en una escala de 1-100.
- Coste : El coste total de todas las instancias en ejecución en el ASG.
- Current : El tipo de instancia ASG. En el caso de los ASG con varios tipos, la columna mostrará varios.
- Nuevo : El tipo de instancia ASG más recomendado.
- Acción : Recomendación para el recurso. La recomendación puede ser una de las siguientes

| Recomendación | Descripción |
| --- | --- |
| Terminar | Dar de baja su recurso porque está predominantemente ocioso. |
| Autoescala | Configura el autoescalado para el recurso. |
| Ninguna acción | Por defecto no se recomienda ninguna acción, pero en el panel de detalles puede haber recomendaciones adicionales con niveles de riesgo más altos. |

Ahorro de costes : Importe estimado del ahorro de costes a 10 o 30 días.

Exportar recomendaciones a un archivo Excel

Para exportar las recomendaciones a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otros.

Detalles de la recomendación

Para ver los detalles de la recomendación de un recurso concreto, seleccione Ver detalles en el menú Más opciones (3 puntos).

La siguiente figura muestra un panel de detalles de la recomendación.

![pantalla de detalles de la recomendación](../../../../03-media/cloudability-premium/images/recommendations-aws-autoscaling.jpg)

Además de la información proporcionada en el panel de detalles EC2, el panel de detalles ASG muestra la siguiente información:

Recuento de instancias : El recuento de instancias mínimo y máximo observado.

Acción (Autoescalado) : Cuando la acción recomendada para un ASG es Autoescalado, la configuración mínima y máxima recomendada del recuento de instancias se muestra entre paréntesis junto al texto. Para obtener más información sobre cómo se utilizan las recomendaciones de autoescalado, consulta «[Acción de](rightsizing-autoscale-action.html) autoescalado para el redimensionamiento adecuado».

Riesgo : Caracteriza la probabilidad de alcanzar los límites de capacidad para una recomendación dada, basada en el escalado a un mayor número de instancias con menor capacidad individual.

Métricas de utilización : Las métricas de utilización mostradas para los ASG se basan en los siguientes parámetros:

| Parámetro | Descripción |
| --- | --- |
| Total CPU (%) | - CPU Total (línea azul) : El porcentaje normalizado de utilización máxima de la CPU en la hora indicada, basado en el recuento máximo de instancias para todo el ASG en la ventana temporal de 10 o 30 días. - Por ejemplo, si un ASG contiene 5 instancias y las 5 instancias utilizan el 100% de CPU, entonces el Total de CPU (%) mostrará 100%. Si 1 instancia utilizó el 100% de la CPU, mientras que las otras 4 instancias utilizaron el 0% de la CPU, entonces el Total de CPU (%) mostrará el 20%. - Recuento de instancias (línea roja) : El número total de instancias en ejecución para este ASG en la hora indicada. - Recomendado (línea discontinua amarilla) : El porcentaje normalizado recomendado de asignación de uso de CPU para todo el ASG en la hora indicada. - Recuento de instancias recomendadas (línea amarilla, se muestra al pasar el ratón por encima) : El número total de instancias recomendadas para este ASG en la hora indicada. |
| Red Total (Bits/s) | - Total de la red (línea azul) : El número total de bits por segundo utilizados basado en el recuento máximo de instancias para todo el ASG en la hora indicada. - Recuento de instancias (línea roja) : El número total de instancias en ejecución para este ASG en la hora indicada. - Recomendada (línea discontinua amarilla) : La asignación de red recomendada para todo el ASG en la hora indicada. - Recuento de instancias recomendadas (línea amarilla, se muestra al pasar el ratón por encima) : El número total de instancias recomendadas para este ASG en la hora indicada. |
| Memoria Total (%) | - Memoria total (línea azul) : El porcentaje normalizado de utilización máxima de memoria en la hora indicada, basado en el recuento máximo de instancias para todo el ASG en la ventana temporal de 10 o 30 días. - Por ejemplo, si un ASG contiene 5 instancias y las 5 instancias utilizan el 100% de memoria, entonces Memoria Total (%) mostrará 100%. Si 1 instancia utiliza el 100% de memoria, mientras que las otras 4 instancias utilizan el 0% de memoria, entonces Memoria Total (%) mostrará el 20%. - Recuento de instancias (línea roja) : El número total de instancias en ejecución para este ASG en la hora indicada. - Recomendado (línea discontinua amarilla) : El porcentaje normalizado recomendado de asignación de utilización de memoria para todo el ASG en la hora indicada. - Recuento de instancias recomendadas (línea amarilla, se muestra al pasar el ratón por encima) : El número total de instancias recomendadas para este ASG en la hora indicada. |
| GPU Total (%) | - Total GPU (%): Esto se maneja de la misma manera que CPU Total (%). |
| Memoria GPU Total (%) | - Memoria GPU Total (%): Se gestiona de la misma manera que la memoria total de la CPU (%) |

Nota:

Las métricas de disco no se utilizan para las recomendaciones de autoescalado.

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
