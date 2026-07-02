---
source_system: "apptio-billing"
practice: "tbm"
language: "es"
doc_type: "boit"
title: "Descripción general y funciones"
breadcrumb:
  - "Billing"
  - "cómo empezar"
  - "Roles y permisos de usuario"
source_path: "boit/billing/getting-started/std-custom-role.html"
images: []
capability_ids: []
last_updated: "2026-05-13"
summary: ""
---
# Descripción general y funciones

Los roles y permisos de los usuarios controlan quién puede ver y trabajar con Benchmarking. Un rol es un conjunto de permisos que se asigna a un usuario, y nadie puede acceder a un producto IBM Apptio sin tener al menos un rol en su cuenta, que se gestiona en Administración de accesos. En la administración de Access, los administradores autorizados crean y gestionan los registros de usuarios, asignan o eliminan roles y controlan qué roles pueden acceder a cada punto final del producto, qué puntos finales están abiertos a cualquier rol elegible y qué puntos finales están ocultos por completo.

Para obtener más información sobre cómo asignar roles, gestionar cuentas de usuario y acceder a los productos IBM Apptio, consulte la documentación de [Administración de acceso](https://www.ibm.com/docs/en/apptio-platform/access-administration/saas "(se abre en una pestaña o una ventana nueva)").

## Roles de usuario

A continuación se destacan algunas de las funciones que tienen acceso a Facturación:

- **Administrador**
  - Acceso completo a todas las funciones de Facturación (incluidos Costing y TBM Studio).
  - Incluye acceso administrativo a Frontdoor y la posibilidad de crear roles personalizados.
- **Apptio Socio**
  - Acceso similar al de un administrador, pero no puede registrar, desactivar ni eliminar cuentas de usuario de un cliente a menos que se le conceda una función independiente con los permisos adecuados.
  - El rol solo puede ser asignado/desasignado por el soporte técnico de IBM.
- **Empresa Consumidor**
  - **Aviso: Se aplica únicamente a la norma de facturación.**
  - Otorga acceso a los informes de la colección «Cargos por servicios» y al grupo «Propietario de la empresa» que aparece en el informe de inicio.
- **Propietario de la empresa**
  - **Aviso: Se aplica únicamente a la norma de facturación.**
  - Otorga acceso a los informes de las colecciones «Cargos por servicios» y «Gestión de relaciones comerciales», así como a los grupos «Propietario de la empresa» y «Gestor de relaciones comerciales» que aparecen en el informe de inicio.
- **Jefe de servicio**
  - **Aviso: Se aplica únicamente a la norma de facturación.**
  - Otorga acceso a los informes de las colecciones «Cargos por servicio» y «Proveedor de servicios de TI», así como a los grupos «Propietario de la empresa» y «Proveedor de servicios» que aparecen en el informe de inicio.

En el caso de Billing Essentials, los roles estándar a los que se les ha concedido acceso a un proyecto de Costing Essentials con los componentes de Billing Essentials instalados tendrán acceso a todos los informes de la colección de informes «Facturación».

Revise periódicamente la administración de accesos (en Frontdoor) y las recopilaciones de informes de facturación para identificar otras funciones con acceso al contenido de facturación.

## Roles personalizados

Puedes crear roles personalizados en Frontdoor. Las funciones personalizadas te permiten adaptar el acceso para satisfacer las necesidades específicas de tu organización.
