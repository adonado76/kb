---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Autenticación e identidad"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
source_path: "studio/new-uc/concepts-architecture/security-model/authentication-identity.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Autenticación e identidad

La autenticación es el primer nivel de seguridad. Comprueba que el usuario sea quien dice ser antes de concederle acceso a TBM Studio.

## Métodos de autenticación

TBM Studio admite múltiples métodos de autenticación, gestionados a través de la plataforma Enhanced Access Administration (EAA).

**Nombre de usuario y contraseña**

El método de autenticación más básico. Los usuarios inician sesión con una dirección de correo electrónico y una contraseña. Los administradores de dominio configuran las políticas de contraseñas a través del cuadro de diálogo «Seguridad del dominio», incluyendo:

- Vigencia mínima y máxima de la contraseña (el valor « -1 » significa que no hay límite)
- Requisitos de complejidad de la contraseña
- Políticas de bloqueo de cuentas

Nota: **Configuración de la política de contraseñas**

Un valor de « -1 » en los campos «Min password age» y «Max password age» significa «ilimitado» Deja el campo «Antigüedad mínima de la contraseña» configurado en « -1 », a menos que tu organización exija un intervalo mínimo entre los cambios de contraseña.

**Inicio de sesión único (SSO)**

Para las organizaciones que utilizan proveedores de identidades corporativos, TBM Studio admite la integración de SSO. Cuando el inicio de sesión único (SSO) está habilitado, los usuarios se autentican a través del proveedor de identidad corporativo, en lugar de introducir una contraseña independiente para TBM Studio. El SSO se configura a nivel de usuario: si se establece la contraseña de un usuario como «SSO» (en mayúsculas o minúsculas), el usuario deberá autenticarse a través del proveedor de SSO.

**Autenticación mediante clave API**

Para el acceso programático (cargas y descargas de datos, e integraciones), TBM Studio admite la autenticación mediante clave API a través de la Administración de acceso mejorada. Las claves API constan de una clave pública y una clave secreta. Son el método de autenticación preferido para el acceso a las API, ya que ofrecen mayor seguridad que las combinaciones de nombre de usuario y contraseña y pueden limitarse a permisos específicos.

Nota:

**Buenas prácticas: autenticación de API**

Utiliza claves API en lugar de nombre de usuario y contraseña para todas las integraciones automatizadas. A las claves API se les pueden otorgar permisos mínimos (como el acceso solo para subir archivos) siguiendo el principio del privilegio mínimo. Consulte la sección 5.5 (Referencia de la API) para obtener información detallada sobre la configuración de la clave de la API.

## Identidad de usuario en TBM Studio

Cuando un usuario se autentica, TBM Studio crea una sesión que registra su identidad durante toda su interacción con el sistema. Entre los conceptos clave de la sesión se incluyen:

- **Tokens de sesión:** tras la autenticación, el sistema emite un token (como el Apptio -opentoken) que se utiliza para las solicitudes posteriores sin necesidad de volver a autenticarse.
- **Tiempo de espera de la sesión:** las sesiones caducan tras un periodo de inactividad, configurado a nivel de dominio. Cuando una sesión caduca, el usuario debe volver a autenticarse.
- **Suplantación de identidad:** Los administradores pueden suplantar la identidad de otro usuario para verificar sus permisos y resolver problemas de acceso. Se trata de una valiosa herramienta de prueba para validar las configuraciones de seguridad.

Importante: **Suplantación de identidad**

La suplantación de identidad es una herramienta administrativa muy eficaz. Úsalo únicamente con fines de prueba y resolución de problemas. Al suplantar la identidad de un usuario, verás exactamente lo mismo que vería ese usuario, incluidas sus restricciones de RLS y sus permisos para generar informes.
