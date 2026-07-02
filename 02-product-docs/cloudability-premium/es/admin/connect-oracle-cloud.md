---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar Oracle Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-oracle-cloud.html"
images:
  - "images/OCI-api-key.png"
  - "images/OCI-generate-api-key.png"
  - "images/OCI-user-groups-.png"
  - "images/generating__api_oci_3.jpg"
  - "images/oracle-cloud-adding-credentials-child-tenancies.jpg"
  - "images/terraform_script_1.jpg"
  - "images/terraform_script_2.jpg"
  - "images/terraform_script_3.jpg"
  - "images/terraform_script_4.jpg"
  - "images/terraform_script_5.jpg"
  - "images/terraform_script_7.jpg"
  - "images/validating_oci_1.jpg"
  - "images/validating_oci_3.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar Oracle Cloud

Puedes conectar tu entorno de Oracle Cloud Infrastructure (OCI) a Cloudability para habilitar la importación de datos de costes y uso.

Nota: Pueden pasar hasta 24 horas antes de que los datos iniciales sobre costes y consumo aparezcan en Cloudability.

Para garantizar una compatibilidad y un soporte técnicos completos, sigue los pasos de conexión tal y como se describen. No se admiten configuraciones personalizadas. Si tiene alguna pregunta, póngase en contacto con **el soporte IBM**.

Resumen de la integración

1. Cómo consultar los datos de costes y consumo en Cloudability

   Cloudability obtiene los datos de costes y uso de OCI a partir de los informes de costes, que son propiedad de OCI y se encuentran en el espacio de inquilino raíz de tu consola de OCI. Para que Cloudability pueda acceder a tus datos de costes y uso de OCI, debes validar las credenciales de tu tenencia raíz, ya que los datos de tus tenencias secundarias se agrupan en la tenencia raíz.

   El proceso de acreditación se lleva a cabo mediante un script de Terraform, y se necesita el OCID de tu tenencia raíz para generar y ejecutar el script. El script incluye comandos para crear un grupo y un usuario, añadir el usuario al grupo, crear políticas y asociarlas al grupo, de modo que Cloudability pueda acceder a los informes de costes desde la consola de OCI. Ten en cuenta que estas políticas otorgan a Cloudability permiso de solo lectura sobre los datos de OCI.

   Una vez ejecutado el script en la consola de OCI, tendrás que generar claves de firma. El último paso consistirá en pegar el nombre de la región de origen, el OCID de usuario, el OCID de grupo, la huella digital y la clave privada en la interfaz de usuario de Cloudability.
2. Cómo obtener los datos de uso en Cloudability

   Una vez que hayas completado el proceso de acreditación de tu tenencia raíz, recibirás datos de utilización de OCI únicamente para tu tenencia principal. Una vez verificadas las credenciales, sus tenencias secundarias aparecerán en la interfaz de usuario de acreditación, y deberá completar también el proceso de acreditación para estas tenencias secundarias a fin de obtener sus datos de utilización. La obtención de datos sobre la utilización permitirá a Cloudability ofrecer recomendaciones para optimizar el tamaño de las instalaciones. Encontrarás más detalles al final de esta página, en el apartado «Añadir credenciales para tus subarrendamientos ».

**Requisitos previos**

Antes de empezar, asegúrate de lo siguiente:

- Eres administrador de « Cloudability ».
- Tienes permisos de administrador en la consola de OCI.
  - Esto es necesario para ejecutar el script de Terraform en la consola de OCI.

Pasos para la integración

Consigue tu ID de inquilino de OCI

1. Inicia sesión en la consola de Oracle Cloud Infrastructure (OCI).
2. Selecciona «Gobernanza y administración» en el menú de navegación situado en la esquina superior izquierda del panel de control.
3. Selecciona «Contratos de alquiler» en el encabezado «Gestión de la organización». Aquí aparecen tus contratos de alquiler.
4. Copia el ID de tu entorno principal seleccionando el icono de copia situado junto al ID de tu entorno, cuyo nombre incluye la expresión «Entorno principal».
5. En Cloudability, ve a Configuración > Credenciales de proveedor > OCI.
6. Selecciona «Añadir una credencial ». Se abre el panel «Añadir una credencial» en la parte izquierda.
7. Pega el ID del contrato de alquiler principal.
8. Selecciona «Guardar ».

Generar el script de Terraform

Una vez guardado tu ID de alquiler, selecciona «Generar script ». Descarga el script de Terraform. Por favor, crea una carpeta específica, por ejemplo: « Cloudability », y guarda el script en esa carpeta de tu ordenador. Esto se hace porque, al subir el script, no es posible subirlo por separado, sino que hay que subir la carpeta que lo contiene.

A continuación se muestra el contenido de Terraform que utiliza Cloudability para crear los recursos necesarios:

