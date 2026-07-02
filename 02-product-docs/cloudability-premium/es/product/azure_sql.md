---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Azure SQL"
breadcrumb:
  - "Cloudability Premium"
  - "Optimizar"
  - "Redimensionamiento en Cloudability Premium"
  - "Dimensionamiento correcto avanzado"
source_path: "product/azure_sql.html"
images:
  - "images/azure-sql-dashboard.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Azure SQL

Puedes utilizar el panel de control «Advanced Rightsizing» para consultar las recomendaciones de optimización de recursos para el Servicio de bases de datos relacionales de Amazon Web Services ( AWS ) ( RDS ). El panel de control muestra recomendaciones de optimización tanto para el ahorro como para las inversiones, gracias a un motor de Turbonomic. Puedes consultar las recomendaciones de varias cuentas de « AWS » desde un único panel de control.

[Ajuste avanzado del tamaño en « Cloudability Premium »](advanced-rightsizing-powered-by-turbonomic.dita "(se abre en una pestaña o una ventana nueva)")

**Antes de empezar**

Para ver el panel de control de « AWS RDS », asegúrate de haber vinculado Cloudability a las cuentas de AWS correctas.

[Conéctate a Microsoft Azure](../admin/azure-cm-setup.dita "(se abre en una pestaña o una ventana nueva)")

Nota: Debes asegurarte de que todas tus credenciales de proveedor existentes cuenten con los permisos necesarios de Turbonomic; de lo contrario, es posible que el motor de Turbonomic no pueda generar el conjunto correcto de acciones. Si ya eras cliente de « Cloudability » antes de la actualización a « Cloudability Premium », tendrás que volver a configurar todas y cada una de las credenciales de los proveedores para concederles un conjunto adicional de permisos.

**Accede al panel de control de AZURE SQL**

Para acceder al panel de control de Azure SQL, abre la página de inicio de Cloudability y, en el menú de navegación de la izquierda, selecciona «Optimizar» > «Ajuste del tamaño» > «Avanzado». En la página «Rightsizing», selecciona la pestaña «AZURE» y, a continuación, selecciona « **SQL Database** » en el menú desplegable.

![](../../../../03-media/cloudability-premium/images/azure-sql-dashboard.png)

**Especificar la base de coste**

La «base de coste» determina cómo se calculan las recomendaciones y cómo se proyectan los ahorros o las inversiones. La base de coste puede **ser** «ajustada» o **«ajustada y amortizada»**, lo que refleja los cálculos subyacentes de los costes de los recursos de origen y de destino.

**Ajustado** : se calcula utilizando el coste en efectivo de un recurso determinado, incluyendo tus tarifas privadas cuando estén disponibles (en cuyo caso el coste de compromiso se considera 0 $), y se compara con el coste en efectivo previsto para el futuro y con la cobertura esperada de los compromisos aplicables a este recurso durante el periodo de referencia. Este cálculo se denomina «On Demand» en la documentación de « Cloudability Premium : Workload Optimization UI» y « Turbonomic ».

**Amortizado ajustado** : se calcula utilizando el coste amortizado de un recurso determinado y los compromisos asociados que se le aplicaron durante el período de referencia (incluidas las tarifas privadas, cuando estén disponibles). El coste futuro del Estado se calcula en función de cómo se prevé que se apliquen esos compromisos, qué partes se prevé que sigan siendo bajo demanda y qué compromiso (si lo hay) queda libre para aplicarse en otro ámbito. Este cálculo se denomina «efectivo» en la documentación de « Cloudability Premium : Workload Optimization UI» y « Turbonomic ».

**Indicadores clave de rendimiento**

En tu panel de control de «Advanced Rightsizing» puedes consultar los siguientes indicadores clave de rendimiento (KPI):

- **Gasto total** : muestra el gasto total asignado actualmente
- **Ahorro potencial** : muestra el ahorro potencial total estimado que se podría conseguir aplicando todas las recomendaciones de optimización cuyo impacto en los costes sea inferior al coste actual
- **Inversiones necesarias** : muestra el total estimado de las inversiones potenciales correspondientes a todas las recomendaciones de optimización cuyo impacto en los costes es superior al coste actual

Nota: En el caso de SQL, el gasto viene determinado por el uso de la instancia.

**Tabla de recomendaciones para el ajuste de plantilla**

El panel de control incluye una tabla de recomendaciones de ajuste de recursos, que ofrece una visión general de los recursos de EDS para los que se han identificado recomendaciones. La tabla incluye las siguientes columnas:

Nota: Por defecto, los datos se ordenan según **la** columna «Impacto en el coste». Para cambiar el orden de clasificación, solo tienes que seleccionar el nombre de la columna.

- **Estado:** Estado que indica si la acción está lista para ejecutarse
- **Nombre del recurso** : El nombre del recurso SQL
- **Nombre de la cuenta** : el nombre de la cuenta en la que se ejecuta el recurso SQL
- **Sin interrupciones:**  Indicación de si la acción presentada no provoca interrupciones
- **Reversible** : indica si la acción descrita es reversible o no
- **Tipo** : El tipo de instancia SQL actual
- **Coste** : el coste actual de la instancia SQL
- **Nuevo tipo de instancia** : el tipo de instancia SQL recomendado
- **Nuevo coste** : El coste previsto del nuevo tipo de instancia SQL recomendado
- **Categoría de la acción** : La categoría de la acción recomendada. Los modos compatibles actualmente son «Rendimiento» o «Ahorro»
- **Medida** : La medida recomendada. En la tabla siguiente se enumeran las distintas acciones compatibles
- **Repercusión económica** : Repercusión económica de la puesta en marcha de esta medida \

|  |  |
| --- | --- |
| **Recomendación** | **Descripción** |
| **Escala** | Cambia el tamaño al tipo de recurso especificado en **la** columna «Nuevo tipo de instancia». Esta acción puede consistir en un «aumento» o una «reducción» de la capacidad, en función de las políticas configuradas |
| **Desactivar** | Cierra tu recurso, ya que está prácticamente inactivo |

**Exportar las recomendaciones de optimización a un archivo de Excel**

Para exportar las acciones recomendadas a un archivo de Excel, **seleccion** a «Exportar». Ten en cuenta que el archivo de Excel incluirá varias columnas adicionales, como la región, el sistema operativo, el precio unitario y otras.

**Detalles de la recomendación**

Para ver los detalles de la acción recomendada para un recurso concreto, **seleccion** a «Ver detalles» en el menú «Más opciones» (tres puntos).

La siguiente figura muestra un ejemplo de panel de detalles de una acción.

**Tema principal:** [Redimensionamiento avanzado](../product/advanced-rightsizing-powered-by-turbonomic.html)
