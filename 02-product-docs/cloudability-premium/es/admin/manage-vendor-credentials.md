---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Gestionar las credenciales de los proveedores en Cloudability"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
  - "Credenciales del proveedor"
source_path: "admin/manage-vendor-credentials.html"
images:
  - "images/archivecredential.png"
  - "images/deleting__a_credential_19_34_am_png.jpg"
  - "images/regenerate_cloudability_more_options.jpg"
  - "images/reverify-cloudability-icon.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gestionar las credenciales de los proveedores en Cloudability

Descripción general

Esta página proporciona información sobre cómo gestionar las credenciales de proveedor en Cloudability.

Requisitos previos 

- Acceso de administrador a Cloudability Credenciales de vendedor
- Las cuentas de proveedores deben acreditarse en Cloudability

**Cómo empezar**

Para gestionar las credenciales, haga clic en... en la parte derecha de la cuenta y haga clic en una de las opciones:

- Volver a verificar las credenciales
- Credenciales de archivo
- Suprimir credenciales

Volver a verificar una credencial

Volver a verificar las credenciales implica comprobar las conexiones del proveedor para asegurarse de que todos los permisos están disponibles y actualizados con los cambios. Si ha borrado o archivado accidentalmente su cuenta, tenga la seguridad de que sus datos se conservarán, una vez que vuelva a verificar su credencial.

**Para volver a verificar manualmente su credencial:**

1. En el menú principal, vaya a Configuración > Credenciales de proveedor.

   Nota: Para acceder a la página «Credenciales de proveedores» se necesitan permisos de administrador.
2. Busque la cuenta que desea volver a verificar.
3. Pasa el cursor por encima del ![Icono Notas](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icono.
4. Haz clic en el icono ![icono de reverificación de credenciales](../../../../03-media/cloudability-premium/images/reverify-cloudability-icon.png) «Volver a verificar» de la lista desplegable.

   Esto inicia la validación y muestra una marca de verificación en caso de éxito.

**Para volver a verificar en bloque su credencial:**

Haga clic en **Acciones masivas** una vez seleccionado el proveedor. Se abrirá una pantalla con varias pestañas.

Haga clic en la pestaña **Verificar credenciales**.

Nota: Esto está disponible en AWS y GCP.

Esta pantalla muestra todas las cuentas excepto las que tienen el estado Credenciales necesarias (X).

Para verificar las credenciales

1. Seleccione las cuentas que deben verificarse.
2. Haga clic en **Revisar selección**
3. Haga clic en **Verificar.**

Esto activaría el proceso de verificación masiva y el botón de acciones masivas se desactivaría hasta que el proceso finalizara.

Una vez completado, las cuentas pasarán a un estado de credencial verificada o a un estado de credencial no válida (debido a errores).

Nota: En caso de que el número de cuentas sea elevado, puede tardar unos minutos.

Archivar una credencial

Al archivar una credencial se elimina el vínculo con el proveedor y se mantienen intactos los datos históricos. Se utiliza para las cuentas dadas de baja.

1. En el menú principal, vaya a Configuración > Credenciales de proveedor.
2. Haga clic en Credenciales de proveedor.
3. Busque la cuenta que desea archivar.
4. Pasa el cursor por encima del ![Icono Notas](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icono.
5. Haz clic en el icono «Archivo» ![icono de credencial de archivo](../../../../03-media/cloudability-premium/images/archivecredential.png) y selecciona **«Confirmar»** cuando se te solicite.

   Nota: Una vez archivada, la cuenta no se podrá recuperar.

Eliminar una credencial

Para eliminar una credencial:

1. En el menú principal, vaya a Configuración > Credenciales de proveedor.
2. Busque la cuenta que desea eliminar.
3. Pasa el cursor por encima del ![Icono Notas](../../../../03-media/cloudability-premium/images/regenerate_cloudability_more_options.jpg) icono.
4. Selecciona el icono «Eliminar» ![icono de eliminación de credenciales](../../../../03-media/cloudability-premium/images/deleting__a_credential_19_34_am_png.jpg) y haz clic en «Confirmar» cuando se te solicite.

Tu cuenta ha sido eliminada.

Nota: Al eliminar una cuenta de pagador, se eliminan todas las cuentas vinculadas o subordinadas.

La eliminación de una cuenta vinculada o secundaria sólo elimina la cuenta seleccionada.

Preguntas más frecuentes

- **¿Archivar una cuenta elimina los datos de Cloudability?**
  - No, archivar una cuenta no elimina los datos de Cloudability
- **¿Suprimir una cuenta** **borra los datos de Cloudability?**
  - No, borrar una cuenta no elimina los datos de Cloudability
- **¿Puedo restaurar una cuenta archivada?**
  - No, tendrás que volver a acreditar la cuenta.
- **¿Puedo archivar una cuenta sin credenciales?**
  - Sí, puedes archivar directamente una cuenta que no tenga credenciales.
- **He archivado una cuenta secundaria (¿ AWS, Linked/ Azure, Subscription/ GCP, Project, etc.). ¿Seguiré recibiendo los datos de costes correspondientes?**
  - Sí Los datos de costes se extraerán ya que los datos de costes están vinculados a la cuenta de nivel superior. Al archivar o eliminar la cuenta secundaria sólo se detendrían los datos necesarios para la acreditación anticipada, por ejemplo, los datos de utilización/compromisos, etc.
- **¿Cómo puedo descargar la plantilla actualizada con los permisos más recientes si se ha producido una actualización de los permisos?**

  - La plantilla actualizada se puede descargar editando la cuenta de facturación existente y descargando la plantilla más reciente correspondiente. Una vez descargada, sigue los pasos para la acreditación que se indican tras la descarga de la plantilla.
- **¿Qué indican los diferentes iconos en Cloudability UI?**
  - Consulte la página [Credenciales de los proveedores](vendor-credentials.html)

**Tema principal:** [Credenciales de proveedor](../admin/vendor-credentials.html)