```
variable "cloudablity_user_email" {
				description = "This is a variable to assign the email to user. If not provided, default email will be set."
				type        = string
				default     = "cldyuser@cloudability.com"
				}
				 
				resource "oci_identity_user" "cloudablity_user" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability user and they will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_User"
				freeform_tags = {
				"User_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_group" "cloudability_group" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This is a Cloudability group and it will be accessing cost data from your tenant."
				name = "CloudabilityDataCollector_Group"
				freeform_tags = {
				"Group_Created_For"= "Cloudability"
				}
				}
				 
				resource "oci_identity_user_group_membership" "user_group_membership" {
				group_id = oci_identity_group.cloudability_group.id
				user_id = oci_identity_user.cloudablity_user.id
				}
				 
				resource "oci_identity_policy" "cloudability_policy" {
				compartment_id = "ocid1.tenancy.oc1..aaaaaaaa4pjpasfply4eky7dl6msfdt3doqpfpmbuw2aesigtvedd4oxhufa"
				description = "This policy will retrieve permissions to access the cost report and list policy."
				name = "CloudabilityCostDataReaderPolicy"
				freeform_tags = {
				"Policy_Created_For"= "Cloudability"
				}
				statements = [
				"define tenancy reporting as ocid1.tenancy.oc1..aaaaaaaaned4fkpkisbwjlr56u7cj63lf3wffbilvqknstgtvzub7vhqkggq",
				"endorse group ${oci_identity_group.cloudability_group.name} to read objects in tenancy reporting",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-tenancy in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read organizations-family in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read policies in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read metrics in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read rate-cards in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-images in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to inspect instances in tenancy",
				"allow group ${oci_identity_group.cloudability_group.name} to read instance-family in tenancy"
				]
		}
```

Nota: Se ha añadido la variable «cloudablity\_user\_email» al script de Terraform, ya que se trata de un dato obligatorio para los usuarios que utilizan Identity Domain en su consola de OCI. La dirección de correo electrónico « cldyuser@cloudability.com » es un ejemplo provisional y se puede modificar directamente en el script de Terraform o actualizar más adelante, una vez que se haya subido a la consola de OCI.

Sube el script de Terraform

1. En la consola de OCI, selecciona el menú de navegación situado en la esquina superior izquierda de la página del panel de control y, a continuación, selecciona «Servicios para desarrolladores ».

   ![Captura de pantalla de OCI Terraform](../../../../03-media/cloudability-premium/images/terraform_script_1.jpg)
2. Selecciona «Stacks» en el encabezado de « Resource Manager ».

   Nota: Asegúrate de seleccionar el compartimento raíz en el «Ámbito de la lista» de la vista lateral izquierda.

   ![Captura de pantalla del gestor de recursos de OCI](../../../../03-media/cloudability-premium/images/terraform_script_2.jpg)
3. Selecciona «Crear pila» para crear una nueva pila.

   ![Captura de pantalla de la pila de OCI](../../../../03-media/cloudability-premium/images/terraform_script_3.jpg)
4. En la página «Crear pila», selecciona «Mi configuración» para cargar los archivos de configuración de Terraform.

   ![Captura de pantalla de mi configuración de OCI](../../../../03-media/cloudability-premium/images/terraform_script_4.jpg)
5. En la sección «Configuración de la pila», selecciona «Carpeta » y, a continuación, busca la carpeta en la que se encuentra el archivo de configuración.
6. Selecciona «Subir» en la ventana emergente.

   Nota: Asegúrate de que, en el campo «Crear en compartimento », el compartimento seleccionado tenga marcado «(raíz)».

   ![Subir una captura de pantalla de Terraform de OCI](../../../../03-media/cloudability-premium/images/terraform_script_5.jpg)
7. En el cuadro de texto «Nombre», introduce « Cloudability » como valor. Selecciona «Siguiente ».
8. Ahora tienes la opción de actualizar la dirección de correo electrónico « cldyuser@cloudability.com » que figura en el script de Terraform. Esta variable solo es necesaria si dispone de «Identity Domain» en su consola de OCI y puede actualizarse en esta fase, si fuera necesario.
9. Selecciona la versión de Terraform « 1.5 »
10. Marca la casilla «Ejecutar y aplicar ».

    ![](../images/OCI_Terrform_version%20update.png)
11. Selecciona «Crear» para crear la pila.

El comando « Resource Manager » validará el archivo Terraform facilitado y creará una nueva pila.

Supervisa el estado del trabajo (estado del ciclo de vida) recuperando el trabajo. «Correcto» indica que la tarea se ha completado.

Esta tarea creará un usuario, un grupo y una política. La operación puede llevar algún tiempo, dependiendo de la complejidad del trabajo. Mientras se ejecuta el trabajo, o una vez finalizado, obtendrás el contenido de los registros del trabajo.

