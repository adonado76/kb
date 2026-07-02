---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "GitHub Enterprise Instalación de la aplicación en el servidor (local)"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
  - "Configurar Cloudability Gobernanza"
source_path: "admin/governance-github-enterprise-installation.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# GitHub Enterprise Instalación de la aplicación en el servidor (local)

En esta guía se explica cómo registrar una aplicación de GitHub en Cloudability para utilizarla con GitHub Enterprise Server (GHES). Este proceso te permite conectar y gestionar tus repositorios de GHES dentro del flujo de trabajo de Governance de Cloudability.

## Requisitos previos

- Acceso a una instancia de « **Cloudability** » con permisos de gobernanza.
- Acceso de administrador a tu instancia de **GitHub Enterprise Server**.

## Instrucciones paso a paso

1. **Ve a Configuración**

   En la barra lateral de « Cloudability », ve a **Gobernanza** > **Configuración**. Selecciona la pestaña **«Integraciones»** y elige « **GitHub Enterprise** » en el menú de la izquierda.
2. **Iniciar el registro**

   Haz clic en el botón **«Registrarse en la aplicación de GitHub »** situado en la parte superior derecha de la sección « GitHub Enterprise ».
3. **Introducir los datos de la aplicación**

   Aparecerá una ventana emergente titulada «Registrar una nueva aplicación de GitHub ». Facilite la siguiente información:

   - **Tipo de cuenta:** Seleccione *«Cuenta personal»* o «*Cuenta de organización* ».

     - Al seleccionar esta opción `Organization Account`, el usuario también deberá introducir el identificador único de su organización GitHub.
   - **Nombre de la aplicación:** Introduce un nombre único para tu aplicación.
   - **URL HTML:** Indique la dirección base URL de su servidor GitHub Enterprise.
   - **URL de la API:** Introduce el punto final de la API de tu servidor (normalmente `https://[your-ghes-domain]/api/v3`).

   Haz clic en **«Enviar»** para continuar.
4. **Inicia sesión en GitHub Enterprise**

   El sistema te redirigirá a tu servidor de GitHub Enterprise.

   - Si se le solicita, inicie sesión con sus credenciales corporativas o mediante su proveedor de identidad (SSO).
   - Una vez que hayas iniciado sesión, aparecerá una página de confirmación de GitHub. Haz clic en «**Crear una aplicación de GitHub para [Tu nombre/Organización]** ».
5. **Finalizar la integración**

   Al hacer clic en «Crear», se le redirigirá automáticamente de nuevo a la interfaz de Cloudability. Aparecerá brevemente un mensaje de éxito («Se ha creado correctamente una aplicación de GitHub Enterprise »).
6. **Verificar el registro**

   La nueva aplicación aparecerá ahora en la columna « **GitHub Enterprise** ». Puedes hacer clic en **«Instalar»,** junto al nombre de la aplicación, para seleccionar los repositorios específicos que deseas integrar.

## Resolución de problemas

- **Problemas con la redirección:** Si tu navegador no te redirige automáticamente durante los pasos de autenticación, busca los enlaces «haz clic aquí» que aparecen en las pantallas de transición.
- **Errores de la API URL :** Asegúrate de que la URL de la API URL incluya el `/api/v3` sufijo, ya que es necesario para que Cloudability se comunique con el servidor GitHub Enterprise.

**Tema principal:** [Configuración de la gobernanci Cloudability](../admin/governance-setup-cldy-governance.html)
