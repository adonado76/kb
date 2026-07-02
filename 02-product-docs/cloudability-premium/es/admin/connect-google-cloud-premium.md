---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar Google Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-google-cloud-premium.html"
images:
  - "images/GCP10_Billing_Export.jpg"
  - "images/GCP11_Billing_Export.jpg"
  - "images/GCP12_Billing_Export.jpg"
  - "images/GCP13_Creds.png"
  - "images/GCP14_Script.jpg"
  - "images/GCP15_EditCredst.png"
  - "images/GCP1_Billing_Export.jpg"
  - "images/GCP2_Billing_Export.jpg"
  - "images/GCP3_Billing_Export.png"
  - "images/GCP4_Billing_Export.jpg"
  - "images/GCP5_Billing_Export.jpg"
  - "images/GCP6_Billing_Export.jpg"
  - "images/GCP7_Billing_Export.jpg"
  - "images/GCP8_Billing_Export.jpg"
  - "images/GCP9_Billing_Export.jpg"
  - "images/connect-google-cloud-premium.png"
  - "images/connect-google-cloud-premium1.png"
  - "images/connect-google-cloud-premium2.png"
  - "images/regenerate_cloudability_more_options.jpg"
  - "images/setup_overview_guide_gcp-error-ok.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar Google Cloud

**Visión general**

Esta guía le explica el proceso para conectar su Google Cloud Platform a IBM Cloudability. Cloudability apoya

- GCP Facturación estándar

- GCP Facturación detallada.

Una vez conectado, tendrá acceso a las funciones de FinOps dentro de Cloudability.

Nota: Para garantizar una compatibilidad y un soporte técnicos óptimos, siga los pasos de conexión tal y como se describen. No se admiten configuraciones personalizadas. Si tienes alguna pregunta, ponte en contacto con **el servicio de asistencia** de IBM.

**Requisitos previos**

- Cloudability utiliza IAM para crear y gestionar roles personalizados

