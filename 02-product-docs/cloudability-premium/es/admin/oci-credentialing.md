---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Federar un usuario para la acreditación OCI"
breadcrumb:
  - "Cloudability Premium"
  - "Introducción de datos Cloudability"
  - "Conectar Oracle Cloud"
source_path: "admin/oci-credentialing.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Federar un usuario para la acreditación OCI

Resumen

En esta página se describe paso a paso el proceso para gestionar un usuario federado en un proveedor de identidad para OCI, centrándose específicamente en la creación y configuración de usuarios y grupos en el servicio Identity Cloud Service («IDCS») de Oracle.

Este proceso es opcional; consiste en implementar un Terraform y, a continuación, sustituir al usuario por un usuario federado.

Requisitos previos

Para crear usuarios y grupos en la federación del servicio Identity Cloud de Oracle, necesitarás el rol de administrador del dominio de identidad o formar parte de un grupo al que se le haya asignado dicho rol.

Pasos

Preparación

Asegúrate de que « CloudabilityDataCollector\_Group », « CloudabilityDataCollector\_User » y « CloudabilityCostDataReaderPolicy » ya se hayan creado mediante Terraform.

Eliminación de un usuario local

Elimina el archivo « CloudabilityDataCollector\_User » si existe.

Creación de un usuario federado

1. Ve a Identidad -> Federación -> Detalles del proveedor de identidad -> Usuarios.
2. Crea un nuevo usuario de IDCS utilizando las siguientes credenciales.

   - Nombre de usuario : CloudabilityDataCollector\_Fed\_User
   - Correo electrónico : cldyfeduser@cloudability.com o cualquier dirección de correo electrónico válida
   - Nombre : CloudabilityDataCollector
   - Apellido : Fed\_User
3. Haz clic en «Crear» y, a continuación, en «Cerrar ».

Creación de un grupo federado

1. Ve a Identidad -> Federación -> Detalles del proveedor de identidad -> Grupo.
2. Crea un nuevo grupo en IDCS llamado « CloudabilityDataCollector\_Fed\_Group ».
3. Añade al grupo al usuario federado « CloudabilityDataCollector\_Fed\_User ».

Asignación de un grupo local a un grupo federado

Dado que no es posible conceder acceso a los grupos federados mediante políticas, es necesario asociar un grupo local al grupo federado.

1. Ve a Identidad -> Federación -> Detalles del proveedor de identidad -> Asignaciones de grupos.
2. Crea un nuevo grupo en IDCS llamado « CloudabilityDataCollector\_Fed\_Group ».
3. Crea una correspondencia entre el grupo de OCI « CloudabilityDataCollector\_Group » y el grupo federado « CloudabilityDataCollector\_Fed\_Group ».

Sincronización del usuario sincronizado de OCI

Ve a Identidad -> Federación -> Detalles del proveedor de identidad -> Usuarios -> « CloudabilityDataCollector\_Fed\_User ».

Haz clic en el enlace «OCI Synched User» del usuario federado « CloudabilityDataCollector\_Fed\_User ».

Generación de claves de API:

1. Ve a «Claves de API ».
2. Añade una nueva clave de API.
3. Genera un par de claves de API.
4. Descarga la clave privada y la clave pública.
5. Añade las claves.

Envío de datos a Cloudability

Facilita los datos necesarios, incluidas las claves API y cualquier otra información pertinente, a Cloudability a través de la interfaz de usuario.

**Tema principal:** [Conectar- Oracle -Cloud](../admin/connect-oracle-cloud.html)
