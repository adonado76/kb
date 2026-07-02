---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Configuración de preferencias"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
  - "Configurar Cloudability Gobernanza"
source_path: "admin/governance-preferences-configurations.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configuración de preferencias

Descripción general

Para obtener los precios específicos de cada cuenta, « Cloudability Governance» busca actualmente la información de la cuenta del proveedor de la siguiente manera:

**AWS Recursos**

**Clientes de HCP TF/Terraform Enterprise** : información de la cuenta del proveedor dentro del propio plan de Terraform, procedente de la fuente de datos aws\_caller\_identity ( [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(se abre en una pestaña o una ventana nueva)") ). Esta información, si está presente en la salida del plan de Terraform, tiene la máxima prioridad. Si la información de la cuenta no está disponible a través de aws\_caller\_identity, Cloudability Governance utiliza la cuenta predeterminada configurada en las preferencias de la página de configuración de Cloudability Governance. Si no se ha configurado una cuenta predeterminada en las preferencias, se utilizará el precio minorista (de catálogo).

**Clientes de TF Community (a través de la acción « GitHub »)** : información de la cuenta del proveedor dentro del propio plan de Terraform, procedente de la fuente de datos «aws\_caller\_identity» ( [https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(se abre en una pestaña o una ventana nueva)") ). Esta información, si está presente en la salida del plan de Terraform, tiene la máxima prioridad. Si la información de la cuenta no está disponible a través de aws\_caller\_identity, Cloudability Governance usa el mapa "cuentas de proveedor" como entrada para la acción GitHub si está configurado. Este es el segundo en orden de preferencia. Si la información de la cuenta no está disponible a través de una acción de entrada de GitHub, Cloudability Governance utiliza la cuenta predeterminada configurada en las preferencias de la página de configuración de Cloudability Governance. Si no se ha configurado una cuenta predeterminada en las preferencias, se utilizará el precio minorista (de catálogo).

**Azure Recursos**

En el caso de los recursos de « Azure », « Cloudability Governance» busca la información sobre la suscripción siguiendo el siguiente orden de prioridad:

**Clientes de HCP TF/Terraform Enterprise** : información sobre la suscripción del proveedor dentro del propio plan de Terraform, a través del recurso «azurerm\_subscription» o la fuente de datos «azurerm\_subscription» ( [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription "(se abre en una pestaña o una ventana nueva)") ). Esta información, si está presente en la salida del plan de Terraform, tiene la máxima prioridad. Si no se dispone de información sobre la suscripción a través de `azurerm\_subscription`, ` Cloudability Governance` utiliza la cuenta predeterminada configurada en las preferencias de la página de configuración de ` Cloudability Governance`. Si no se ha configurado una cuenta predeterminada en las preferencias, se utilizará el precio minorista (de catálogo).

**Clientes de TF Community (mediante la acción « GitHub »)** : información sobre la suscripción del proveedor dentro del propio plan de Terraform, procedente del recurso «azurerm\_subscription» o de la fuente de datos «azurerm\_subscription» ( [https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription](https://registry.terraform.io/providers/hashicorp/azurerm/latest/docs/resources/subscription "(se abre en una pestaña o una ventana nueva)") ). Esta información, si está presente en la salida del plan de Terraform, tiene la máxima prioridad. Si la información de la suscripción no está disponible a través de `azurerm\_subscription`, Cloudability Governance utiliza el mapa «provider-accounts» como entrada para la acción ` GitHub `, si está configurada. Este es el segundo en orden de preferencia. Si la información de la suscripción no está disponible a través de la entrada de acción de GitHub, Cloudability Governance utiliza la cuenta predeterminada configurada en las preferencias de la página de configuración de Cloudability Governance. Si no se ha configurado una cuenta predeterminada en las preferencias, se utilizará el precio minorista (de catálogo).

**Tema principal:** [Configuración de la gobernanza de Cloudability](../admin/governance-setup-cldy-governance.html)
