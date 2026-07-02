---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conexión con Azure MCA - API de detalles de costes"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Microsoft Azure"
source_path: "admin/azure-cmapi-mca.html"
images:
  - "images/Azure-MCA-Cost-Details-API.png"
  - "images/Azure-PowerShell-Upload.jpg"
  - "images/CLDY-Vendor-Creds-Azure-Verified.png"
  - "images/billing-mca-property.png"
  - "images/clip_image001_-1832790195.png"
  - "images/clip_image002_-821243953.png"
  - "images/copy-subscription-id.png"
  - "images/copy-tenant-id.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conexión con Azure MCA - API de detalles de costes

**Descripción general**

Esta guía te explica paso a paso cómo conectar de forma segura tu entorno MCA de Azure a IBM Cloudability a través de las API de detalles de costes de Azure.

La API de detalles de costes es un mecanismo alternativo de acreditación para los clientes de Azure. Una vez conectado, podrás acceder a la experiencia « FinOps » en Cloudability. En este proceso, crearemos un «Service Principle» en tu cuenta de Azure, lo que permitirá a Cloudability obtener los datos de facturación.

Nota: Cloudability recomienda utilizar las exportaciones de Azure para la acreditación en Microsoft Azure. Haz clic [aquí](azure-cm-ea.html) para configurar las exportaciones de Azure. Microsoft Azure También recomienda utilizar [las exportaciones](https://learn.microsoft.com/en-us/azure/cost-management-billing/automate/usage-details-best-practices "(se abre en una pestaña o una ventana nueva)") como buena práctica para conjuntos de datos de gran tamaño. (Más de 2 GB al mes)

Para garantizar una compatibilidad y un soporte técnicos completos, sigue los pasos de conexión tal y como se describen. No se admiten configuraciones personalizadas. Si tiene alguna pregunta, póngase en contacto con **el soporte IBM**.

**Requisitos previos**

Antes de empezar, asegúrate de tener acceso a:

- Azure Portal de la MCA

- Rol de «Administrador de empresa» (o, como mínimo, «Responsable de inscripciones», o el equivalente en su organización) en Azure

- Acceso de administrador a la página «Credenciales de proveedores» de Cloudability

El proceso de acreditación de la API de « Azure » de Cloudability requiere dos pasos principales:

- Acreditación de cuentas de facturación

- Acreditación de suscripciones

**Acreditación de cuentas de facturación**

Cloudability Utiliza las credenciales de la cuenta de facturación para importar los datos de costes y uso de Azure, a nivel de recurso, así como las etiquetas de los grupos de recursos correspondientes a las cuentas de facturación con credenciales.

El proceso de acreditación consta de varios pasos que requerirán que realices algunas acciones tanto en el portal Azure como en Cloudability en distintas fases.

Empecemos con el proceso de acreditación:

1. **En el portal « Azure »:**

   1. Busca tu **número de identificación de la cuenta de facturación** (número de inscripción).
      1. Busca «**Gestión** de costes + Facturación» y selecciónalo de la lista para abrir la página «Resumen de gestión de costes + facturación».
      2. Selecciona el ámbito de facturación
      3. **Ve a «Configuración», haz clic en «Propiedades»,** copia y guarda **el ID** de tu cuenta de facturación (ID de inscripción).

         ![](../../../../03-media/cloudability-premium/images/billing-mca-property.png)
   2. Busca tu **número de inquilino**
      1. Busca «**Microsoft Entra ID** » y selecciónalo para abrir la página de descripción general de « Active Directory ».
      2. Copia y guarda el **ID de inquilino**

         ![](../../../../03-media/cloudability-premium/images/copy-tenant-id.png)
   3. Consigue tu **ID de suscripción**
      1. De la lista de suscripciones asociadas a la misma cuenta de facturación.
      2. Copia uno de los **ID de suscripción** y guárdalo.

         ![](../../../../03-media/cloudability-premium/images/copy-subscription-id.png)
2. **En Cloudability : configurar las credenciales de la cuenta de facturación de Azure**

   Debes tener derechos de administrador de « Cloudability » para completar este procedimiento.

   Si no dispones de derechos de administrador, ponte en contacto con el administrador principal de Cloudability de tu organización para que te ayude.

   1. En Cloudability, ve **a**  Configuración >  **Credenciales de proveedor**  >  **Añadir fuente de datos y selecciona Azure - EA**
   2. Introduce el **ID de inscripción de** Azure (ID de la cuenta de facturación), el ID de inquilino y el ID de suscripción
   3. Introduce «**NA** » en todos los demás campos.
   4. Haz clic en **«Generar script de configuración».**
   5. Se descargará un script de « PowerShell ».![](../../../../03-media/cloudability-premium/images/Azure-MCA-Cost-Details-API.png)
3. **En el portal « Azure »: sube el script « PowerShell »**

   El siguiente paso consiste en conceder a Cloudability permiso de lectura sobre los datos de costes y uso de tu almacenamiento de Azure ejecutando el script de configuración en tu portal de Azure : Cloud Shell.

   1. Ejecuta el script « PowerShell » en la consola de PowerShell (o de forma nativa)
   2. Para ejecutar el script:
      1. Inicia sesión en el portal Azure y cambia al tenant correspondiente
      2. Desde el portal Azure, abre el generador de scripts ( Cloud Shell ) y selecciona « PowerShell » como lenguaje de scripting.
      3. Una vez que se haya iniciado el « Cloud Shell », selecciona **«Upload»** en el menú del terminal « Cloud Shell ».

         ![](../../../../03-media/cloudability-premium/images/Azure-PowerShell-Upload.jpg)
      4. Sube el archivo del script de configuración que se proporciona en Cloudability.
      5. Ejecuta el script escribiendo:

         Nota:

         >: ./<YOUR\_SCRIPT\_NAME\_HERE>.ps1
   3. Este script de PowerShell creará un principio de servicio denominado «**CloudabilityUtilizationDataCollector** ».

      Nota: Esto debería añadir el rol «Billing Account Reader» al sujeto de servicio « Cloudability »
4. **En Cloudability : comprueba las credenciales de la cuenta de facturación**
   1. En Cloudability, vaya a **Configuración > Credenciales de proveedor > Azure.**
   2. Haz clic en el símbolo «…» situado junto a la cuenta que se está verificando y selecciona «Volver a verificar».
      1. Una marca verde (![](../../../../03-media/cloudability-premium/images/clip_image001_-1832790195.png)) indica que se ha realizado correctamente, mientras que un signo de exclamación rojo (![](../../../../03-media/cloudability-premium/images/clip_image002_-821243953.png)) indica que hay errores

En caso de que la verificación falle, vuelve a intentarlo dentro de 15 minutos.

Una vez finalizado este proceso, en unas pocas horas,

- Cloudability Empezará a mostrar tus datos de facturación y las etiquetas « Azure » en Cloudability.
- También se incluirían los datos sobre precios.
- Cloudability también mostrará las suscripciones

El siguiente paso consiste en configurar las credenciales de las suscripciones.

![](../../../../03-media/cloudability-premium/images/CLDY-Vendor-Creds-Azure-Verified.png)

**Acreditación de cuentas de suscripción**

Como siguiente paso, sigue las instrucciones de **«Configuración de credenciales avanzadas», « Azure : ajuste de la capacidad» y «Planificación de instancias reservadas** ». La configuración de estos permisos permitirá incorporar las etiquetas de suscripción de Azure y los datos de uso, lo que resulta útil para utilizar las funciones de Optimize de Cloudability.

**Preguntas más frecuentes**

1. **No veo ningún dato sobre los costes tras completar los pasos para la acreditación de la cuenta, ¿qué debo hacer?**

   Comprueba, por favor, si la cuenta se ha verificado correctamente (aparece una marca verde). Si es así, espera 24 horas a que se reciban los datos; de lo contrario, ponte en contacto con el equipo de asistencia de Cloudability.

   Si la cuenta no está verificada (¡aparece en rojo!), Por favor, comprueba de nuevo las configuraciones y verifica que todos los datos sean correctos Y que el script se haya ejecutado en tu entorno.
2. **Hace poco activé Azure y configuré las credenciales de las cuentas en Cloudability. ¿Cuánto tiempo tardaré en ver los datos de costes y uso?**

   Pueden pasar hasta 24 horas hasta que se muestren tus primeros datos de costes en Cloudability.
3. **¿Cómo puedo actualizar a la última plantilla de PowerShell para los permisos?**

   Esto se puede hacer a través de Cloudability, en la sección «Gestionar credenciales» ( Azure ).

   1. Para regenerar la plantilla PowerShell y reconfigurar tu acceso a Azure, sigue estos pasos:

      1. En Cloudability, vaya a **Configuración > Credenciales de proveedor > Azure**.
      2. Guarda y descarga la plantilla actual de « **PowerShell** ».
      3. En el portal de « Azure », instala la plantilla.
      4. Una vez realizada la actualización correctamente, vuelve a verificar la cuenta.
4. **¿Podemos importar datos históricos de costes en Cldy? En caso afirmativo, ¿hasta cuándo se pueden importar los datos?**

   Sí, podemos. Las API de detalles de costes permiten recuperar datos de los últimos 13 meses.

   Para cualquier consulta relacionada con los datos históricos, envía una solicitud de asistencia.
5. **¿Cuándo debo utilizar la API de detalles de costes para Azure?**

   Se recomienda utilizar la API de detalles de costes de Azure para conjuntos de datos más pequeños, preferiblemente de menos de 2GB.
6. **En primer lugar, ¿qué volumen de datos históricos aportará Cloudability?**

   Cloudability mostrará los datos de costes del mes actual y de los meses anteriores.
7. **¿Cómo puedo pasar de la API de detalles de costes de Azure a las exportaciones de detalles de Azure?**

   Esto implicaría tener que volver a autenticar las cuentas. Sigue los pasos de acreditación para las exportaciones de « Azure ».
8. **¿Se recomienda modificar el contenido del script « PowerShell » generado por Cloudability?**

   No se recomienda este enfoque, ya que para que « Cloudability » funcione correctamente es necesario aplicar el principio de servicio y asignar los roles dentro del script « PowerShell ». No se admite ningún cambio en el guion.

**Tema principal:** [Conectar Microsoft Azure](../admin/azure-cm-setup-premium.html)
