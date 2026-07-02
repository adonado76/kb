---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Configure las credenciales de IBM Cloud utilizando el método Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar IBM Cloud"
source_path: "product/setup_ibm_cloud_credentials_using_cldy_method.html"
images:
  - "images/ibm1.jpg"
  - "images/ibm10.jpg"
  - "images/ibm11.jpg"
  - "images/ibm12.jpg"
  - "images/ibm13.jpg"
  - "images/ibm14.jpg"
  - "images/ibm15.jpg"
  - "images/ibm16.jpg"
  - "images/ibm17.jpg"
  - "images/ibm18.jpg"
  - "images/ibm19.jpg"
  - "images/ibm2.jpg"
  - "images/ibm20.jpg"
  - "images/ibm21.jpg"
  - "images/ibm22.jpg"
  - "images/ibm23.jpg"
  - "images/ibm24.jpg"
  - "images/ibm25.jpg"
  - "images/ibm26.jpg"
  - "images/ibm3.jpg"
  - "images/ibm4.jpg"
  - "images/ibm5.jpg"
  - "images/ibm6.jpg"
  - "images/ibm7.jpg"
  - "images/ibm8.jpg"
  - "images/ibm9.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configure las credenciales de IBM Cloud utilizando el método Cloudability

## Resumen

Conecte o acredite sus cuentas de IBM Cloud a Cloudability para permitir la ingestión de datos de costes y uso. Este documento se centra en el método Cloudability y proporciona una guía paso a paso para configurar un espacio de trabajo IBM Cloud utilizando Terraform. El espacio de trabajo se utilizará para desplegar infraestructura utilizando configuraciones de Terraform alojadas en un repositorio de GitHub.

## Prerrequisito

Habilitación de su cuenta IBM para exportar datos de uso

