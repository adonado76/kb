---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Configurar Cloudability Gobernanza"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
source_path: "admin/governance-setup-cldy-governance.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Configurar Cloudability Gobernanza

## Antes de empezar

Esta documentación está destinada a las siguientes funciones dentro de una organización:

- **Administradores de plataforma** : son los responsables de configurar la función e instalar la aplicación GitHub. Para las organizaciones que utilizan HCP o Terraform Enterprise, tendrán que configurar la tarea de ejecución de gobernanza Cloudability y asegurarse de que está alineada con los límites de seguridad de la organización.
- **FinOps Equipos** - Definirán y gestionarán las políticas de su organización (como las familias de instancias aprobadas, las etiquetas requeridas o las restricciones regionales).
- **Cloud Engineers** - Consumirán la integración de Cloudability Governance con GitHub y Terraform. Los desarrolladores ejecutan planes y aplican Terraform como parte de sus flujos de trabajo y reciben información inmediata sobre costes y cumplimiento.

Para utilizar correctamente esta función, asegúrese de que cumple los siguientes requisitos previos:

- **Para usuarios de GitHub :**

  - Repositorio que contiene código Terraform de muestra.
  - Lista de direcciones IP permitidas: si su organización GitHub utiliza una lista de direcciones IP permitidas, debe asegurarse de que se incluyan los rangos de direcciones IP salientes de Cloudability. Sin estas entradas, Cloudability Governance no podrá comunicarse con sus repositorios GitHub y es posible que las comprobaciones de políticas fallen. Los siguientes rangos de IP deben añadirse a la lista de permitidos de su organización GitHub :
    - **185.115.88.0/22**
    - **103.195.128.0/22**
    - **129.41.0.0/22**
- Una cuenta de IBM Cloudability con los permisos de gobernanza adecuados asignados.
- **Para clientes de HCP Terraform / Terraform** : Una cuenta HCP Terraform con permisos para crear espacios de trabajo y gestionar Run Tasks.
- **Para usuarios de la Comunidad Terraform** : GitHub Las acciones están disponibles en su cuenta de GitHub.

## Visión general

Para configurar Governance, los administradores de Cloudability deben configurar la integración con GitHub, que se utilizará para el flujo de trabajo de aprobación de solicitudes de incorporación de cambios (PR) en todos los tipos de clientes. A continuación, dependiendo de la plataforma Terraform en uso, los pasos de configuración difieren:

- **Para los usuarios de HCP Terraform o Terraform Enterprise**, GitHub Actions no es necesario. En su lugar, los administradores deben configurar una tarea de ejecución en su espacio de trabajo de Terraform recuperando la clave HMAC y el punto final URL de Cloudability y añadiéndolos a la configuración de la tarea de ejecución.
- **Para los usuarios de Terraform Community**, los administradores deben configurar algunas variables/secretos a nivel de organización en GitHub para almacenar las claves de la API de Frontdoor, el ID de entorno de Frontdoor URL y la API Cloudability URL. También deben crear o configurar sus propios flujos de trabajo de Acciones GitHub que invoquen las Acciones de gobernanza GitHub de Cloudability.

Una vez completado, Governance identificará sus «implementaciones» (unidades gestionadas por Terraform, también denominadas «espacios de trabajo» en HCP Terraform) y las mostrará en la página Configuración de Governance. Los usuarios tendrán que asignarlos a proyectos (que son grupos de despliegues), que tendrán políticas asociadas. Los clientes pueden optar por definir los proyectos por aplicación, equipo, servicio o entorno. El nombre de un proyecto para una implementación también se puede proporcionar como entrada opcional dentro del propio flujo de trabajo de la acción « GitHub » (Crear implementación).

- **[Instalación de la aplicación GitHub.com (en la nube)](../admin/governance-github-app-installation.html)**
- **[GitHub Enterprise Instalación de la aplicación en el servidor (local)](../admin/governance-github-enterprise-installation.html)**
- **[HCP Terraform/Terraform Enterprise](../admin/governance-hcp-terraform-terraform-enterprise.html)**
- **[Configure GitHub Acciones para Terraform Community](../admin/governance-configure-github-actions-for-terraform-community.html)**
- **[Configuraciones de implantación](../admin/governance-deployment-configurations.html)**
- **[Configuración de preferencias](../admin/governance-preferences-configurations.html)**
