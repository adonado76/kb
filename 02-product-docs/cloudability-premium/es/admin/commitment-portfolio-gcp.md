---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Configuración de la cartera de compromisos para GCP"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Google Cloud"
source_path: "admin/commitment-portfolio-gcp.html"
images:
  - "images/commitment-portfolio-3.jpg"
  - "images/vc_ss6.jpg"
  - "images/vc_ss7.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configuración de la cartera de compromisos para GCP

La cartera de compromisos de « GCP » (compromisos basados en el gasto) requiere dos permisos adicionales para su configuración, además de la acreditación básica.

Antes de empezar

Necesita acreditar su cuenta antes de seguir los pasos para configurar la Cartera de Compromisos. Consulte [Conéctese a Google Cloud](connect-google-cloud.html) para acreditar su cuenta.

Permisos adicionales para la cartera de compromisos

Siga los siguientes pasos para configurar las credenciales para los permisos adicionales mencionados anteriormente.

1. Inicia sesión en Cloudability y, a continuación, ve a Configuración > Credenciales de proveedor > GCP.
2. Busca una cuenta de facturación que haya adquirido CUDs de « GCP » basados en el gasto.
3. Pase el ratón por encima del icono de menú de elipsis y, a continuación, haga clic en ![icono de edición](../../../../03-media/cloudability-premium/images/commitment-portfolio-3.jpg) para seleccionar Editar una credencial.

   ![editar captura de pantalla de credenciales](../../../../03-media/cloudability-premium/images/vc_ss6.jpg)
4. Añada su ID de organización.
5. Haga clic en Actualizar credenciales.

Para obtener más información sobre los recursos organizativos, consulte [Creación y administración de recursos de la organización](https://cloud.google.com/resource-manager/docs/creating-managing-organization "(se abre en una pestaña o una ventana nueva)").

Una vez completado el ajuste a la credencialización, se muestran los siguientes nuevos permisos en la sección Reserva de la cuenta de facturación del pagador maestro:

- consumerprocurement.orders.list

- consumerprocurement.orders.get

Como parte del proceso de acreditación, el siguiente paso consiste en crear un nuevo rol dentro del ámbito de una organizació GCP. Aplique esto en el ámbito de la Cuenta de Facturación junto con el rol existente en el ámbito del Proyecto con los permisos de la Tabla BQ para una credencialización exitosa.

![captura de pantalla de detalles de credenciales](../../../../03-media/cloudability-premium/images/vc_ss7.jpg)

**Tema principal:** [Conectar Google Cloud](../admin/connect-google-cloud-premium.html)
