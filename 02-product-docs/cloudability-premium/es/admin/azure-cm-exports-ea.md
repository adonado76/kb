---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conexión con Azure EA - Exportación de gestión de costes"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Microsoft Azure"
source_path: "admin/azure-cm-exports-ea.html"
images:
  - "images/Azure-EA-Enrollment-id.png"
  - "images/blobid0.jpg"
  - "images/blobid1.jpg"
  - "images/blobid5.jpg"
  - "images/blobid9.jpg"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image002_-821243953.png"
  - "images/new-create_a_new_csv_export.jpg"
  - "images/resource_group_name.jpg"
  - "images/updated_new_import.jpg"
  - "images/updated_storage_account.jpg"
  - "images/updated_tenant_id.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conexión con Azure EA - Exportación de gestión de costes

**Visión general**

Esta guía te explica paso a paso el proceso para vincular tu **Contrato Empresarial de Microsoft (EA)** a IBM Cloudability a través de las exportaciones de gestión de costes de Azure.

Azure Las exportaciones de gestión de costes ofrecen información detallada que incluye todos los datos brutos de facturación y consumo subyacentes a los costes y las etiquetas de recursos de Azure. Cloudability Para esta integración se necesitan un par de archivos:

- Detalles de costes y consumo (reales)

- Detalles de costes y uso (amortizados)

Una vez conectado, tendrás acceso a las funciones de « FinOps » en Cloudability.

Nota: Para garantizar una compatibilidad y un soporte técnicos óptimos, sigue los pasos de conexión tal y como se describen. No se admiten configuraciones personalizadas. Si tiene alguna pregunta, póngase en contacto con **el soporte IBM**.

**Requisitos previos**

Antes de empezar,

Asegúrate de que tienes uno de los siguientes roles en tu organización: Azure Active Directory :

- Administrador global o administrador de empresa.
- Responsable de matrículas o puesto equivalente para asignar el rol de lector de matrículas

