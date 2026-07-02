---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Configuración de la asistencia para precios personalizados para GCP"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Google Cloud"
source_path: "product/gcp-rightsizing-custom-pricing-support.html"
images:
  - "images/gcp-standard-billing-1.jpg"
  - "images/gcp-standard-billing-2.jpg"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configuración de la asistencia para precios personalizados para GCP

El servicio de precios personalizados se ha ampliado ahora a GCP para Cloudability, de modo que los descuentos contractuales y otras tarifas específicas para cada cliente se apliquen a las recomendaciones de ajuste de recursos de GCP y **a la planificación de cargas de trabajo**.

Sigue los pasos que se indican a continuación para habilitar la exportación de datos de precios personalizados para las cuentas de GCP.

1. Accede a la cuenta de facturación de GCP.
2. Seleccione **Facturación** > **Exportar facturación**.

   ![GCP Captura de pantalla de la factura estándar](../../../../03-media/cloudability-premium/images/gcp-standard-billing-1.jpg)
3. En **Precios**, haga clic en " **Activar exportación de precios** ".
4. Seleccione **Precios > Editar configuración**.
5. En función de la opción de **facturación GCP** elija ( **facturación estándar** o **facturación detallada** ), debe asegurarse de lo siguiente:
   - Seleccione el **nombre del proyecto** y el **nombre del conjunto de datos** tal y como se ha **seleccionado** para " **Coste de uso estándar** " si está utilizando **la facturación estándar**.

   ![Icono Notas](../../../../03-media/cloudability-premium/images/gcp-standard-billing-2.jpg)

   - Seleccione el **nombre del proyecto** y el **nombre del conjunto de datos** igual que el **seleccionado** para " **Coste de uso detallado** " si está utilizando **la facturación detallada**.

**Tema principal:** [Conectar Google Cloud](../admin/connect-google-cloud-premium.html)