- Debe tener permisos de IAM en [GCP para crear un rol personalizado](https://docs.cloud.google.com/iam/docs/creating-custom-roles "(se abre en una pestaña o una ventana nueva)")

- Cloudability utiliza estos roles personalizados con permisos específicos para consultar datos de facturación, compromisos y precios.

  - CloudabilityRole\_Billing – para la cuenta de facturación
  - CloudabilityRole\_Buckets - para el acceso a los buckets de GCS
  - CloudabilityRole\_AdvancedFeatures – para proyectos

- Debe tener permisos para crear un depósito GCS dentro de GCP.

- Se requieren los siguientes permisos:

  - bigquery.tables.export (exportar datos de tablas fuera de BigQuery )
  - storage.buckets.getIamPolicy
  - storage.buckets.get
  - storage.multipartUploads.abortar
  - storage.multipartUploads.crear
  - storage.multipartUploads.lista
  - storage.multipartUploads.listParts
  - storage.objects.create
  - storage.objects.delete
  - storage.objects.get
  - storage.objects.list
  - storage.objects.update

- Debería ser posible ejecutar el script de shell « GCP » en la consola de GCP, lo que vinculará el rol a la cuenta de servicio de Cloudability ( [billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com](mailto:billing-data-service-acct@cloudability-credentials.iam.gserviceaccount.com "(se abre en una pestaña o una ventana nueva)") ) como miembro con el rol personalizado a nivel del proyecto de facturación

- Para poder ejecutar con éxito nuestro script desde su consola en la nube, su usuario gcloud necesita tener concedidos los siguientes permisos IAM a nivel de proyecto:

  - iam.roles.create
  - resourcemanager.projects.setIamPolicy
  - resourcemanager.projects.getIamPolicy

- Esto proporciona a los clientes un control total y una visibilidad completa de todas las acciones realizadas por cualquier entidad que asuma esa función dentro de sus proyectos de GCP.

- Acceso de administrador a las credenciales de proveedor de Cloudability

- Conocimiento de [las organizaciones de « GCP »](https://docs.cloud.google.com/resource-manager/docs/creating-managing-organization "(se abre en una pestaña o una ventana nueva)")

- Conocimiento del [sistema de acreditación GCP mediante acciones masivas.](gcp-credentialing-bulk-actions.html)

- Acceso y capacidad para habilitar la API Google Cloud Resource Manager

**Primeros pasos:**

El proceso de acreditación de Cloudability ( GCP ) requiere dos pasos principales:

- GCP Credenciales de la cuenta de facturación

- GCP Acreditación de proyectos (para funciones avanzadas)

El proceso de acreditación de cuentas de facturación de GCP consta de varios pasos que requieren que usted realice acciones tanto en el portal GCP como en Cloudability en distintas fases.

Durante este proceso, Cloudability utilizará su ID de tabla de facturación y generará un script que contiene comandos gcloud IAM que deberán ejecutarse en la consola GCP.

- Compruebe la sección IAM del proyecto correspondiente para determinar si dispone de estos permisos.
- Habilita la API « Google Cloud » (Compartir en la red social) de Resource Manager
- Cloudability utiliza la API Cloud Resource Manager de Google para comprobar si se han concedido los permisos necesarios para admitir las funciones disponibles.
- La API Cloud Resource Manager de Google ofrece numerosas ventajas sin coste alguno para usted. Puedes obtener más información al respecto en [Resource Manager](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2F "(se abre en una pestaña o una ventana nueva)").
- Puede encontrar una lista de las API disponibles a través de Resource Manager en [Cloud Resource Manager API](https://docs.cloud.google.com/resource-manager/reference/rest "(se abre en una pestaña o una ventana nueva)").

Nota: Cloudability utiliza la API projects.testIamPermissions para comprobar si se han concedido permisos específicos para admitir funciones avanzadas y de facturación. Para obtener más información, consulte [el método: projects.testIamPermissions](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Freference%2Frest%2Fv1%2Fprojects%2Ftestiampermissions "(se abre en una pestaña o una ventana nueva)").

**Acreditación** **de la cuenta de facturación de GCP**

**Paso 1 - Portal GCP : habilite la exportación BigQuery y el ID de tabla.**

- En la consola de GCP, **en** APIs y servicios > Biblioteca, busque **«API** de Cloud Resource Manager ».
- En la página API de Cloud Resource Manager, **seleccione** HABILITAR.
- Asegúrate de que la opción «API habilitada» esté marcada.

Trabajando en la Consola Google, escriba Facturación en la barra de búsqueda y cuando aparezcan los resultados seleccione Cuentas de facturación.

![](../../../../03-media/cloudability-premium/images/GCP1_Billing_Export.jpg)

Seleccione Exportación de facturación.

![](../../../../03-media/cloudability-premium/images/GCP2_Billing_Export.jpg)

Seleccione Editar configuración (en función del tipo de exportación que vaya a realizar).

![](../../../../03-media/cloudability-premium/images/GCP3_Billing_Export.png)

Seleccione el tipo de exportación que desea implementar (facturación estándar o detallada) haciendo clic en Editar configuración.

Nota: Recomendamos la facturación detallada, ya que los datos se enriquecen con detalles adicionales y proporcionan informes mucho más precisos.

Seleccione el proyecto en el que se almacenarán sus datos de facturación (probablemente su proyecto de facturación) y, a continuación, haga clic en Conjunto de datos y seleccione Crear un nuevo conjunto de datos.

![](../../../../03-media/cloudability-premium/images/GCP4_Billing_Export.jpg)

Añada un ID de conjunto de datos y haga clic en Crear conjunto de datos.

Nota: Te recomendamos que selecciones una ubicación multirregional (UE o EE. UU.) para tu conjunto de datos, de modo que tus datos de facturación se añadan de forma retroactiva para el mes actual y el anterior en GCP. Consulta [«Exportar datos de facturación a BigQuery »](https://docs.cloud.google.com/billing/docs/how-to/export-data-bigquery#dataset_locations_supported_for_use_with_data "(se abre en una pestaña o una ventana nueva)") para obtener más detalles y conocer las limitaciones

![](../../../../03-media/cloudability-premium/images/GCP5_Billing_Export.jpg)

Seleccione Guardar para completar el proceso.

![](../../../../03-media/cloudability-premium/images/GCP6_Billing_Export.jpg)

Nota: Cuando habilita la **BigQuery** exportación para una cuenta **de** facturación. Se crea automáticamente una tabla dentro del conjunto de datos especificado. Esta tabla se denomina tabla de facturación

- GCP El nombre de la tabla de costes de uso estándar debe tener el siguiente formato: **gcp\_billing\_export\_v1\_<BILLING\_ACCOUNT\_ID>**.

- GCP El nombre de la tabla detallada de costes de uso debe tener este formato  **gcp\_billing\_export\_resource\_v1\_<BILLING\_ACCOUNT\_ID>**  .

El uso estándar/la tabla detallada de costes de uso debe tener los siguientes detalles de partición, tal y como se indica en la imagen siguiente.

![](../../../../03-media/cloudability-premium/images/GCP7_Billing_Export.jpg)

Nota: Tutorial de « Google »: «[Exportar datos de facturación a BigQuery](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fbilling%2Fdocs%2Fhow-to%2Fexport-data-bigquery "(se abre en una pestaña o una ventana nueva)") ».

Una vez habilitada la exportación de « BigQuery », la tabla de facturación tardará unas horas en crearse, tras lo cual podrá localizar el ID de la tabla.

Puede encontrar el ID de la tabla de facturación navegando hasta el proyecto que contiene la exportación BigQuery de sus datos de facturación, **en Información de la tabla > ID de la tabla**.

![](../../../../03-media/cloudability-premium/images/GCP8_Billing_Export.jpg)

Debe especificar un proyecto y un conjunto de datos a los que se exportarán los datos de facturación cuando habilite la exportación de **BigQuery** para **una cuenta de** facturación. Se crea automáticamente una tabla dentro del conjunto de datos especificado. Esta tabla se denomina tabla de facturación y la **cuenta** de servicio de Cloudability debe poder leer los datos de esta tabla.

**Crear un depósito de almacenamiento**

Se necesita un cubo de almacenamiento en el que copiar los datos de la exportación de la tabla BQ para que Cloudability los recupere.

Trabajando en la Consola Google; escriba Cloud Storage en la barra de búsqueda y selecciónelo cuando aparezca.

![](../../../../03-media/cloudability-premium/images/GCP9_Billing_Export.jpg)

Haga clic en Crear para crear un cubo.

Introduzca un nombre para su cubo de almacenamiento (por ejemplo: cloudability-export y haga clic en Crear).

![](../../../../03-media/cloudability-premium/images/GCP10_Billing_Export.jpg)

Cuando se le solicite, mantenga los valores predeterminados y haga clic en Confirmar.

![](../../../../03-media/cloudability-premium/images/GCP11_Billing_Export.jpg)

Se creará un cubo.

![](../../../../03-media/cloudability-premium/images/GCP12_Billing_Export.jpg)

**Paso 2 - Cloudability :** **añada los datos de las credenciales en Cloudability.**

**Facturación estándar con GCS**

Nota: Para la facturación estándar, recomendamos el uso de un depósito de almacenamiento y no la transmisión a través de API

Una vez que haya recopilado la información indicada anteriormente, puede introducirla en Cloudability para actualizar su credencial de GCP.

Cloudability utilizará esta información para generar un script de Shell. Cuando se ejecuta el script desde su Cloud Shell en el portal GCP, se crearán y concederán derechos para Cloudability a través de la función personalizada con el fin de proporcionar acceso a la cuenta de almacenamiento.

- En Cloudability, navega hasta
- **Configuración** > **Credenciales del proveedor** > **Añadir fuente de datos** > **GCP**.
- Pulse Siguiente
- Seleccione « GCP » ( **Añadir** cuenta de correo electrónico). Se abrirá el panel «Add GCP Account» (Añadir cuenta de correo electrónico).

O

- **Configuración** > **Credenciales del proveedor** > **Ingress** > **GCP**.
- Pulse Siguiente
- Seleccione **Fact** uración estándar de GCP : se abrirá el panel Añadir credencial.
- Introduzca el identificador completo de la tabla, que es una combinación del proyecto, el conjunto de datos y la tabla, por ejemplo, project:dataset.gcp\_billing\_export\_v1\_<BILLING\_ACCOUNT\_ID>
- Introduzca el nombre del depósito GCS
- Introduzca el ID de la organización (recomendado, facilita la incorporación rápida)

  - *GCP Los clientes pueden acreditar rápidamente los proyectos de forma automatizada utilizando*[*GCP organización*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fcreating-managing-organization "(se abre en una pestaña o una ventana nueva)")*. Deberá trasladar todos los proyectos que haya creado en «Sin organización» a su nuevo recurso de organización.*
  - *Para obtener instrucciones sobre cómo trasladar tus proyectos,* [*consulta «Migración de proyectos a un recurso de la organización*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fproject-migration "(se abre en una pestaña o una ventana nueva)") *».*
- Elige entre el reajuste avanzado en modo de **solo lectura** o la automatización de acciones:
  - **«Solo lectura»** implica que los clientes permiten permisos de supervisión de costes de Cloudability, Turbonomic y Turbonomic.
  - La opción **«Automatizar acciones»** implica que los clientes conceden todos los permisos de Cloudability y Turbonomic, incluidos los relativos a las acciones automatizadas, es decir, la ejecución de Turbonomic y la ejecución de facturación de Turbonomic.
- Haga clic en «Generar script de configuración»
- Haga clic en Descargar script
- Se descargará localmente una plantilla de script de shell GCP. Guárdela en un lugar seguro para el siguiente paso, ya que deberá cargarla en la consola GCP

**Facturación estándar con BQ Streaming**

- **Configuración** > **Credenciales del proveedor** > **Añadir fuente de datos** > **GCP**.
- Pulse Siguiente
- Seleccione « GCP » ( **Añadir** cuenta de correo electrónico). Se abrirá el panel «Add GCP Account» (Añadir cuenta de correo electrónico).

O

- **Configuración** > **Credenciales del proveedor** > **Ingress** > **GCP**.
- Pulse Siguiente
- Seleccione **Fact** uración estándar de GCP : se abrirá el panel Añadir credencial.
- Introduzca el identificador completo de la tabla, que es una combinación del proyecto, el conjunto de datos y la tabla, por ejemplo, project:dataset.gcp\_billing\_export\_v1\_<BILLING\_ACCOUNT\_ID
- Nombre del cubo (opcional, se puede dejar en blanco)
- Identificación de la organización (recomendado, facilita la incorporación rápida)

  - *GCP Los clientes pueden acreditar rápidamente los proyectos de forma automatizada utilizando*[*GCP organización*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fcreating-managing-organization "(se abre en una pestaña o una ventana nueva)")*. Deberá trasladar todos los proyectos que haya creado en «Sin organización» a su nuevo recurso de organización.*
  - *Para obtener instrucciones sobre cómo trasladar tus proyectos,* [*consulta «Migración de proyectos a un recurso de la organización*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fproject-migration "(se abre en una pestaña o una ventana nueva)") *».*

- Elige entre las opciones avanzadas de ajuste de tamaño **«Solo lectura»** y «**Automatizar acciones** »:
  - **«Solo lectura»** implica que los clientes permiten permisos de supervisión de costes de Cloudability, Turbonomic y Turbonomic.
  - La opción **«Automatizar acciones»** implica que los clientes conceden todos los permisos de Cloudability y Turbonomic, incluidos los relativos a las acciones automatizadas, es decir, la ejecución de Turbonomic y la ejecución de facturación de Turbonomic.
- Haga clic en «Generar script de configuración»
- Haga clic en Descargar script
- Se descargará localmente una plantilla de script de shell GCP. Guárdela en un lugar seguro para el siguiente paso, ya que deberá cargarla en la consola GCP

![](../../../../03-media/cloudability-premium/images/GCP13_Creds.png)

**Facturación detallada con GCS (recomendado)**

- **Configuración** > **Credenciales del proveedor** > **Añadir fuente de datos** > **GCP**.
- Pulse Siguiente
- Seleccione « GCP » ( **Añadir** cuenta de correo electrónico). Se abrirá el panel «Add GCP Account» (Añadir cuenta de correo electrónico).

O

- **Configuración** > **Credenciales del proveedor** > **Ingress** > **GCP**.
- Pulse Siguiente
- Seleccione **Fact** uración detallada de GCP : se abrirá el panel Añadir credencial.
- Introduzca **el identificador completo de la tabla,** que es una combinación del proyecto, el conjunto de datos y la tabla, por ejemplo, project:dataset.gcp\_billing\_export\_resource\_v1\_<BILLING\_ACCOUNT\_ID
- Introduzca **el nombre del depósito GCS**.
- Introduzca **la fecha de facturación detallada**.

  Nota: Esta fecha indica el mes y el año desde el que tiene habilitadas las exportaciones de facturación detalladas. Si es la primera vez que lo hace, será el mes actual en formato AAAA-MM.

- **Identificación de la organización** (recomendado, facilita la incorporación rápida)

  - *GCP Los clientes pueden acreditar rápidamente los proyectos de forma automatizada utilizando*[*GCP organización*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fcreating-managing-organization "(se abre en una pestaña o una ventana nueva)")*. Deberá trasladar todos los proyectos que haya creado en «Sin organización» a su nuevo recurso de organización.*
  - *Para obtener instrucciones sobre cómo trasladar tus proyectos,* [*consulta «Migración de proyectos a un recurso de la organización*](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fresource-manager%2Fdocs%2Fproject-migration "(se abre en una pestaña o una ventana nueva)") *».*
- Elige entre las opciones avanzadas de ajuste de tamaño **«Solo lectura»** y «**Automatizar acciones** »:
  - **«Solo lectura»** implica que los clientes permiten permisos de supervisión de costes de Cloudability, Turbonomic y Turbonomic.
  - **La opción «Automatizar acciones»** implica únicamente que los clientes conceden todos los permisos de Cloudability y Turbonomic, incluidos los relativos a las acciones automatizadas, es decir, la ejecución de Turbonomic y la ejecución de facturación de Turbonomic.
- Haga clic en «Generar script de configuración»
- Haga clic en Descargar script
- Se descargará localmente una plantilla de script de shell GCP. Guárdela en un lugar seguro para el siguiente paso, ya que deberá cargarla en la consola GCP

**Paso 3: cargue y ejecute el script de shell « GCP ».**

El script realiza dos pasos: primero configura una función personalizada dentro del proyecto de facturación y, a continuación, añade la cuenta de servicio de Cloudability como miembro del proyecto, vinculando la función personalizada. Esto garantiza que nuestra cuenta de servicio solo pueda leer datos de las tablas BigQuery dentro de un proyecto de facturación. No accedemos a los datos de BigQuery en proyectos que no sean de facturación.

En el caso del depósito GCS, seguimos el proceso anterior, exportamos los datos de BigQuery a GCS mediante una tarea de exportación de BigQuery y extraemos esos datos a Cloudability.

**1. Configuración de roles personalizados**

En primer lugar, el script crea roles personalizados dentro del proyecto de facturación. El script asigna los permisos necesarios para leer los datos de facturación al rol personalizado

# Ejemplo: Crear una función personalizada de facturación para my-billing-project-123 # El ID del proyecto de facturación es my-billing-project-123 gcloud iam roles create CloudabilityRole\_Billing \ --project \ my-billing-project-123 \ --title \ " Cloudability Billing Role" \ --description \ "Allows Cloudability access to billing account data" \ --permissions \ bigquery.jobs.create,bigquery.tables.getData \ --stage =GA

**2. Añadir cuenta de servicio como miembro y vincular rol personalizado**

Una vez creado el rol personalizado, el script añade **la** cuenta de servicio de Cloudability como miembro del proyecto de facturación y vincula el rol personalizado a ella.

# Ejemplo: Añadir la cuenta de servicio de Cloudability como miembro de my-billing- project-123 # El ID del proyecto de facturación es my-billing-project-123 gcloud projects add-iam-policy-binding my-billing-project-123 \ --member serviceAccount:billing-data-service-acct@cloudability- credentials.iam.gserviceaccount.com \ --role 'projects/my-billing-project- 123/roles/CloudabilityRole\_Billing '

**3. Cubeta GCS**

Si opta por la facturación estándar de GCP con un depósito de GCS o la facturación detallada de GCP, debe configurar un depósito de GCS GCP. Cloudability Exportará datos a este bucket de GCS temporalmente desde la tabla configurada GCP BigQuery para ingestar estos datos en Cloudability. Una vez completada la ingesta de datos, Cloudability eliminará los datos del depósito.

**Nota:** No se pueden utilizar los mismos ID de cuenta de pagador de GCP en la facturación estándar y detallada al mismo tiempo.

**Ejecuta el script.**

Siga los pasos que se indican a continuación para ejecutar el script a través de Cloud Shell en su consola en la nube. No importa desde qué lugar de Cloud Shell ejecute el script.

- Activa la función « Cloud Shell » (Compartir en la nube), selecciona el![](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icono y **selecciona** «Upload file» (Subir archivo). Elija el script descargado desde el explorador de archivos y confirme.
- chmod +x <nombre del script> para hacer que el script sea ejecutable
- A continuación, ejecute el script en su Cloud Shell :

`./ script-name`

Nota: En los comandos siguientes, sustituya script-name por el nombre completo y la extensión del script real.

- Compruebe si hay algún error. Por ejemplo:

![](../../../../03-media/cloudability-premium/images/setup_overview_guide_gcp-error-ok.jpg)

- Si el script tiene éxito, verá una salida similar a la siguiente en su Cloud Shell :

![](../../../../03-media/cloudability-premium/images/GCP14_Script.jpg)

**Paso 4 – Cloudability Verificar credenciales**

- Seleccione «Verificar credenciales».
- Seleccione el icono de actualización para actualizar el estado.

La marca de verificación verde indica que esta cuenta de facturación se ha acreditado correctamente.

Nota: Tus proyectos no serán visibles de inmediato; tardarán hasta 24 horas en aparecer en Cloudability.

Ya has añadido correctamente tu cuenta de facturación a Cloudability. Ingerimos datos a intervalos regulares y sus datos de facturación estarán disponibles a partir del siguiente ciclo de ingesta. En la próxima ingesta, también enumeraremos los proyectos asociados a esta cuenta de facturación.

Por último, si su organización tiene cuentas de facturación adicionales de GCP que desea añadir, repita este proceso para cada una de esas cuentas de facturación.

Nota: Al configurar tus cuentas de GCP, desactiva cualquier restricción de dominio aplicada. Puede activarlo una vez finalizado el proceso de acreditación.

Una vez finalizado este proceso, en unas pocas horas,

- Cloudability Empezará a mostrar tus datos de facturación y las etiquetas de « GCP » en Cloudability.
- También se importarán los datos de precios minoristas. Para habilitar la fijación de precios personalizada, consulte [**la sección "Configuración de la compatibilidad con precios personalizados para GCP**](https://www.ibm.com/docs/en/SSSVH06/cloudability/product/gcp-rightsizing-custom-pricing-support.html "(se abre en una pestaña o una ventana nueva)")
- Cloudability también mostrará los proyectos.

El siguiente paso consiste en configurar las credenciales de los proyectos de GCP.

**GCP Acreditación de proyectos (funciones avanzadas)**

El objetivo de esta sección es ayudarle a recorrer el proceso de acreditación de sus proyectos para activar las funciones avanzadas de Cloudability. Si su organización tiene varios proyectos de GCP, este proceso debe repetirse para cada proyecto en el que desee habilitar las funciones avanzadas.

Antes de comenzar, asegúrese de haber revisado los requisitos previos

Para acreditar su proyecto:

- Añada una nueva credencial de proyecto, como se describe en Configurar credenciales a nivel de proyecto.
- Ejecuta el script tal y como se describe en «[Ejecutar el script](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=cloudability-connect-google-cloud#/Run "(se abre en una pestaña o una ventana nueva)") ».
- Familiarícese con [la acreditación de GCP mediante acciones masivas.](gcp-credentialing-bulk-actions.html)

**Añadir una nueva credencial de proyecto**

Para habilitar las funciones avanzadas para un proyecto de GCP :

- Vaya **a «Credenciales del** proveedor» y seleccione la pestaña « **GCP ».**
- Seleccione **el** icono Editar para abrir el panel Editar una credencial.
- - Si se ha añadido un ID de organizació GCP a en la cuenta de facturación, la elección entre «**Solo lectura** » y **«Acciones automatizadas»** a nivel de proyecto se ajusta a la selección realizada en el nivel superior
  - Si no se ha añadido un ID de organizació GCP e en la cuenta de facturación, la opción de **elegir** entre «Solo lectura» y **«Acciones automatizadas»** a nivel de proyecto estará disponible en cada proyecto individual.

  Seleccione Actualizar credencial.
- **Selecc** ione Descargar script.
- Si su navegador le muestra una advertencia, **sel** eccione «Conservar».

![](../../../../03-media/cloudability-premium/images/GCP15_EditCredst.png)

Ejecuta el script

Para obtener más información, consulte la sección Ejecutar el script

**Cómo confirmar el éxito**

Esto puede hacerse mediante acciones masivas o manualmente.

- Verificación masiva a través de la interfaz de usuario: [GCP Acreditación mediante acciones masivas](gcp-credentialing-bulk-actions.html)

- Verificación manual a través de la interfaz de usuario:

- **Seleccione** «Verificar credenciales» en cada proyecto.

- **Sel** eccione Detalles para verificar que el proyecto tiene los permisos necesarios para las funciones avanzadas.

**Actualización de los clientes actuales de Cloudability a Cloudability Premium**

Tras actualizar a Cloudability Premium, las credenciales existentes de Cloudability seguirán funcionando para Cloudability, pero no para Turbonomic. Para que Cloudability y Turbonomic funcionen juntos, los clientes tendrían que volver a acreditar sus cuentas. Esto se debe a que se necesitan más permisos para que funcionen sin problemas

1. En Cloudability, vaya a **Configuración > Credenciales de proveedor > GCP.**
2. Seleccione una cuenta existente y haga clic en las elipses.
3. Seleccione el icono del lápiz para abrir Editar una credencial.
4. Introduzca **el ID de la organización** (opcional): Esto ayuda a automatizar las credenciales a nivel de cuenta de facturación.
5. Elige entre las opciones avanzadas de ajuste de tamaño **«Solo lectura»** y «**Automatizar acciones** »:
   - **«Solo lectura»** implica que los clientes permiten permisos de supervisión de costes de Cloudability, Turbonomic y Turbonomic.
   - La opción «Automatizar acciones» implica que los clientes conceden todos los permisos de Cloudability y Turbonomic, incluidos los relativos a las acciones automatizadas, es decir, la ejecución de Turbonomic y la ejecución de facturación de Turbonomic.
6. Descargue la plantilla.
7. Actualiza los permisos ejecutando el script en la consola de GCP.
8. Vuelva a verificar la cuenta en Cloudability UI.
9. La verificación correcta se indicará con una marca verde.

El estado de Automatizar acciones se muestra a continuación:

- Se mostraría como **«Desactivado»** si **el** conmutador «Ajuste avanzado» estuviera configurado en «**Solo lectura** ».
- Se mostraría como **«Activado»** si **el** conmutador «Ajuste avanzado» estuviera configurado en «**Automatizar acciones** ».

**Nota:** La función «Automatizar acciones» solo muestra el estado de la plantilla seleccionada para la descarga y aún no muestra el estado « Turbonomic ».

- Si se selecciona la acreditación automatizada utilizando un ID de organización de GCP

  - Automatizar acciones: **ON/OFF** seguirá la selección basada en la cuenta de facturación GCP.
    - Si **la opción «Automatizar acciones» (Activada)** está configurada en una cuenta de facturación de GCP, todos los proyectos de GCP estarán **activados** para las cuentas de la organización seleccionada en GCP.
    - Si la cuenta de facturación GCP está configurada como **de solo lectura (DESACTIVADA)**, todos los proyectos GCP estarán **DESACTIVADOS** para las cuentas de la organización GCP seleccionada.
  - GCP El estado de los proyectos no se puede cambiar en cuentas vinculadas individuales cuando se opta por la acreditación automatizada mediante el ID de la organización.
- Si no se selecciona la credencialización automatizada mediante ID de organización.

  - Tanto las cuentas de facturación de GCP como los proyectos pueden tener diferentes estados **ON/OFF** en Automate Actions.
  - El estado **ON/OFF** se puede cambiar individualmente sin ninguna dependencia entre las cuentas de facturación de GCP y los proyectos.

Al cambiar de «Ajuste avanzado» a «Solo lectura», aparece una ventana emergente que solicita confirmación.

![](../../../../03-media/cloudability-premium/images/connect-google-cloud-premium.png)

**Visualización de los permisos de Turbonomic**

Hay permisos adicionales de Turbonomic que se añaden a los básicos (datos de facturación), avanzados (datos de utilización) y optimización de recursos (ejecutar acciones), que se documentan en los documentos del centro de ayuda. Una vez verificada tu cuenta, puedes ver la lista de permisos seleccionando la opción **Detalles** en cada cuenta de GCP que aparece en Cloudability.

![](../../../../03-media/cloudability-premium/images/connect-google-cloud-premium1.png)

Si los clientes existentes no vuelven a acreditar sus cuentas en ese momento:

- En Cloudability, GCP la ingesta de datos de facturación continuará.
- Las acciones de Automatizar se marcarán como **DESACTIVADAS**.
- En la pestaña **«Detalles»**, todos **los permisos de « Turbonomic »** aparecen marcados con una «x» ROJA.

Si los clientes existentes vuelven a acreditar sus cuentas en Cloudability utilizando el script de powershell con permisos de **sólo lectura** y se verifica la(s) cuenta(s):

- Las acciones de Automatizar se mostrarán como **DESACTIVADAS.**
- En la pestaña Detalles, los permisos relacionados con Turbonomic aparecerán con una marca verde.
- Turbonomic comenzaría a funcionar con permisos de **solo lectura**.

Una vez que se hayan habilitado los nuevos permisos mediante **«Automate Actions»** en la consola de GCP y se hayan verificado las cuentas:

- Las acciones de Automatizar se marcarán como **ON**.
- En la pestaña Detalles, todos y los permisos aparecen con una marca de verificación verde.
- Turbonomic empezaría a trabajar con los permisos de «Automate Actions».

Nota: La opción **Activar/Desactivar** acciones automáticas se muestra en la interfaz de usuario de credenciales de proveedores según la selección realizada en Alternar y descargar la plantilla.

**Estado de las credenciales**

Cloudability La pantalla de credenciales del proveedor muestra el estado de la cuenta desde:

- Cloudability
- Turbonomic

Una vez que se ejecuten las últimas plantillas, el estado de la cuenta debería estar sincronizado entre Cloudability y Turbonomic. Para obtener más información sobre el estado de la cuenta, consulte la sección de detalles de la cuenta.

![](../../../../03-media/cloudability-premium/images/connect-google-cloud-premium2.png)

**Preguntas más frecuentes**

**Los datos proporcionados en la página «Billing Export» (Exportación de facturación) difieren de los que aparecen en la página « BigQuery » (Exportación de datos de facturación) de su tabla de facturación.**

En concreto, el ID de tabla de la página BigQuery se construye utilizando el ID del proyecto de facturación, mientras que en la página de exportación de facturación aparece el nombre del proyecto de facturación. Los ID son únicos, mientras que los nombres no lo son.

Solución: Revisar los requisitos previos.

**¿Qué hacer si el ID del proyecto, el conjunto de datos o el ID de la tabla se truncan?**

Contexto: Introduces tu ID completo de la tabla de facturación GCP y observas que hay errores. Además, al editar la credencial, se observa que el ID del proyecto, el conjunto de datos o el ID de la tabla aparecen truncados. Es posible que haya recuperado o creado su ID de tabla de facturación GCP en la página Exportación de facturación.

Solución: Debe copiar el ID completo de la tabla de la página BigQuery para su tabla de facturación.

**¿Cómo puedo descargar la plantilla actualizada con los permisos más recientes si se ha producido una actualización de los permisos?**

La plantilla actualizada se puede descargar editando la cuenta de facturación existente y descargando la plantilla más reciente correspondiente. Una vez descargada, sigue los pasos para la acreditación que se indican tras la descarga de la plantilla.

**[Script] Error: ( gcloud.iam.roles.create ) Un recurso del proyecto es objeto de conflicto.**

Contexto: Esto puede ocurrir cuando tiene un rol existente dentro de su proyecto de facturación con role\_id CloudabilityRole\_Billing. El error indica que el script no puede crear un nuevo rol con role\_id CloudabilityRole\_Billing porque ya existe uno.

Solución: Ignore este error.

**[Script] Error: ( gcloud.iam.roles.create ) FAILED\_PRECONDITION: No se puede crear un rol con role\_id ( CloudabilityRole\_Billing ) cuando ya existe un rol con ese role\_id en estado eliminado.**

Contexto: Esto puede ocurrir cuando ejecuta el script después de eliminar un rol existente de su proyecto de facturación con role\_id CloudabilityRole\_Billing. El rol podría estar en un estado eliminado y el script no puede crear un nuevo rol con ese role\_id. Puede ver el estado del rol (Activado, Desactivado, Eliminado) en su consola en la nube.

Solución: Elimine el rol existente con role\_id CloudabilityRole\_Billing de su proyecto de facturación y vuelva a ejecutar el script.

**¿Cómo gestionar las restricciones de dominio de GCP?**

Si tiene restricciones de dominio, es posible que observe mensajes de error. Para solucionar esto, añada Cloudability a la lista blanca para consultar los datos añadiendo el ID de cliente del espacio de trabajo GCP de Cloudability en su política de organización.

El dominio es cloudability.com y el ID es C03n3dgoi

**Controles del servicio VPC**

[Obtener recomendaciones basadas en datos de la GPU](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=cloudability-connect-google-cloud "(se abre en una pestaña o una ventana nueva)")

**Requisitos previos:**

1. Cada VM debe tener [GPU conectadas](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fcompute%2Fdocs%2Fgpus%2Fcreate-vm-with-gpus "(se abre en una pestaña o una ventana nueva)").

1. Cada tarjeta « VM » debe tener [instalado un controlador de](https://www.ibm.com/links?url=https%3A%2F%2Fcloud.google.com%2Fcompute%2Fdocs%2Fgpus%2Finstall-drivers-gpu%23verify-driver-install "(se abre en una pestaña o una ventana nueva)") GPU.

1. Cada servidor de « VM » debe tener instalado « Python », « 3.6 » o una versión posterior.

1. Cada servidor de VM debe tener instalados los paquetes necesarios para crear entornos virtuales de Python.

Consulte también [Configurar el agente de supervisión GCP para el dimensionamiento adecuado](gcp-memory-metrics.html).

- **¿El estado de la cuenta Cloudability y el estado del destino Turbonomic no coinciden en las pantallas de credenciales del proveedor? ¿Cuáles podrían ser las razones?**

  Los clientes actuales de Cloudability que actualicen a Cloudability Premium deben volver a acreditar sus cuentas para obtener los últimos permisos de Turbonomic.

  El desajuste en el estado de la cuenta puede deberse a varias razones:
  - La recertificación no se realizó basándose en las últimas plantillas/permisos.
  - Si se realizó la recertificación, es posible que se hiciera utilizando una versión anterior de la plantilla y, desde entonces, se han añadido algunos permisos nuevos para Cloudability Premium.
  - Si la recertificación no ayuda, póngase en contacto con los equipos IBM de asistencia.

  **¿Dónde puedo encontrar los diferentes iconos que aparecen en las descripciones del estado de las cuentas?**

  [Indicadores de estado de las credenciales de los proveedores](vendor-credentials.html)

  **Para ver las mejoras completas de SCUD en la interfaz de usuario de informes de Cloudability para una cuenta de pagador de GCP, ¿qué exportación de facturación se debe utilizar para la configuración de credenciales?**

  Se recomienda **la exportación detallada de facturación** de « GCP », ya que proporciona una visibilidad completa de los casos de uso excesivo y uso insuficiente dentro de los informes de « Cloudability »

- [GCP Acreditación mediante acciones masivas](gcp-credentialing-bulk-actions.html)
- [Referencia sobre permisos - GCP](permissions-reference-gcp.html)
- [Configurar el agente de monitorizació GCP para el ajuste de recursos](gcp-memory-metrics.html)
- [Compatibilidad con las etiquetas « GCP »](gcp-tags.html)
- [Configuración de la compatibilidad con precios personalizados para GCP](../product/gcp-rightsizing-custom-pricing-support.html)
- [Configuración de la cartera de compromisos para « GCP »](commitment-portfolio-gcp.html)

- **[GCP Acreditación mediante acciones masivas](../admin/gcp-credentialing-bulk-actions.html)**
- **[Referencia de permisos - GCP](../admin/permissions-reference-gcp.html)**
- **[Configurar un agente de supervisión de GCP para el redimensionamiento](../admin/gcp-memory-metrics.html)**
- **[GCP Etiquetas y rótulos](../admin/gcp-tags.html)**
- **[Configuración de la asistencia para precios personalizados para GCP](../product/gcp-rightsizing-custom-pricing-support.html)**
- **[Configuración de la cartera de compromisos para GCP](../admin/commitment-portfolio-gcp.html)**