Para el portal Azure, debe tener permisos otorgados por uno de estos [ámbitos Azure](https://docs.microsoft.com/en-us/azure/cost-management-billing/costs/understand-work-scopes "(se abre en una pestaña o una ventana nueva)") para crear la exportación de datos de facturación.

- Propietario (puede ver y gestionar todo, incluida la configuración de costes)

- Colaborador (puede ver y gestionar todo, incluida la configuración de costes, salvo el control de acceso)

- Colaborador en la gestión de costes (puede ver y gestionar la configuración de costes)

- Acceso de administrador a las credenciales de proveedor de Cloudability

**Primeros pasos:**

El proceso de acreditación de « Azure » de Cloudability consta de dos pasos principales:

- Azure Acreditación de cuentas de facturación

- Azure Acreditación de cuentas de suscripción

Azure El proceso de acreditación de la cuenta de facturación consta de varios pasos que requerirán que realices acciones tanto en el portal Azure como en Cloudability en distintas fases.

Durante este proceso, Cloudability :

- Añade el principal de servicio de Cloudability ( “CloudabilityUtilizationDataCollector” ) y asígnale el rol de “CloudabilityCostDataReader”.

- CloudabilityCostDataReader Esta función se utiliza para obtener los datos de costes y uso mediante [la función](https://learn.microsoft.com/en-us/azure/role-based-access-control/built-in-roles/storage#storage-blob-data-reader) "(se abre en una pestaña o una ventana nueva)") integrada «Storage Blob Data Reader» de Azure.

- Utiliza el rol «Enrollment Reader», que proporciona acceso de solo lectura a los datos de facturación de la empresa

Nota: Solo un usuario que tenga un rol de « EnrollmentReader » (escritor de inscripciones), como por ejemplo «Administrador de empresa» o «Administrador global» (o su equivalente), puede asignar un rol a un SPN.

**Paso 1 - Portal « Azure » - Crear una exportación de los detalles de costes de « Azure »**

Nota: Cloudability recomienda utilizar las exportaciones de Azure para la acreditación en Microsoft Azure.

Microsoft Azure También recomienda utilizar [las exportaciones](https://learn.microsoft.com/en-us/azure/cost-management-billing/automate/usage-details-best-practices "(se abre en una pestaña o una ventana nueva)") como buena práctica para conjuntos de datos de gran tamaño (más de 2 GB de un mes a otro).

1. En el portal « Azure », busca «Gestión decostes + Facturación» y selecciónalo de la lista para abrir la página «Ámbitos de facturación ». Por ejemplo:

   ![](../../../../03-media/cloudability-premium/images/blobid1.jpg)
2. En la página «Gestión de costes + Facturación », asegúrate de haber seleccionado el ámbito de facturación correcto. Si tienes varios, selecciona el ámbito en el que se concentra la mayor parte de tu gasto en la nube.

   ![](../../../../03-media/cloudability-premium/images/blobid0.jpg)
3. Desde la consola de «Gestión de costes + Facturación », selecciona «Exportaciones» en el panel de navegación para abrir la herramienta de exportación « Azure ».

   ![](../../../../03-media/cloudability-premium/images/blobid5.jpg)
4. Selecciona «Crear» para abrir la página de exportación y crear una nueva exportación de « CSV ».

   ![](../../../../03-media/cloudability-premium/images/new-create_a_new_csv_export.jpg)
5. Crear una nueva exportación para
   1. **Coste y consumo (reales)** :
      1. Tipo de datos: Costes y consumo (reales)
      2. Crea un prefijo de exportación, p. ej., g.: Cloudability, y, a continuación, haz clic en «cldy-actual-cost» para mostrar:
         1. Nombre de exportación: Nombre de archivo único definido por el cliente
         2. Versión del conjunto de datos: 1 de octubre de 2021
         3. Frecuencia: exportación diaria de los costes acumulados del mes hasta la fecha
         4. Descripción de la exportación: Opcional
      3. Pulse Guardar
      4. Haz clic en «Siguiente» para abrir la pestaña «Destino»
         1. Tipo de almacenamiento: almacenamiento de blobs de Azure
         2. Destino y almacenamiento: Selecciona si deseas utilizar una suscripción y un grupo de recursos ya existentes o crear otros nuevos
         3. Suscripción: Selecciona la suscripción de destino
         4. Cuenta de almacenamiento: Selecciona una cuenta de almacenamiento
         5. Contenedor: Introduce un nombre de contenedor válido que cumpla con tus normas de nomenclatura
         6. Directorio: Introduce un nombre de directorio válido que cumpla con tus normas de nomenclatura
         7. Formato: CSV
         8. Tipo de compresión: Ninguna o Gzip
         9. Partición de archivos: Mantener la selección predeterminada
         10. Sobrescribir datos: Mantener la selección predeterminada
      5. Pulse Siguiente
      6. En la pestaña «Revisar y crear», haz clic en «Crear»

         ![](../../../../03-media/cloudability-premium/images/updated_new_import.jpg)
   2. **Coste y consumo (amortizados)** :

      1. Sigue los mismos pasos que antes
      2. Asegúrate de que se utilicen la misma suscripción, el mismo contenedor de la cuenta de almacenamiento y el mismo directorio que en la creación de la exportación anterior
      3. Haz clic en «Revisar y crear»

         Nota: Los archivos con formato « CSV » son obligatorios para Cloudability y deben estar presentes en la cuenta de almacenamiento utilizada para recopilar datos de gestión de costes.

         No recomendamos utilizar la ingesta de datos de FOCUS para « Azure », ya que las exportaciones nativas de « Azure » de Cost Management proporcionan información mucho más detallada.
6. Asegúrate de que se apliquen los siguientes ajustes a la cuenta de almacenamiento configurada para las exportaciones:
   1. Ve a «Cuentas de almacenamiento» y selecciona la cuenta de almacenamiento que utilizas para Cloudability
   2. Selecciona «Seguridad y redes»
   3. Seleccionar «Redes»
   4. Pulse Gestionar
      1. En «Acceso a redes públicas», selecciona «Habilitar»
      2. En el apartado «Ámbito de acceso a la red pública», selecciona una de las siguientes opciones:
         1. Habilitar desde todas las redes, o
         2. Habilitar desde las redes seleccionadas
            1. En este caso, ponte en contacto con el servicio de asistencia de Cloudability para obtener un rango de direcciones IP que puedan incluirse en la lista blanca
   5. Pulse Guardar
   6. Selecciona «Seguridad y redes»
   7. Seleccionar cifrado
   8. Haz clic en «Ámbitos de cifrado»
   9. Indica un nombre para el ámbito de cifrado
   10. Tipo de cifrado
       1. Claves gestionadas por Microsoft (MMK)
   11. Cifrado de la infraestructura
       1. Activado o desactivado
   12. Pulse Crear
7. **Recopila los datos de facturación necesarios para configurar tus credenciales de Cloudability**

   Una vez que hayas creado las exportaciones de datos de facturación, Cloudability necesita información adicional de tu portal de Azure para la configuración de las credenciales de Cloudability, tal y como se indica a continuación:

   Puedes consultar la lista de todas las propiedades que necesita « Cloudability » en la consola de gestión de costes del portal « Azure »:

| Nombre de propiedad | Cómo encontrarlo |
| --- | --- |
| ID de inscripción | - Busca «**Gestión** de costes + Facturación» y selecciónalo de la lista para abrir la página «Resumen de gestión de costes + facturación». - Selecciona «Ámbitos de facturación» y haz clic en el ámbito de facturación correspondiente - **Ve a «Configuración», haz clic en «Propiedades»,** copia y guarda **tu ID de cuenta de** facturación (ID de inscripción) |
| ID de arrendatario | - Busca **«Microsoft Entra ID»** y selecciónalo para abrir la página de descripción general de « Active Directory ».  - Copia y guarda **el ID de** inquilino |
| ID de suscripción | - Busca **«Suscripciones» y** selecciónalo para abrir la página de suscripciones - En la lista de suscripciones de la misma cuenta de facturación, selecciona la suscripción - Copia **el «ID** de suscripción» en el que se crearon las exportaciones y guárdalo. |
| Nombre del grupo de recursos | En la página «Descripción general» de la cuenta de almacenamiento, haz clic en el enlace de la cuenta de almacenamiento para ver el nombre del grupo de recursos, tal y como se muestra en este ejemplo: |
| Nombre de la cuenta de almacenamiento  Nombre de contenedor  Nombre del directorio  Nombre de la exportación de costes  Nombre de exportación amortizado | - Busca «**Gestión** de costes + Facturación» y selecciónalo - Ve a «Exportaciones» en «Configuración» para ver una tabla con los datos de facturación de tu cuenta de almacenamiento. - Desplázate hacia la derecha y selecciona la cuenta de almacenamiento de tus datos de facturación para abrir la página «Resumen», donde podrás ver el   - Nombre de la cuenta de almacenamiento,   - Nombre del contenedor de almacenamiento,   - Nombre del directorio de almacenamiento,   - los nombres de los archivos de exportación tanto del «coste real» como del «coste amortizado»: |

**Paso 2 - Cloudability - Iniciar sesión con los datos de facturación**

Una vez que hayas recopilado la información que figura en la tabla, puedes introducirla en Cloudability para actualizar tu credencial de EA.

Cloudability utilizará esta información para generar un script de PowerShell. Cuando se ejecute el script desde Cloud Shell en el portal Azure o desde PowerShell (con el ámbito de tu inquilino), se creará una entidad de servicio y se concederán derechos a Cloudability a través del rol CloudabilityCostDataReader, con el fin de proporcionar acceso a la cuenta de almacenamiento.

1. En Cloudability, ve a
   1. **Configuración** > **Credenciales de proveedor** > **Añadir fuente de datos** > **AZURE**.
   2. Pulse Siguiente
   3. Selecciona «Acuerdo empresarial (EA)»: se abrirá el panel «**Añadir cuenta de Azure** ».O
   4. **Configuración** > **Credenciales de proveedor** > **Ingreso** > **AZURE**.
   5. Pulse Siguiente
   6. Selecciona «Acuerdo empresarial (EA) **»;** se abrirá el panel «Añadir credencial».
2. Introduce la información obtenida en el portal « Azure » en los campos correspondientes
   1. Introduce el número de identificación de inscripción de « Azure » (número de identificación de la cuenta de facturación)
   2. ID de arrendatario
   3. ID de suscripción
   4. Nombre del grupo de recursos
   5. Nombre de la cuenta de almacenamiento
   6. Nombre de contenedor
   7. Nombre de directorio
   8. Nombre de la exportación de costes
   9. Nombre de la exportación del coste amortizado
3. Selecciona **«Generar script de configuración»** para descargar el nuevo archivo de script.
4. Selecciona «**Cerrar** ».

Volverás más tarde para comprobar los cambios.

**PASO 3 - Portal « Azure » -** **Conceder acceso a « Cloudability » desde el portal « Azure »**

El siguiente paso consiste en conceder a Cloudability permiso de lectura sobre los datos de costes y uso de tu almacenamiento de Azure ejecutando el script de configuración en tu portal de Azure : Cloud Shell.

Para ejecutar el script:

1. Inicia sesión en el portal de Azure y selecciona el tenant correspondiente (el directorio de nivel superior en Azure para la inscripción de destino y donde se guardan tus exportaciones de gestión de costes).
2. Desde el portal Azure, abre el generador de scripts ( Cloud Shell ) y selecciona « PowerShell » como lenguaje de scripting.
3. Una vez que se haya iniciado el « Cloud Shell », selecciona **«Upload»** en el menú del terminal « Cloud Shell ».
4. Sube el archivo del script de configuración que se proporciona en Cloudability.

![](../../../../03-media/cloudability-premium/images/blobid9.jpg)

1. Ejecuta el script escribiendo:

   ./<YOUR\_SCRIPT\_NAME\_HERE>.ps1

**Paso 4 - Cloudability - Verificar las credenciales de la cuenta**

El último paso consiste en verificar tus credenciales actualizadas de EA en Cloudability.

1. Vuelve a la página de credenciales de Cloudability Azure en **Configuración > Credenciales de proveedores > AZURE**.
2. Selecciona los tres puntos situados a la derecha y elige «Editar» junto a tus datos de acceso **a EA**.
3. Selecciona **«Verificar credenciales»** en el panel que se abre.
4. Haz clic en el símbolo «…» situado junto a la cuenta que se está verificando y selecciona «Volver a verificar».

Una marca verde (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png)) indica que se ha realizado correctamente, mientras que un signo de exclamación rojo (![](../../../../03-media/cloudability-premium/images/clip_image002_-821243953.png)) indica que hay errores.

Una vez finalizado este proceso, en unas pocas horas,

- Cloudability Empezará a mostrar tus datos de facturación y las etiquetas « Azure » en Cloudability.
- También se incluirían los datos sobre precios.
- Cloudability también mostrará las suscripciones

El siguiente paso consiste en configurar las credenciales de las suscripciones.

Haz clic aquí para [configurar el « Azure : Rightsizing and Reserved Instance Planning»](azure-advanced-rightsizing.html) con el fin de acreditar las suscripciones de « Azure »

**Preguntas más frecuentes** 

1. **Hace poco he activado las exportaciones de gestión de costes de Azure y he iniciado sesión en Cloudability. ¿Cuánto tiempo tardaré en ver los datos en Cloudability?**Consulte la [documentación](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=ts-cloudability-cloudability-cost-usage-data-availability-in-reporting "(se abre en una pestaña o una ventana nueva)") sobre la disponibilidad de los datos de costes y uso
2. **Azure API de detalles de costes de «Exportaciones frente a Azure »: ¿cuál se debe utilizar para integrar Azure en Cloudability?**El uso de las exportaciones de « Azure » es el método recomendado por Microsoft. Se trata de un enfoque escalable, ya que, a medida que tu conjunto de datos crece, las exportaciones son capaces de gestionar conjuntos de datos más grandes. Azure La API de detalles de costes se puede utilizar para conjuntos de datos más pequeños.
3. **¿Se pueden importar datos históricos de costes en « Cloudability »? En caso afirmativo, ¿hasta cuándo se pueden incorporar los datos?** Sí, podemos hacerlo mediante exportaciones puntuales. Consulta con los equipos de asistencia de IBM y Cloudability cómo importar datos históricos.
4. **¿Se puede utilizar el formato FOCUS en lugar de las exportaciones de « Azure » para la integración?**Núm. Para una integración correcta en Cloudability y para importar datos sobre conceptos como el «Rightsizing», las «instancias reservadas» y el «plan de ahorro» Azure, recomendamos utilizar las exportaciones, ya que proporcionan información mucho más detallada.
5. **¿Dónde puedo encontrar las API de credenciales de proveedores de « Cloudability » para « Azure »?**Consulte: [Puntos finales de credenciales de proveedores Azure](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-standard/saas?topic=api-vendor-credentials-end-points-azure "(se abre en una pestaña o una ventana nueva)")
6. **¿Admite la exportación de costes en los perfiles de facturación y** **los departamentos?**Sí, podemos. Ponte en contacto con el equipo de asistencia de IBM Cloudability para obtener más información.

**Tema principal:** [Conectar Microsoft Azure](../admin/azure-cm-setup-premium.html)
