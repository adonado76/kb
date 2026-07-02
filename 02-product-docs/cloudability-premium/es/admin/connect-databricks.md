---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar tejidos de datos"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-databricks.html"
images:
  - "images/Databrick-Runtime.png"
  - "images/Databricks-Add-Service-Principle-permission.png"
  - "images/Databricks-Add-Service-Principle.png"
  - "images/Databricks-Service-Principle.png"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image002_-821243953.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar tejidos de datos

Puedes vincular tu cuenta de Databricks a Cloudability para habilitar la recopilación de datos sobre costes y uso. Esta integración está pensada para utilizarse únicamente con Databricks en AWS y Databricks en GCP. Si utilizas Azure Databricks, dispondrás de suficiente nivel de detalle en tus datos de facturación de Azure.

Tardan 24 horas en aparecer los datos iniciales sobre costes y consumo en Cloudability

**Requisitos previos**

- Debe ser un administrador de « Cloudability » y tener acceso a la página «Credenciales de proveedor» de Cloudability.

- Permisos adecuados para configurar un catálogo de Unity, habilitar un espacio de trabajo y un esquema del sistema, y crear un **usuario principal de servicio** que tenga acceso al catálogo, al esquema y a la tabla.

- Debes ser administrador de la cuenta de Databricks para gestionar las credenciales de « OAuth » de los sujetos de servicio.
- Los administradores de cuenta y de espacio de trabajo de Databricks pueden realizar acciones en la consola del espacio de trabajo de Databricks.

- Es necesario crear un SQL Warehouse (que debe ser sin servidor) que pueda utilizar el usuario principal del servicio para ejecutar la consulta
- Debería ser posible programar el notebook para que se ejecute una vez cada 24 horas y recabe los datos de costes y uso de Databricks
- Para programar el cuaderno, el cliente debe crear una máquina de cálculo que contenga la configuración de Spark.
- Comprueba si tienes un contrato de compromiso o un contrato de pago por uso con Databricks; esto nos ayudaría a comprobar si Cloudability muestra correctamente el coste de facturación

Resumen de la integración

Esta integración requiere que los usuarios configuren un catálogo de Unity, habiliten un espacio de trabajo y un esquema del sistema, y creen un usuario principal de servicio que tenga acceso al catálogo, al esquema y a la tabla. Los usuarios también deben crear un SQL Warehouse que pueda ser utilizado por el usuario principal del servicio para ejecutarlo, basándose en el cuaderno descargado en la interfaz de usuario de credenciales. Este cuaderno debe ejecutarse una vez al día para obtener los datos de costes y uso de Databricks. Cloudability no tiene acceso a tus descuentos personalizados con Databricks, por lo que hemos añadido una opción para introducir esa información en la interfaz de usuario de credenciales, de modo que podamos tener en cuenta este descuento en los costes que mostramos.

Databricks recomienda utilizar una identidad de entidad de servicio para herramientas, tareas y aplicaciones automatizadas. Te pedimos que crees uno para esta integración, ya que estamos automatizando el proceso de supervisión del uso y la facturación.