Una vez creada la pila, podrás verla en la sección «Pilas ».

![Captura de pantalla de la pila de Terraform de OCI](../../../../03-media/cloudability-premium/images/terraform_script_7.jpg)

Validar los recursos creados

1. Selecciona «Identidad y seguridad» en el menú de navegación situado en la esquina superior izquierda del panel de control.

   ![Captura de pantalla de identidad y seguridad de OCI Terraform](../../../../03-media/cloudability-premium/images/validating_oci_1.jpg)
2. Selecciona «Usuarios» en el encabezado «Identidad» yendo a Identidad → Dominio → Seleccionar dominio → pestaña «Gestión de usuarios».

   Se puede observar que hay un usuario llamado « "CloudabilityDataCollector\_User" » que fue creado por la tarea de Terraform.

   Nota: Si no deseas que « Cloudability » cree un usuario local y, en su lugar, prefieres tener un usuario «federado», consulta «[Federación de un usuario para la acreditación de OCI](oci-credentialing.html) ».
3. Selecciona «Grupos» en el encabezado «Identidad ». Si estás utilizando Identity Domain, tendrás que seleccionar Dominios en el encabezado de Identity, y a continuación seleccionar Dominio predeterminado, Gestión de usuarios y, por último, Grupos. Se puede observar un grupo llamado « "CloudabilityDataCollector\_Group" » que fue creado por la tarea de Terraform.
4. Selecciona « CloudabilityDataCollector\_Group » para comprobar si « CloudabilityDataCollector\_User » se ha añadido a este grupo como miembro del grupo.
5. En la sección «Información del grupo », copia el OCID del grupo y guárdalo. Esta información deberá pegarse más adelante en la interfaz de usuario de « Cloudability ».

   ![](../../../../03-media/cloudability-premium/images/OCI-user-groups-.png)
6. Selecciona «Políticas» en el encabezado «Identidad».

   ![Captura de pantalla de las políticas de Terraform de OCI](../../../../03-media/cloudability-premium/images/validating_oci_3.jpg)

   Se puede observar la política denominada « "CloudabilityCostDataReaderPolicy" », creada por la tarea de Terraform. Esta política incluye todas las políticas necesarias para obtener datos del entorno del cliente. No es posible modificar el nombre de esta política.

Generar la clave de API

1. Selecciona «Identidad y seguridad» en el menú de navegación situado en la esquina superior izquierda del panel de control.
2. Selecciona «Usuarios» en el encabezado «Identidad» yendo a Identidad → Dominio → Seleccionar dominio → pestaña «Gestión de usuarios».

   Nota: Si estás utilizando el módulo «Identity Domain », selecciona «Dominios» en el encabezado «Identidad» y, a continuación, selecciona «Dominio predeterminado» y «Usuarios ».
3. Selecciona el usuario llamado « "CloudabilityDataCollector\_User" ».
4. Selecciona «Claves de API» → «Añadir clave de API»

   ![](../../../../03-media/cloudability-premium/images/OCI-api-key.png)
5. Selecciona «Generar par de claves API ».

   ![](../../../../03-media/cloudability-premium/images/OCI-generate-api-key.png)
6. Selecciona «Descargar clave privada ». Tendrás que pegarlo más tarde en la interfaz de usuario de « Cloudability ».
7. Selecciona «Descargar clave pública ».
8. Selecciona «Añadir» y se generará la huella dactilar.
9. Selecciona el archivo «Ver configuración ».

   ![Captura de pantalla de la configuración de la vista de Terraform de OCI](../../../../03-media/cloudability-premium/images/generating__api_oci_3.jpg)

Paso 2: En « Cloudability » (Gestión de la información de los usuarios), añade la información en la interfaz de usuario de « Cloudability » (Gestión de la información de los usuarios)

1. En Cloudability, ve a Configuración > Credenciales de proveedor > Añadir fuente de datos > OCI. Se abre el panel «Añadir cuenta OCI ».

   O

   En Cloudability, ve a Configuración > Credenciales de proveedor > OCI. Selecciona «Añadir una credencial ». Se abre el panel «Añadir una credencial ».

   Pega la información en el archivo de configuración tal y como se indica a continuación:
   - Región de origen : aparece junto a «región» en el archivo de configuración
   - ID de usuario : aparece junto a «usuario» en el «archivo de configuración ».
   - ID de grupo : Esta información se guardó en el paso anterior. Puedes encontrar este OCID accediendo a Identidad y seguridad > Grupos > « CloudabilityDataCollector\_Group ».
   - Espacio de nombres : este es tu espacio de nombres OCI; introduce el espacio de nombres configurado.
   - Huella digital : Se muestra directamente en el  archivo de configuración  .
   - Contraseña : Se puede dejar en blanco.
   - Clave privada : esta información se guardó en el paso anterior.

     Nota: Asegúrate de pegar la clave privada íntegra en Cloudability, incluyendo «-----BEGIN PRIVATE KEY----» y «-----END PRIVATE KEY----».
