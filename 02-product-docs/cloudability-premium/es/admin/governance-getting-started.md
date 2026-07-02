---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Gobernanza - Primeros pasos"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
source_path: "admin/governance-getting-started.html"
images:
  - "images/Terraform2.png"
  - "images/Workflow_Terraform.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Gobernanza - Primeros pasos

## Qué puede hacer con Cloudability Gobernanza

Configure nuestra hoja de ruta de gobernanza: [Encuesta « 2‑Minute » (El futuro de la gobernanza de Internet)](https://forms.office.com/r/qs2wL1U2xt "(se abre en una pestaña o una ventana nueva)")

Cloudability La gobernanza permite a los equipos gestionar de forma proactiva los costes de la nube y aplicar las políticas de FinOps directamente en los flujos de trabajo de los desarrolladores. Con esta función, puedes:

- **Calcular los costes antes de la implementación:** obtén estimaciones de costes en tiempo real para los recursos en la nube, incluyendo precios personalizados y descuentos de EA, directamente en GitHub y HCP Terraform
- **Optimice la selección de recursos:** reciba recomendaciones sobre alternativas más económicas de AWS EC2 y RDS con configuraciones similares
- **Aplique políticas en IaC :** garantice el cumplimiento imponiendo claves/valores de etiqueta obligatorios, bloqueando el aprovisionamiento de recursos heredados y estableciendo umbrales de presupuesto para equipos y aplicaciones.
- **Controle el cumplimiento:** utilice un panel centralizado para realizar un seguimiento del cumplimiento de las políticas de FinOps en toda su organización.
- **Gestione las solicitudes de relaciones públicas no conformes:** identifique y revise las solicitudes de extracción que infrinjan las normas de costes o políticas, con flujos de trabajo de aprobación integrados

Esta función hace que la gestión de los costes de la nube pase de ser reactiva a proactiva, lo que ayuda a evitar los gastos excesivos y las infracciones de las políticas antes de desplegar la infraestructura.

## Integraciones compatibles

- **IaC Herramientas** : HCP Terraform, Terraform Enterprise, [Terraform Editions](https://developer.hashicorp.com/terraform/intro/terraform-editions "(se abre en una pestaña o una ventana nueva)") (versión 1.10.5 ); Terragrunt (versión 0.72.6 )
- **VCS:** GitHub.com, servidor GitHub Enterprise
- **Proveedor de servicios en la nube:** AWS, Azure

## Flujo de trabajo - HCP Terraform/Terraform Enterprise

![imagen](../../../../03-media/cloudability-premium/images/Workflow_Terraform.png)

Las capacidades representadas en el diagrama están disponibles para el flujo de trabajo impulsado por VCS y para los clientes que utilizan GitHub.

Para los clientes que utilizan otros VCS o flujos de trabajo basados en CLI/API, no se admiten determinadas funciones de gobernanza:

- Los desencadenantes de flujos de trabajo impulsados por CLI o API no aparecen en la página Cloudability Governance → Pull Request.
- Las comprobaciones de actualización de estado y validación no se envían de vuelta al entorno iniciador (página PR de Github, si se ha creado)
- Las acciones de gobernanza, como la validación de políticas, el bloqueo de la aplicación o la aprobación manual, no están disponibles a través de la interfaz de gobernanz Cloudability.

## Flujo de trabajo - Comunidad Terraform

![imagen](../../../../03-media/cloudability-premium/images/Terraform2.png)

## Resumen de permisos

Cloudability El acceso a la gobernanza se controla mediante cuatro permisos específicos. Asegúrese de que tiene asignadas las funciones/permisos adecuados.

- **GovernanceFeatureViewOnly** - Este permiso permite a los usuarios ver todas las páginas del elemento de menú "Gobernanza" de Cloudability. Este permiso está incluido en el rol **" Cloudability User"**.
- **GovernanceFeatureConfigurationFullAccess** - Este permiso permite a los usuarios acceder a la funcionalidad de configuración (ver, crear, actualizar detalles de configuración). Este permiso está incluido en los roles **" Cloudability Admin"** y **" Cloudability Governance Automation User"**.
- **GovernanceFeaturePolicyFullAccess** - Este permiso permite al usuario acceder a la funcionalidad de configuración de políticas (ver, crear, actualizar políticas) bajo la opción de menú Cloudability "Governance". Este permiso está incluido en el rol **" Cloudability Governance Policy Admin"**.
- **GovernanceFeaturePRApproval** - Este permiso permite a los usuarios aprobar Pull Requests que están bloqueados cuando no cumplen con las políticas. Este permiso está incluido en el rol **" Cloudability Governance PR Approver"**.

## Seguridad - Cómo se protegen su código y la infraestructura CSP

Cloudability La gobernanza se ha diseñado teniendo en cuenta la seguridad y la privacidad, garantizando que su código y la infraestructura de su proveedor de servicios en la nube (CSP) permanezcan protegidos durante todo el proceso de comprobación de costes y políticas.

1. GitHub Seguridad de la integración:
   - La **aplicación IBM Cloudability GitHub** sólo se utiliza para leer metadatos de solicitudes de pull (PR), publicar comentarios en solicitudes de pull y establecer estados de comprobación de PR.
   - Requiere **permisos mínimos** :
     - Acceso **de sólo lectura** a metadatos y pull requests.
     - Acceso **de lectura y escritura** a los pull requests. El acceso de escritura a los pull requests es necesario para poder enviar comentarios a los pull requests.
     - Acceso **de lectura/escritura** a las comprobaciones (necesario para añadir comprobaciones relacionadas con la gobernanza en GitHub PRs y actualizar su estado como fallido, neutral o satisfactorio).
   - Para los usuarios de Terraform Community, la acción GitHub que invoca Cloudability Governance se ejecuta **completamente dentro de su entorno**, asegurando que no haya acceso externo a su código base.
2. **AWS / Azure Protección de infraestructuras** :
   - Cloudability **Govern** ance no accede a su entorno de AWS / Azure.
   - En su lugar, analiza **las salidas estáticas del plan Terraform** pasadas a través de GitHub Action o HCP Terraform. Los resultados del plan de Terraform no persisten en el lado de Cloudability y cualquier secreto o información confidencial del plan de Terraform puede ser censurado antes de proporcionarse como entrada a Cloudability Governance.
   - AWS / Azure Los ID de cuenta se **utilizan** únicamente para determinar el nivel de precios; no se requieren credenciales **y** no se realizan llamadas directas a la API AWS / Azure en las cuentas de los clientes.
   - Todos los datos de precios proceden del **servicio de precios interno de Cloudability**, no de su infraestructura.

Esta arquitectura garantiza que su código IaC y su infraestructura en la nube permanezcan seguros, sin exposición de datos sensibles ni requisitos de acceso elevados.

[Configurar Cloudability Gobernanza](governance-setup-cldy-governance.html)

[Crear y gestionar políticas](governance-create-and-manage-policies.html)

[Pull Requests - Flujo de aprobación](governance-pull-requests-and-approval-workflow.html)

[Recomendaciones de recursos](governance-resource-recommendations.html)

[Estimación de costes basada en el uso y la configuración](governance-usage-and-configuration-based-cost-estimation.html)

[Solución de problemas](governance-troubleshooting.html)
