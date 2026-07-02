---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Instalación de la aplicación GitHub.com (en la nube)"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
  - "Configurar Cloudability Gobernanza"
source_path: "admin/governance-github-app-installation.html"
images:
  - "images/Gov3.png"
  - "images/Gov4.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Instalación de la aplicación GitHub.com (en la nube)

Se utiliza una aplicación GitHub para establecer/actualizar el estado de ejecución de la comprobación en la solicitud de extracción. Los clientes deben instalar la aplicación IBM Cloudability GitHub en sus organizaciones GitHub accediendo al enlace de instalación desde la página de configuración de Gobernanza. Para instalar la aplicación, el usuario que realiza estas operaciones debe tener permisos de administrador para la org GitHub o para los repositorios de la org.

A continuación se muestra la primera página de aterrizaje de Gobernanza. La primera acción que debe llevarse a cabo es instalar IBM Cloudability GitHub App en GitHub org del cliente.

![imagen](../../../../03-media/cloudability-premium/images/Gov3.png)

1. Haga clic en el enlace "Instalar GitHub App" *(presente en la parte frontal y central de la pestaña Configuración si se configura por primera vez)* para acceder al enlace de instalación desde la página Gobernanza.
2. Se le redirigirá a [GitHub - Build and ship software on a single, collaborative platform](http://github.com/ "(se abre en una pestaña o una ventana nueva)") for the installation.
3. Elija la organización GitHub y, a continuación, podrá instalar la aplicación para todos los repositorios o sólo para los repositorios seleccionados de esa organización GitHub.

   ![](../../../../03-media/cloudability-premium/images/Gov4.png)

   Una vez seleccionada la GitHub org, se dará la opción de:

   - instale la aplicación para acceder a todos los repositorios de GitHub org
   - sólo los repositorios seleccionados en GitHub org
4. Al instalar la aplicación, se requieren los siguientes permisos:

   - Acceso de solo lectura a los metadatos (para poder identificar los metadatos de las solicitudes de extracción)
   - Acceso de lectura/escritura a las solicitudes de extracción (se necesita acceso de escritura a las solicitudes de extracción para poder publicar comentarios en ellas)
   - Acceso de lectura y escritura a los controles (necesidad de establecer y actualizar los resultados del estado de ejecución de los controles)

Una vez concedido el acceso, la página redirige de nuevo a la página Cloudability Governance.

**Tema principal:** [Configuración Cloudability Governance](../admin/governance-setup-cldy-governance.html)