1. Configurar Unity Catalog. Haz clic en [https://docs.databricks.com/en/data-governance/unity-catalog/get-started.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fdata-governance%2Funity-catalog%2Fget-started.html "(se abre en una pestaña o una ventana nueva)").
2. Habilitar un espacio de trabajo para Unity Catalog. Haz clic en [https://docs.databricks.com/en/data-governance/unity-catalog/enable-workspaces.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fdata-governance%2Funity-catalog%2Fenable-workspaces.html "(se abre en una pestaña o una ventana nueva)").
3. Activar **el esquema del sistema** en Unity Catalog. Haz clic en [https://docs.databricks.com/api/azure/workspace/systemschemas/enable](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fapi%2Fazure%2Fworkspace%2Fsystemschemas%2Fenable "(se abre en una pestaña o una ventana nueva)")
4. Crea un **usuario principal de servicio** a nivel de cuenta. Haz clic en [https://docs.databricks.com/en/admin/users-groups/service-principals.html#add-service-principals-to-your-account-using-the-account-consol](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fadmin%2Fusers-groups%2Fservice-principals.html%23add-service-principals-to-your-account-using-the-account-consol "(se abre en una pestaña o una ventana nueva)").
5. Añadir un principal de servicio al espacio de trabajo habilitado para el catálogo de Unity. Haz clic en [https://docs.databricks.com/en/admin/users-groups/service-principals.html#add-a-service-principal-to-a-workspace-using-the-workspace-admin-settings](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fadmin%2Fusers-groups%2Fservice-principals.html%23add-a-service-principal-to-a-workspace-using-the-workspace-admin-settings "(se abre en una pestaña o una ventana nueva)").
6. Conceda al «Service Principal» el privilegio sobre el catálogo, el esquema y la tabla recién creados. Haz clic en [https://docs.databricks.com/en/data-governance/unity-catalog/manage-privileges/index.html#manage-privileges-in-unity-catalog](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fdata-governance%2Funity-catalog%2Fmanage-privileges%2Findex.html%23manage-privileges-in-unity-catalog "(se abre en una pestaña o una ventana nueva)").
7. Crea un almacén de datos SQL. [Haz clic en « https://docs.databricks.com/en/compute/sql-warehouse/create.html](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fcompute%2Fsql-warehouse%2Fcreate.html "(se abre en una pestaña o una ventana nueva)") ».

   Nota: SQL Warehouse debe ser un servicio sin servidor
8. Conceda al responsable del servicio permiso para utilizar SQL Warehouse. Haz clic en [https://docs.databricks.com/en/compute/sql-warehouse/create.html#manage-a-sql-warehouse](https://www.ibm.com/links?url=https%3A%2F%2Fdocs.databricks.com%2Fen%2Fcompute%2Fsql-warehouse%2Fcreate.html%23manage-a-sql-warehouse "(se abre en una pestaña o una ventana nueva)").

Nota: Si adquieres Databricks a través del mercado de un proveedor de servicios en la nube y añades datos de costes y uso de Databricks con esta integración, verás que los costes aparecen dos veces en los informes de « Cloudability ». Por ejemplo, si has adquirido Databricks a través del Marketplace de AWS, dispondrías de:

- La partida presupuestaria de alto nivel correspondiente a « AWS ».

- Las partidas con los costes detallados de Databricks y en las que AWS Marketplace figura como «Vendedor».

Tendrás que configurar filtros o vistas para ocultar los costes de Marketplace. Los costes del Marketplace no se incluyen en la factura.

**Paso 1: Consola de la cuenta de Databricks**

**Crear una entidad de servicio**

Para añadir una entidad de servicio a la cuenta mediante la consola de la cuenta, sigue los pasos que se indican a continuación.

1. Como administrador de la cuenta, inicia sesión en la consola de la cuenta.
2. Haz clic en «Gestión de usuarios ».
3. En la pestaña «Entidades de servicio », haz clic en «Añadir entidad de servicio ».
4. Introduce un nombre para el sujeto de servicio.
5. Haz clic en «Añadir».
6. Selecciona la pestaña «Credenciales y claves secretas»
7. En « **OAuth Secrets** », haz clic en «**Generate Secret** ».
8. Selecciona el número máximo de días y pulsa «Hecho».
9. Copia el **«Secret»** y **el «Client ID** » que aparecen en pantalla y, a continuación, haz clic en **«Hecho».**

![](../../../../03-media/cloudability-premium/images/Databricks-Service-Principle.png)

**Paso 2 – Consola de Databricks Workspace**

Añadir un entidad de servicio al espacio de trabajo

1. Inicia sesión en el espacio de trabajo.
2. Haz clic en «Gestión de usuarios ».
3. Selecciona «Configuración ».
4. Haz clic en «Identidad y acceso ».
5. Haz clic en «Gestionar» en «Entidades de servicio».
6. Haz clic en «Añadir entidad de servicio».
7. Añade la misma entidad de servicio que se ha creado anteriormente.

![](../../../../03-media/cloudability-premium/images/Databricks-Add-Service-Principle.png)

Añadir permiso al sujeto de servicio en el almacén

1. Haz clic en «SQL Warehouse ».
2. Para que el almacén se utilice en la consulta, haz clic en él.
3. Haz clic en «Permisos ».
4. Añade una entidad de servicio con el permiso «Can Use ».

![](../../../../03-media/cloudability-premium/images/Databricks-Add-Service-Principle-permission.png)

**Paso 3 – Cloudability**

1. En Cloudability, ve a **Configuración** > **Credenciales de proveedor** > **Añadir fuente de datos y selecciona Databricks**
   1. Descargar el cuaderno

**Paso 4 – Consola de Databricks Workspace**

El cliente debe programar el script que ha descargado desde la interfaz de usuario de Cloudability para que se ejecute una vez cada 24 horas en su **Workspace, donde se ha añadido el entidad de servicio.**

Nota: Para ejecutar este cuaderno, el cliente debe crear su máquina de cálculo con el entorno de ejecución de Databricks que se indica a continuación, el cual debe incluir Spark.

![](../../../../03-media/cloudability-premium/images/Databrick-Runtime.png)

Si el catálogo «billing\_data» existe, sigue los pasos que se indican a continuación; si no existe, ejecuta el cuaderno de trabajo descargado de Cloudability y, a continuación, sigue los pasos que se indican a continuación.

Añadir el permiso «Service Principal» a la tabla

1. Haz clic en el catálogo.
2. Haz clic en el nombre del catálogo al que quieras conceder permisos.
3. Haz clic en «Permisos ».
4. Haz clic en «Conceder ».
5. Selecciona a los directores.
6. Selecciona USE CATALOG, USE SCHEMA y SELECT en la sección Privilegios.
7. Haz clic en «Confirmar».

**Paso 5: Consola « Cloudability »**

1. Introduce los datos en la interfaz de usuario de « Cloudability »
   1. ID de cuenta de Databricks
   2. ID de cliente de Databricks
   3. El secreto de Databricks

      Nota: Copia el ID de cliente y el secreto del entidad de servicio
   4. Espacio de trabajo URL sin https: este es el espacio de trabajo en el que has aplicado la entidad de servicio
   5. Introduce el ID del almacén que has creado en el paso 2
   6. Selecciona el modelo de suscripción
      1. Marketplace: selecciona «Marketplace» si has adquirido Databricks a través de AWS o GCP marketplace
      2. Directo: selecciona esta opción si has comprado directamente a Databricks
   7. CSP dependiente
      1. Selecciona AWS o GCP, donde se aloja la infraestructura
   8. Selecciona un modelo de pago
      1. Contrato comprometido
         1. Aquí necesitamos la fecha de inicio, la fecha de finalización, el porcentaje de descuento y los detalles de los compromisos
         2. Si tienes varios contratos de compromiso, puedes añadirlos utilizando el botón «+»
      2. Pago por uso
         1. Indica la fecha de inicio del plan de pago por uso
   9. Haz clic **en «Guardar»**
   10. Haz clic en «**Verificar** ».

Una marca verde (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png)) indica que se ha realizado correctamente, mientras que un signo de exclamación rojo (![](../../../../03-media/cloudability-premium/images/clip_image002_-821243953.png)) indica que hay errores

En caso de que la verificación falle, vuelve a intentarlo dentro de 15 minutos.

Una vez finalizado este proceso, en un plazo de 24 horas, empezarás a ver cómo se van completando tus datos de facturación y las etiquetas de Databricks en Cloudability.

**Preguntas más frecuentes**

**¿ Cloudability admite listas blancas de direcciones IP para controlar el tráfico hacia Databricks?**

Sí, se admite la lista blanca de direcciones IP. Para obtener más información, ponte en contacto con el servicio de asistencia de IBM.

**¿** **Cloudability, admite enlaces privados o el uso compartido de deltas para Databricks?**

Por el momento, Databricks no admite enlaces privados ni el uso compartido de Delta.

**¿Qué hay que hacer si el cuaderno programado no se está ejecutando?**

Asegúrate de configurar una máquina de cálculo con Spark habilitado

**¿Se puede modificar el portátil?**

Se recomienda no editar el cuaderno descargado desde la interfaz de usuario de Cloudability, ya que varios procesos internos utilizan sus configuraciones.

**¿Cómo se obtienen las etiquetas de Databricks?**

Cloudability admite etiquetas personalizadas a nivel de recurso

- Estos datos forman parte de la información de facturación de Databricks y no se necesitan permisos adicionales en Cloudability para habilitarlos
- Transmitimos metadatos de uso, metadatos de identidad y características del producto, ya que « Tags.Workspaceid » aparecerá como clave de etiqueta bajo «cldy:databricks:workspaceid»

**¿Por qué es necesario introducir los descuentos en la interfaz de usuario?**

Cloudability no tiene acceso a tus descuentos personalizados con Databricks, por lo que hemos añadido una opción para introducir esa información en la interfaz de usuario de credenciales, de modo que podamos tener en cuenta este descuento en los costes que mostramos

**¿Qué importancia tienen las fechas a la hora de acreditarse en Databricks?**

Las fechas indicadas en la interfaz de usuario de credenciales se utilizan para recuperar los datos de Databricks.

Las API de Databricks nos permiten recuperar los datos de los últimos 13 meses; los clientes pueden elegir cualquier fecha dentro de ese periodo para obtener datos detallados de Databricks.
