---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar con ServiceNow"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-servicenow-integration.html"
images:
  - "images/ServiceNow-Creds.jpeg"
  - "images/servicenow_integration-1.jpg"
  - "images/servicenow_integration-2.jpg"
  - "images/vc_ss8.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar con ServiceNow

**Visión general**

Esta guía le explica el proceso para conectar su **ServiceNow** cuenta a IBM Cloudability. Una vez conectado, podrás acceder a dentro ServiceNow de Cloudability.

**Requisitos previos**

Antes de empezar, asegúrate de lo siguiente:

- Usted es administrador de Cloudability.
- Su organización utiliza ServiceNow Cloud.
- El administrador de su instancia ServiceNow está disponible durante el proceso de configuración.
- Tiene el nombre de dominio para su instancia ServiceNow.

**ServiceNow** El proceso de acreditación de cuentas implica varios pasos que requerirán que usted realice acciones tanto en ServiceNow la consola como Cloudability en diversas fases.

Durante este proceso, Cloudability utilizaremos su ServiceNow dominio para conectarse con su cuenta.

**Paso 1 - ServiceNow Consola**

- Anote el nombre de dominio de su ServiceNow Cloud. por ejemplo https://xxxyyy.service-now.com

**Paso 2 - Cloudability**

En la consola Cloudability :

1. En Cloudability, vaya a **Configuración** > **Credenciales de proveedor** > **Añadir fuente de datos** > **ServiceNow**. Se abre el panel **Añadir cuenta ServiceNow**.
2. Introduzca el nombre de dominio de su **ServiceNow** instancia.

   Seleccione **Guardar**.
3. Haga clic en **Generar script y descargue el script**.

**Paso 3 - ServiceNow** **Consola**

1. En ServiceNow, vaya a **System Definitions** > **Fix Scripts**.
2. Haga clic en **Nuevo**.
3. Introduzca el nombre como Cldy Script.
4. Pega el script generado en el paso anterior en la sección **Script**.
5. Asegúrese de que la **aplicación** está configurada como **Global**.
6. Haga clic en **Enviar**.
7. Ir al **Script Cldy** creado.
8. Haga clic en **Ejecutar Script Fix y Proceder**.
9. Vaya a **Seguridad del sistema** > **Usuarios**.
10. Buscar el nombre **CldyUser\_Script**. Anote el **ID de usuario.**
11. Haga clic en **Establecer contraseña** y, a continuación, escriba y guarde la contraseña. Anote la contraseña si es necesario.

    ![Captura de pantalla de la integración de ServiceNow](../../../../03-media/cloudability-premium/images/servicenow_integration-1.jpg)
12. Accede a **Sistema OAuth** > **Registro de aplicaciones**.

    ![captura de pantalla del registro de aplicaciones](../../../../03-media/cloudability-premium/images/servicenow_integration-2.jpg)
13. Busca el nombre «**Cldy OAuth Client** ». Anote el **Id de cliente**.
14. Pulse el botón de bloqueo del **Secreto de Cliente**. Copiar el **secreto del cliente**.

![](../../../../03-media/cloudability-premium/images/ServiceNow-Creds.jpeg)

**Paso 4 - Cloudability**

Acceda a la Cloudability consola e introduzca los siguientes datos que se han recopilado en el paso anterior:

1. Introduzca el **ID de usuario**.
2. Introduzca la **contraseña**.
3. Introduzca el **ID de cliente**.
4. Introduzca el **Secreto de Cliente**.
5. Haga clic en **Guardar**.

   ![Captura de pantalla de edición de credenciales de ServiceNow](../../../../03-media/cloudability-premium/images/vc_ss8.jpg)

**Cómo confirmar el éxito**

Compruebe el estado en **Configuración > Credenciales de proveedor > ServiceNow**. Una marca verde indica que la integración se ha realizado correctamente.

**Preguntas más frecuentes**

**He seguido los pasos anteriores, pero el estado de mi cuenta sigue siendo rojo. ¿Qué debo hacer?**

Comprueba que has introducido los datos correctamente, por ejemplo, el nombre de dominio, el ID de usuario, la contraseña y ClientId el secreto del cliente.

**¿Cómo puedo editar los detalles de ServiceNow la integración?**

Haz clic en los tres puntos junto a la cuenta y selecciona «Editar». Añade los datos y guarda la credencial.

En caso de que el dominio haya cambiado, añada una nueva credencial siguiendo todos los pasos mencionados en esta integración. Por favor, elimine la cuenta antigua antes de hacerlo.
