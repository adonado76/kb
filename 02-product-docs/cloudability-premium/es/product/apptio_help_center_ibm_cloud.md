---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "product"
title: "Conectar IBM Cloud"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
source_path: "product/apptio_help_center_ibm_cloud.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Conectar IBM Cloud

Puede conectar sus cuentas de IBM Cloud a Cloudability para permitir la ingesta de datos de costes y uso. Cloudability admite la introducción de datos de cuentas Enterprise y Standard. Una **cuenta estándar de IBM Cloud** es simplemente una cuenta independiente para una organización o usuario, con su propia facturación y gestión de acceso. Una **[cuenta de empresa](https://cloud.ibm.com/docs/enterprise-management?topic=enterprise-management-what-is-enterprise "(se abre en una pestaña o una ventana nueva)")** es una cuenta principal de nivel superior que sirve como eje central para gestionar una jerarquía de múltiples cuentas secundarias individuales y grupos de cuentas.

Nota:

El coste inicial y los datos de uso tardan entre 4 y 24 horas en aparecer en Cloudability. Esto depende del tiempo que tarde IBM Cloud en generar sus primeros informes de facturación.

**Dos formas de conectarse**

Existen dos métodos para conectar sus cuentas de IBM Cloud a Cloudability :

1. Cloudability Método: Se proporciona un script de Terraform para la gestión de credenciales, que se basaría en claves API.
2. Método de la aplicación de arquitectura desplegable (DA): IBM Cloud admite una aplicación de arquitectura desplegable (DA) denominada « IBM Cloudability Enablement», mediante la cual puedes introducir las credenciales de tu cuenta de IBM Cloud en Cloudability. Este es el método recomendado para acreditar cuentas de IBM Cloud, ya que la aplicación ayuda a agilizar el proceso.

- **[Configure las credenciales de IBM Cloud utilizando el método Cloudability](../product/setup_ibm_cloud_credentials_using_cldy_method.html)**
- **[Configurar IBM Cloud Credenciales mediante la aplicación de arquitectura desplegable (DA)](../product/setup_ibm_cloud_credentials_using_da_method.html)**
