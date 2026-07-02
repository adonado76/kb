---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Gestionar usuarios y grupos de usuarios"
breadcrumb:
  - "Cloudability Premium"
  - "Administración"
source_path: "admin/manage-users-and-user-groups.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gestionar usuarios y grupos de usuarios

En Cloudability, los usuarios y grupos de usuarios ayudan a definir quién puede acceder a la plataforma y qué puede ver o hacer. Hay tres componentes clave:

Un ***Usuario*** enCloudability es un individuo al que se le ha concedido acceso a la plataforma. Cada usuario tiene una identidad única, normalmente vinculada a una dirección de correo electrónico. Los usuarios se crean y autentican a través de **FrontDoor**, que se encarga tanto de la autenticación como de la autorización. Una vez aprovisionado en FrontDoor,, al usuario se le pueden asignar funciones específicas de Cloudability, como administrador de MSP, gestor de facturación o usuario/administrador de Cloudability. Estos roles determinan los permisos y niveles de acceso del usuario dentro de la plataforma.

Más información **[Gestionar usuarios, vistas de usuario y cuadros de mando](create-and-manage-users.html)**

Un ***Grupo de usuarios*** en Cloudability es un conjunto de usuarios agrupados para simplificar la gestión de accesos y la asignación de vistas. Los administradores pueden crear grupos de usuarios y añadir usuarios individuales a ellos. Una vez creados, estos grupos pueden asignarse a Vistas específicas para controlar la visibilidad y el acceso de forma eficaz.

Más información **[Gestión de grupos de usuarios](manage-user-groups.html)**

Un ***Grupo Entra ID*** en Cloudability se refiere al grupo de usuarios gestionado dentro de Microsoft Entra ID (anteriormente Azure Active Directory), el servicio de gestión de identidad y acceso basado en la nube de Microsoft. En lugar de crear manualmente grupos de usuarios en Cloudability, las organizaciones pueden importar Grupos Entra ID junto con sus usuarios asociados.

Más información **[Gestión de grupos Entra ID](manage-entra-id-groups.html)**

- **[Gestión de usuarios, vistas de usuario y cuadros de mando](../admin/create-and-manage-users.html)**
- **[Gestionar grupos de usuarios](../admin/manage-user-groups.html)**
- **[Gestionar grupos Entra ID](../admin/manage-entra-id-groups.html)**
- **[Preguntas frecuentes sobre usuarios y grupos de usuarios](../admin/users-and-user-groups-faqs.html)**
