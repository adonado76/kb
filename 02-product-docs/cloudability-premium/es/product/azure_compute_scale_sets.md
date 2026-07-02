---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Azure Conjuntos de escalabilidad informática"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto"
source_path: "product/azure_compute_scale_sets.html"
images:
  - "images/edit-icon.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure Conjuntos de escalabilidad informática

Puede utilizar el panel de control de Rightsizing para ver las recomendaciones de optimización de recursos para una máquina virtual de computación de Windows ( Microsoft Azure ) gestionada a través de conjuntos de escalado. El panel muestra recomendaciones de redimensionamiento y inactividad (terminación) tanto para conjuntos de escalas homogéneos como heterogéneos. Puede ver las recomendaciones de varias cuentas desde un único panel de control.

[Ajuste de plantilla en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

## Antes de empezar

Para ver el panel de control de Azure Compute, asegúrese de haber conectado Cloudability a las cuentas correctas de Azure.

[Conéctate a Microsoft Azure](../admin/azure-cm-setup.html)

## Acceda al panel de control de computación de Azure

Para acceder al panel de control de Azure Compute, abra la página de inicio de Cloudability y, en el menú de navegación de la izquierda, **sel** eccione Optimizar > Ajustar el tamaño. En **la** página Rightsizing, seleccione la **Azure** pestaña y, a continuación, seleccione la subpestaña **Comp** **ute Scale Sets**.

**Personalizar el panel de control**

Puede configurar las siguientes opciones para personalizar su panel de control.

**Especificar la base del coste**

La base de costes determina cómo se calculan las recomendaciones. La base de costos puede ser bajo demanda o efectiva . La base de costes bajo demanda se selecciona de forma predeterminada.

**Nota:**

Si su organización ha habilitado los precios personalizados en Cloudability, se aplicarán las tarifas personalizadas pertinentes a los cálculos de la base de costes.

- **Bajo demanda** : la base de costes bajo demanda proporciona una comparación directa entre la instancia que aparece en la columna Actual y la instancia recomendada en la columna Nueva, basándose únicamente en los precios bajo demanda. No incluye ningún impacto potencial de las instancias reservadas (RI) ni de los planes de ahorro (SP). Tenga en cuenta que los precios bajo demanda reflejarán cualquier acuerdo de precios personalizados que haya configurado en Cloudability
- **Efectivo** : La base de coste efectiva tiene en cuenta el impacto histórico de las instancias reservadas (RI) y los planes de ahorro (SP) para calcular el coste del tipo de instancia actual durante el periodo del informe. Al igual que la métrica «Coste (amortizado)», incluye todos los costes iniciales y recurrentes asociados.

  En otras palabras, la base de coste efectivo muestra el coste efectivo de ejecutar su instancia actual. Las cifras de costes del nuevo tipo de instancia recomendado se basan en los precios bajo demanda. Esto se debe a que es posible que la nueva configuración no se beneficie de las RI ni de las SP. Esta comparación es la opción más conservadora. Incluso si, sin darse cuenta, se aleja de los RI o los SP, su nueva tasa global seguirá siendo mejor. Como resultado, el ahorro total calculado con esta metodología a veces será menor. Se aplicarán precios personalizados a estas cifras, si procede.

**Nota:**

Utilice la base de costes bajo demanda si desea eliminar la naturaleza impredecible de los descuentos basados en compromisos de su análisis y maximizar el número de recomendaciones que se le proporcionan. Utilice la base de coste efectivo si prefiere basar sus recomendaciones en el coste real histórico de ejecutar sus instancias y adoptar un enfoque conservador.

**Seleccionar cuenta**

De forma predeterminada, el panel muestra recomendaciones para todas las cuentas. Para ver las recomendaciones para una cuenta en particular, seleccione el nombre de la cuenta en el menú desplegable Cuenta.

**Especificar el calendario**

Puedes elegir entre revisar los gastos de los últimos 10 días o de los últimos 30 días. De forma predeterminada, la opción «Línea de tiempo» está configurada en «10 días». Para la mayoría de los usuarios, el período recomendado es de 10 días, ya que permite capturar las tendencias de rendimiento más recientes y ofrece una mejor predicción del uso futuro de los recursos.

**Aplicar opciones**

También puede configurar opciones a nivel de página para incluir o excluir determinadas recomendaciones.

**Aplicar filtros**

Puede añadir filtros para incluir o excluir datos en función de una o varias condiciones.

**Añadir un filtro**

Para añadir un filtro:

1. Seleccione «Añadir filtro» en la barra de herramientas.
2. En el menú «Añadir filtro», seleccione una «Dimensión».
3. Seleccione un operador para proporcionar una condición lógica.
4. Elija un valor para refinar su filtro.
5. Seleccione Añadir filtro para aplicar el nuevo filtro a la página.

**Aplicar filtros con enlaces**

También puede añadir filtros seleccionando los valores con hipervínculos azules de la tabla principal. La regla de filtro se aplica automáticamente al campo Filtros. Solo puede seleccionar un valor o parámetro de cada columna a la vez.

**Eliminar un filtro**

Para eliminar un filtro:

1. Seleccione el icono del filtro  ![](../../../../03-media/cloudability-premium/images/edit-icon.jpg).
2. **Seleccione** la X situada junto al filtro que desea eliminar.

## Indicadores clave de rendimiento

Puede ver los siguientes indicadores clave de rendimiento (KPI) en su panel de control de Rightsizing:

- **Gasto total** : muestra el gasto total asignado actualmente.
- **Ahorro estimado en modo inactivo** : muestra el ahorro total estimado para todas las recomendaciones de Terminate.
- **Ahorro estimado con Rightsize** : muestra el ahorro potencial total estimado que se puede conseguir con todas las recomendaciones de Rightsize.
- **Gasto optimizado estimado** : muestra el gasto total estimado después de aplicar las recomendaciones.

## Tabla de recomendaciones de redimensionamiento

El panel contiene una tabla de recomendaciones de redimensionamiento, que ofrece una visión general de los recursos informáticos para los que se han identificado recomendaciones. La tabla incluye las siguientes columnas:

**Nota:**

De forma predeterminada, los datos se ordenan por la columna «Ahorro de costes». Para cambiar el orden de clasificación, solo tienes que seleccionar el nombre de la columna.

- **Nombre del recurso**  : El nombre del recurso « ScaleSet ».
- **Nombre de la cuenta** : El nombre de la cuenta en la que se ejecutan los recursos
- **Grupo de recursos** : El grupo de recursos de computación.
- **Fuente de datos** : La fuente de datos utilizada para los datos de utilización relevantes
- **Inactivo** : El tiempo empleado por debajo del 2 % de CPU en una escala de 1 a 100.
- **Coste:** el coste total de todas las instancias en ejecución en Compute.
- **Actual** : El tipo de instancia Compute actual. Para conjuntos de escalas heterogéneos, se introducirá el valor «Mixto» en el campo Actual
- **Novedad** : el tipo de instancia de Compute más recomendado.
- **Acción** : Recomendación para el recurso. La recomendación puede ser una de las siguientes

|  |  |
| --- | --- |
| **Recomendación** | **Descripción** |
| Dimensionar correctamente | Cambia el tamaño al tipo de recurso especificado en la columna Nuevo. |
| Terminar | Finalice su recurso porque está predominantemente inactivo. |
| Escalado automático | Configure el autoescalado para el recurso. |
| Ninguna acción | Por defecto, no se recomienda ninguna acción, pero es posible que haya recomendaciones adicionales con niveles de riesgo más altos disponibles en el panel Detalles. |

Ahorro de costes: importe estimado del ahorro de costes en 10 o 30 días.

**Exportar recomendaciones a un archivo Excel**

Para exportar las recomendaciones a un archivo Excel, seleccione Exportar. Tenga en cuenta que el archivo Excel incluirá varias columnas adicionales, como región, sistema operativo, precio unitario y otras.

**Detalles de la recomendación**

Para ver los detalles de la recomendación de un recurso concreto, seleccione «Ver detalles» en el menú «Más opciones» (tres puntos).

Para consultar las descripciones de las dimensiones y métricas de costes, véase «[Glosario de dimensiones y métricas de costes](glossary-of-cost-dimensions-and-metrics.html) ».

Para consultar los detalles de la dimensión y las métricas de utilización, consulte [el «Glosario de dimensiones y métricas de utilización](glossary-of-utilization-dimensions-and-metrics.html) ».

**Tema principal:**

[Ajuste de plantilla en Cloudability](get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)

**Tema principal:** [Redimensionamiento](../product/get-recommendations-for-scaling-your-cloud-resources-with-rightsizing.html)