Antes de poder habilitar tu cuenta IBM para exportar datos de uso, necesitas tener rol de administrador o editor en el servicio de gestión de cuentas de facturación. Para más información, consulte [Acceso IAM](https://cloud.ibm.com/docs/account?topic=account-userroles "(se abre en una pestaña o una ventana nueva)").

Para habilitar su cuenta para exportar datos de uso, siga estos pasos:

1. En la consola IBM Cloud, vaya a Gestionar > Facturación y uso, y seleccione Configuración.
2. Haz clic en Conectar.
3. Seleccione una Cloud Object Storage instancia y Cubo. Al seleccionar estos, está eligiendo qué cubo almacenará sus informes de uso.
   - Opcional: Si no desea seleccionar una instancia existente, haga clic en Seleccionar una instancia > Crear nueva.
   - Opcional: Seleccione un cubo o cree uno nuevo haciendo clic en Crear nuevo cubo en el desplegable. Para más información, consulte [Introducción a IBM Cloud Object Storage](https://cloud.ibm.com/docs/cloud-object-storage?topic=cloud-object-storage-getting-started-cloud-object-storage "(se abre en una pestaña o una ventana nueva)").
4. Para autorizaciones de servicio a servicio, haga clic en Autorizar. Para el acceso requerido, seleccione Object Writer y Content Reader. Haga clic en Revisar y, a continuación, en Asignar.
5. Haga clic en Conectar después de revisar los detalles de su carpeta.

Referencia: [Exporta tus datos de uso para obtener información continua](https://cloud.ibm.com/docs/billing-usage?topic=billing-usage-exporting-your-usage&interface=ui "(se abre en una pestaña o una ventana nueva)")

Copiar los detalles de la cuenta en la que está configurada Enterprise

Copiar ID de empresa:

1. Vaya a Gestionar.
2. Seleccione Empresa en el menú desplegable.

   ![captura de pantalla de ibm enterprise](../../../../03-media/cloudability-premium/images/ibm1.jpg)
3. Acceda al Panel de control y localice el campo ID.

   ![ibm enterprise dashboard captura de pantalla](../../../../03-media/cloudability-premium/images/ibm2.jpg)

Copiar ID de cuenta

1. Vaya a Gestionar.
2. Haga clic en Empresa en el menú desplegable y seleccione Cuentas.
3. Identifique la cuenta etiquetada como "Esta cuenta es la cuenta de empresa" y copie su ID.

   ![ibm enterprise cpoy account id captura de pantalla](../../../../03-media/cloudability-premium/images/ibm3.jpg)

Copiar detalles de cuenta para la cuenta donde Enterprise no está configurado

Copiar ID de cuenta:

1. Vaya a Gestionar.
2. Haga clic en Cuenta en el menú desplegable y, a continuación, seleccione Configuración de la cuenta.
3. Copia su ID.

   ![Captura de pantalla de la configuración de la cuenta empresarial de IBM](../../../../03-media/cloudability-premium/images/ibm4.jpg)

   ![ibm enterprise account settings 2 captura de pantalla](../../../../03-media/cloudability-premium/images/ibm5.jpg)

Copiar nombre de instancia de almacenamiento

1. Acceda al menú de navegación IBM Cloud.
2. Vaya a Lista de recursos y seleccione Almacenamiento.
3. Seleccione la Cloud Object Storage instancia que contiene el Cubo donde se exporta el Informe de uso.

   ![ibm enterprise copy storage captura de pantalla](../../../../03-media/cloudability-premium/images/ibm6.jpg)

   ![ibm enterprise copy storage 2 captura de pantalla](../../../../03-media/cloudability-premium/images/ibm7.jpg)

Copiar nombre de cubo y región de cubo

1. Acceda al menú de navegación IBM Cloud.
2. Vaya a Lista de Recursos, seleccione Almacenamiento y luego elija Instancia de Almacenamiento.
3. Busque la sección Buckets y seleccione el Bucket donde se exporta el Informe de Uso.
4. Vaya a Configuración y copie el Nombre del cubo y la Ubicación (Región).

   ![ibm enterprise copy bucket nombre captura de pantalla](../../../../03-media/cloudability-premium/images/ibm8.jpg)

Prefijo del coste de copia

1. Acceda al menú de navegación IBM Cloud.
2. Vaya a Lista de Recursos, seleccione Almacenamiento y luego elija Instancia de Almacenamiento.
3. Busque la sección Buckets y seleccione el Bucket donde se exporta el Informe de Uso.
4. Acceda al menú de navegación IBM Cloud y seleccione el Cubo donde se exportará el Informe de uso.

Copie el prefijo situado entre el Nombre del cubo y el nombre de la carpeta (que contiene el año y el mes; por ejemplo, 2023-10), excluyendo tanto el Nombre del cubo como el nombre de la carpeta Año-Mes.

![ibm enterprise copy cost prefix captura de pantalla](../../../../03-media/cloudability-premium/images/ibm9.jpg)

Copia Informe de costes Nombre

1. Acceda al menú de navegación IBM Cloud.
2. Vaya a Lista de Recursos, seleccione Almacenamiento y luego elija Instancia de Almacenamiento.
3. Busque la sección Buckets y seleccione el Bucket donde se exporta el Informe de Uso.
4. Acceda al menú de navegación IBM Cloud y seleccione el Cubo donde se exportará el Informe de uso.
5. Navegue a cualquier carpeta Año-Mes y copie el nombre de archivo llamado 'manifest' (el nombre de archivo por defecto es manifest).

   ![captura de pantalla del informe de costes de copia de ibm enterprise](../../../../03-media/cloudability-premium/images/ibm10.jpg)

   Nota:

   No copie la extensión del nombre del archivo. Debería ser simplemente "manifiesto" y no manifest.json.

## Generar plantilla Terraform a partir de Cloudability

1. Asegúrese de que todos los datos estén copiados y sean fácilmente accesibles.
2. Inicie sesión en Cloudability UI y vaya a Configuración: Credenciales de proveedor: Haga clic en "Añadir fuente de datos" y seleccione " IBM ".

   ![captura de pantalla de la plantilla ibm enterprise terraform](../../../../03-media/cloudability-premium/images/ibm11.jpg)
3. En el panel lateral Añadir cuenta IBM, haga clic en Siguiente.
4. Introduzca todos los datos copiados anteriormente y haga clic en Generar plantilla.

   Nota:

   El nombre del informe de costes no debe tener la extensión de nombre de archivo (.json).

   ![ibm enterprise añadir cuenta ibm captura de pantalla](../../../../03-media/cloudability-premium/images/ibm12.jpg)

## Ejecución del Terraform

Requisitos previos para Terraform

1. Asegúrese de que Terraform se ha descargado y está alojado en un repositorio como GitHub.

   Nota: Si tu repositorio de GitHub es privado, tendrás que generar un token de acceso personal (PAT) tal y como se describe aquí.
2. Además, asegúrese de que tiene acceso de Propietario de Cuenta o Administrador de Servicio y acceso de Plataforma de Administrador para el Servicio de Esquemas en su Acceso IAM.

Nota: El Terraform descargado también se puede ejecutar mediante la CLI local

Pasos para la ejecución

**Paso 1: Conéctese a IBM Cloud**

1. Vaya a la página de inicio de sesión IBM Cloud.
2. Introduzca sus credenciales de IBM Cloud e inicie sesión en su cuenta de IBM Cloud.

**Paso 2: Acceder a los esquemas y crear un espacio de trabajo**

1. Después de iniciar sesión, acceda al menú Navegación dentro de IBM Cloud.
2. En el menú Navegación, seleccione Esquemas.
3. Haga clic en Espacios de trabajo para acceder a la interfaz de gestión de espacios de trabajo.

   ![ibm enterprise access schematics captura de pantalla](../../../../03-media/cloudability-premium/images/ibm13.jpg)

**Paso 3: Configurar el espacio de trabajo**

1. Haga clic en Crear espacio de trabajo para iniciar el proceso de creación del espacio de trabajo.

   ![ibm enterprise create workspace captura de pantalla](../../../../03-media/cloudability-premium/images/ibm14.jpg)
2. Proporcione el repositorio GitHub URL donde están alojados sus archivos de configuración de Terraform.
3. Si su repositorio GitHub es privado, proporcione el Token de Acceso Personal (PAT) que generó durante los requisitos previos.

   Referencia: [Gestión de sus claves de acceso personales](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-fine-grained-personal-access-token "(se abre en una pestaña o una ventana nueva)")
4. Seleccione la última versión de Terraform, en este caso, terraform\_v1.5.

   Nota:

   La versión de Terraform debe ser v1.5 y superior.
5. Haga clic en Siguiente para continuar.

   ![ibm enterprise schematics captura de pantalla](../../../../03-media/cloudability-premium/images/ibm15.jpg)

**Paso 4: Definir variables**

1. Asigne un nombre a su espacio de trabajo, por ejemplo, 'CldyWorkspace'.
2. En Etiquetas, añada una etiqueta llamada "createdFor" con el valor 'Cldy'.
3. Deje el grupo de recursos como "Predeterminado".
4. Elija una ubicación para su espacio de trabajo, ya que determina dónde se ejecutarán las acciones del espacio de trabajo.
5. La descripción es opcional.
6. Haga clic en Siguiente para continuar.

   ![ibm enterprise definir variables captura de pantalla](../../../../03-media/cloudability-premium/images/ibm16.jpg)

**Paso 5: Aplicar el plan Terraform**

1. Haga clic en Crear para confirmar y crear el espacio de trabajo.
2. Se creará tu CldyWorkspace.

   ![ibm enterprise apply terraform plan captura de pantalla](../../../../03-media/cloudability-premium/images/ibm17.jpg)

**Paso 6: Acceder a los recursos creados**

1. Seleccione 'CldyWorkspace' en la lista de espacios de trabajo.
2. Vaya a Configuración para 'CldyWorkspace'.
3. En la sección Variables, expanda tres puntos (elipsis) y seleccione Editar.

   ![ibm enterprise access recursos creados captura de pantalla](../../../../03-media/cloudability-premium/images/ibm18.jpg)
4. Se creará tu CldyWorkspace. Proporcione su ibmcloud\_api\_key, que debe tener el acceso necesario para crear recursos IAM.

   Referencia: [Gestión de claves API de usuario](https://cloud.ibm.com/docs/account?topic=account-userapikey&interface=ui#create_user_key "(se abre en una pestaña o una ventana nueva)")
5. Seleccione la casilla Sensible si desea tratar este valor de variable como información sensible o secreta. Esto evita que se exponga en los detalles del espacio de trabajo, la salida CLI o la salida de registro.

   ![ibm enterprise información secreta captura de pantalla](../../../../03-media/cloudability-premium/images/ibm19.jpg)
6. Una vez configuradas las variables, vuelva a 'CldyWorkspace' y vaya a la sección Trabajos.
7. Haga clic en Aplicar plan para iniciar el despliegue de la configuración de Terraform.

   ![ibm enterprise apply plan captura de pantalla](../../../../03-media/cloudability-premium/images/ibm20.jpg)

   ![ibm enterprise log details captura de pantalla](../../../../03-media/cloudability-premium/images/ibm21.jpg)
8. Una vez que el plan Aplicar se haya ejecutado correctamente, podrá acceder a los recursos creados en la sección Gestionar.

   ![ibm enterprise access IAM captura de pantalla](../../../../03-media/cloudability-premium/images/ibm22.jpg)
9. Los roles personalizados se encuentran en Acceso (IAM) > Roles.

   ![ibm enterprise custom roles captura de pantalla](../../../../03-media/cloudability-premium/images/ibm23.jpg)
10. Con esto concluye que ha desplegado correctamente los recursos y puede gestionar el acceso y las funciones según sea necesario .

**Paso 7: Verificar las credenciales en Cloudability**

1. Una vez que el plan de terraformación se haya aplicado correctamente, vuelva a la interfaz de usuario Cloudability y haga clic en Verificar credenciales. La marca de verificación verde indica que el proceso de acreditación se ha realizado correctamente. 

   ![ibm enterprise verificar credenciales captura de pantalla](../../../../03-media/cloudability-premium/images/ibm24.jpg)

   **Verificar credenciales** **mediante acciones masivas**

   Para verificar varias cuentas rápidamente, haz clic en el botón Acciones masivas. Esta pantalla muestra todas las cuentas excepto aquellas con el estado «Se requieren credenciales» (X).

   1. Seleccione las cuentas que deben verificarse.
   2. Haga clic en **Revisar selección.**
   3. Haga clic en **Verificar.**

   Esto activaría el proceso de verificación masiva y el botón de acciones masivas se desactivaría hasta que el proceso finalizara.

   Una vez completadas, las cuentas pasarán a tener el estado «Credencial verificada» o «Credencial no válida» (debido a errores).

   Nota: Si el número de cuentas es muy grande, esto puede tardar unos minutos.

   Ejemplo de script Terraform

   (Cabecera ampliable)

   ![Captura de pantalla de Terraform de IBM Enterprise Sample](../../../../03-media/cloudability-premium/images/ibm25.jpg)

   ![ibm enterprise sample terraform captura de pantalla continuada](../../../../03-media/cloudability-premium/images/ibm26.jpg)

**Tema principal:** [Conectar IBM Cloud](../product/apptio_help_center_ibm_cloud.html)
