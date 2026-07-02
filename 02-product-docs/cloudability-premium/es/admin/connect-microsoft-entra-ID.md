---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Conectar Microsoft Entra ID"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "admin/connect-microsoft-entra-ID.html"
images:
  - "images/Picture16.png"
  - "images/Picture17.png"
  - "images/Picture18.png"
  - "images/Picture19.png"
  - "images/Picture20.png"
  - "images/Picture21.png"
  - "images/Picture22.png"
  - "images/Picture23.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar Microsoft Entra ID

Microsoft Entra ID (anteriormente conocido como Azure Active Directory ) es un servicio de Gestión de Identidades y Accesos (IAM) basado en la nube que actúa como Proveedor de Identidades ( IdP ). Autentica y verifica las identidades de usuarios, dispositivos y servicios para un acceso seguro a aplicaciones y recursos.

Antes de empezar, asegúrate:

- Usted es administrador de Cloudability.
- Tiene permisos de administrador en el arrendatario Microsoft Entra ID.

**Cómo se conecta Cloudability con su inquilino de Microsoft Entra ID**

- Para conectarse a su inquilino de Microsoft Entra ID, Cloudability registra su propia aplicación en el inquilino Entra ID que usted elija para acreditarse con Cloudability. A continuación, Cloudability crea un Service Principal en su tenant utilizando la app registrada.
- Para la autenticación, Cloudability utiliza la clave de acceso y la clave secreta de su aplicación, que son almacenadas y gestionadas por Apptio.
- Para acreditar Cloudability con su Microsoft Entra ID, descargue una secuencia de comandos power shell del módulo Vendor Credentials de Cloudability y ejecútela en el inquilino de Microsoft Entra ID al que desee acreditar.
- A continuación se muestra un ejemplo de script de Power Shell:

  ```
  $entraAppId = "8dd8d868-a85c-4607-acd4-491df5068a79" $cldyEntraObjectId = (Get-AzADServicePrincipal -ApplicationId $entraAppId).id if (!$cldyEntraObjectId) { New-AzADServicePrincipal -ApplicationId $entraAppId $cldyEntraObjectId = (Get-AzADServicePrincipal -ApplicationId $entraAppId).id } else { echo "Service principal already present, skipping new service principal creation" }
  ```
- Ejecutando este script en tu comando power shell registrarás la app de Cloudability (con el AppID como se menciona en la primera línea del script) en tu tenant y crearás el Service Principal usando la app. Si ya existe un Service Principal, se omitirá la creación de un nuevo Service Principal y se reutilizará el Service Principal existente.
- Finalmente, deberá agregar los permisos *User.ReadBasic.All* y *GroupMember Read.All* al principal de servicio.

  Nota: Para acreditar Cloudability con su ID de Entra, no necesita realizar ninguna otra acción en su entorno Azure aparte de ejecutar el script power shell como se mencionó anteriormente y otorgar los permisos requeridos.

**Pasos detallados**

1. Vaya a **Configuración > Credenciales de proveedor**.
2. Haga clic en el botón **Add Datasource** y seleccione **Microsoft Entra ID**.

   ![Grupo de usuarios](../../../../03-media/cloudability-premium/images/Picture16.png)
3. Haga clic en **Siguiente** en el menú desplegable.

   ![grupo de usuarios](../../../../03-media/cloudability-premium/images/Picture17.png)
4. Proporcione el ID de arrendatario para el arrendatario específico de Azure Entra ID que desea acreditar con Cloudability y haga clic en **Guardar**.

   ![grupos de usuarios](../../../../03-media/cloudability-premium/images/Picture18.png)
5. Seleccione **Descargar script**.

   ![entraid descargar ss](../../../../03-media/cloudability-premium/images/Picture19.png)
6. Ejecute el script descargado en el tenant específico Azure Entra ID.
7. Agregue los permisos *User.ReadBasic* *Read.All GroupMember* a la entidad de servicio. Siga estos pasos para añadir los permisos:
   1. Busque "CloudabilityGroupReaderApp" en la barra de búsqueda del portal Azure.
   2. Una vez dentro de la aplicación, vaya a la sección Permisos en Gestionar.
   3. Haga clic en **Conceder consentimiento de administrador para Directorio predeterminado**.
   4. Una vez concedida la autorización, podrá ver los permisos en la lista que se muestra a continuación.

      ![grupos de usuarios](../../../../03-media/cloudability-premium/images/Picture20.png)
8. Una vez que la secuencia de comandos se haya ejecutado correctamente, vaya a **Configuración > Credenciales de proveedor > ficha ID de Microsoft Entra**. La credencial se mostrará con una **marca amarilla** que indica que aún no se ha verificado. Ampliar la **...** y seleccione la opción **Editar**.

   ![grupos de usuarios](../../../../03-media/cloudability-premium/images/Picture21.png)
9. Haga clic en el botón **Verificar credenciales** de la presentación.

   ![grupos de usuarios](../../../../03-media/cloudability-premium/images/Picture22.png)
10. Si se verifica, la credencial se mostrará con una **marca verde**.

    ![grupos de usuarios](../../../../03-media/cloudability-premium/images/Picture23.png)