2. Selecciona «Guardar ».
3. Selecciona «Verificar credenciales ».

   Nota: Asegúrate de seleccionar «Guardar» antes de seleccionar «Verificar credenciales» para evitar que aparezcan mensajes de error.

Si la información se ha verificado correctamente, aparecerá una marca de verificación verde debajo de «Informes de facturación ». También aparecerá una marca de verificación verde debajo de «Funciones avanzadas », pero solo para la tenencia raíz.

Una vez finalizado este proceso, en unas pocas horas,

- Cloudability Empezará a mostrar tus datos de facturación y tus etiquetas de OCI en Cloudability.
- También se recopilarían datos sobre precios
- Cloudability también mostrará los contratos de alquiler secundarios de OCI.

El siguiente paso consiste en configurar las credenciales de los tenancies secundarios de OCI.

Una vez que veas tus datos de OCI, puedes proceder a actualizar tus etiquetas y asignaciones comerciales; puedes obtener más información al respecto en la [publicación de la comunidad Apptio](https://community.apptio.com/blogs/soline-plichta/2023/09/14/cloudability-for-oci-cost-management-faq "(se abre en una pestaña o una ventana nueva)").

Paso 3 - En « Cloudability » (Gestión de la propiedad): añadir datos de acceso para tus subarrendamientos

Una vez verificadas tus credenciales, Cloudability detectará automáticamente tus subarrendamientos y los mostrará en la interfaz de usuario. Pasa el cursor por encima de los tres puntos situados a la derecha del contrato de alquiler de tu hijo y selecciona el botón con el símbolo del «lápiz».

![OCI Terraform: añadir credenciales para la captura de pantalla secundaria](../../../../03-media/cloudability-premium/images/oracle-cloud-adding-credentials-child-tenancies.jpg)

A continuación, puedes empezar a dar de alta los contratos de alquiler de tus hijos, siguiendo el mismo proceso descrito anteriormente para los contratos de alquiler de los padres.

**Verificar credenciales** **mediante acciones masivas**

Para verificar varias cuentas rápidamente, haz clic en el botón «Acciones masivas». Esta pantalla muestra todas las cuentas, excepto aquellas que tienen el estado «Se requieren credenciales» (X).

1. Selecciona las cuentas que deban verificarse.
2. Haz clic en **«Revisar selección»**
3. Haz clic en **«Verificar».**

Esto activaría el proceso de verificación masiva y el botón de acciones masivas quedaría desactivado hasta que finalizara el proceso.

Una vez completadas, las cuentas pasarán a tener el estado «Verificada y acreditada» o «Acreditación no válida» (debido a errores).

Nota: Si el número de cuentas es muy elevado, este proceso puede tardar unos minutos.

Tardará hasta 48 horas en aparecer tu información de utilización en Cloudability y en empezar a recibir recomendaciones de ajuste de recursos.

Lista de permisos

A continuación encontrarás la lista de permisos que aparecen en los detalles de las credenciales de OCI. Algunas de ellas solo son aplicables a la cuenta principal o al contrato de alquiler, y no a la cuenta secundaria o al contrato de alquiler secundario ( “oci.get.costReports”, « oci.list.tenancies » y “oci.list.rateCards” ).

| Permiso | Descripción | Aplicable a la cuenta principal/contrato de alquiler | Aplicable a la cuenta o contrato de alquiler del menor |
| --- | --- | --- | --- |
| oci.get.costReports | Permiso para recuperar el informe de costes | Sí | No |
| oci.list.tenancies | Autorización para dar de alta un contrato de alquiler secundario a partir del contrato principal | Sí | No |
| oci.get.metrics | Permiso para obtener métricas | Sí | Sí |
| oci.list.rateCards | Autorización para publicar las tarifas | Sí | No |
| oci.list.assignedSubscriptions | Permiso para mostrar las suscripciones asignadas | Sí | Sí |
| oci.list.computeShapes | Permiso para enumerar formas de cálculo | Sí | Sí |
| oci.list.computeImages | Permiso para listar imágenes de cálculo | Sí | Sí |
| oci.list.imageShape.Compatibility | Permiso para enumerar las formas de las imágenes | Sí | Sí |
| oci.get.instanceFamily | Permiso para leer la familia de instancias | Sí | Sí |
| oci.list.policies | Política de permisos de lectura para fines de verificación | Sí | Sí |

- **[Federación de un usuario para la acreditación en OCI](../admin/oci-credentialing.html)**
