---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "HCP Terraform/Terraform Enterprise"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
  - "Configurar Cloudability Gobernanza"
source_path: "admin/governance-hcp-terraform-terraform-enterprise.html"
images:
  - "images/Gov5.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# HCP Terraform/Terraform Enterprise

## Visión general

Cloudability La gobernanza se integra con [HCP Terraform](https://developer.hashicorp.com/terraform/cloud-docs "(se abre en una pestaña o una ventana nueva)") y [Terraform](https://developer.hashicorp.com/terraform/enterprise "(se abre en una pestaña o una ventana nueva)") Enterprise a través de una [**tarea de ejecución**](https://developer.hashicorp.com/terraform/cloud-docs/workspaces/settings/run-tasks "(se abre en una pestaña o una ventana nueva)"), lo que permite el análisis automatizado de costes y la aplicación de políticas durante los flujos de trabajo de solicitud de extracción.

Una vez configurada, la tarea de ejecución evalúa los planes de Terraform y proporciona información en tiempo real -señalando riesgos de costes, etiquetas que faltan y recursos no conformes- antes de la implantación.

**Requisito previo:** Asegúrese de tener instalada la aplicación IBM Cloudability GitHub antes de proceder a la configuración de la Tarea de ejecución.

## Generar credenciales en Cloudability

1. En la interfaz de usuario Cloudability, vaya a **Configuración > Integraciones**.
2. Generar una **devolución de llamada URL** y una **clave HMAC**.
   - Estas credenciales autentican y enrutan las devoluciones de llamada de Run Task desde HCP Terraform.
   - Cada par de claves representa una única credencial HCP para su organización.

   ![imagen](../../../../03-media/cloudability-premium/images/Gov5.png)

## Crear una tarea de ejecución en HCP Terraform

1. En la interfaz de usuario de HCP Terraform, vaya a **Configuración → Integraciones → Ejecutar tareas**.
2. Cree una nueva tarea de ejecución con los siguientes detalles:
   - **Etapa** : Después del plan
   - **Punto final URL** : Utilice la devolución de llamada URL de Cloudability
   - **Clave HMAC** : Utilice la clave generada en Cloudability
   - **Nivel de aplicación** : Elija Aviso (sólo advertir) u Obligatorio (bloquear en caso de fallo).

     *Consejo: empiece con el asesoramiento para evaluar el impacto antes de imponerlo.*
3. Adjunte la tarea de ejecución a uno o varios espacios de trabajo:
   - Puede aplicarlo globalmente a todos los espacios de trabajo o adjuntarlo individualmente.
   - Se recomienda reutilizar una única tarea de ejecución en varios espacios de trabajo.

   Una vez finalizada la configuración, diríjase a la página [**Configuración de la implantación**](governance-deployment-configurations.html).

## Configuración con Terraform Enterprise

Si su instancia de Terraform Enterprise está alojada detrás de un cortafuegos, asegúrese de que permite las **solicitudes entrantes de Cloudability** para que los resultados de la tarea de ejecución se puedan publicar correctamente.

Consulte la documentación de [Terraform Enterprise Run Task API](https://developer.hashicorp.com/terraform/enterprise/api-docs/run-tasks/run-tasks-integration#run-task-callback "(se abre en una pestaña o una ventana nueva)") para obtener detalles técnicos sobre la configuración de la devolución de llamada.

Si tiene algún problema, póngase en contacto con el equipo de su cuenta en Cloudability. Ellos le pondrán en contacto con el equipo de productos para que le presten asistencia.

## Cómo incluir la información de la cuenta del proveedor en la salida del plan de Terraform

En cuanto a AWS los recursos, esto se puede lograr incluyendo [aws\_caller\_identity](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/caller_identity "(se abre en una pestaña o una ventana nueva)") como fuente de datos en sus archivos Terraform.

Para los archivos Terraform que implementan recursos en una sola cuenta, esto se puede hacer añadiendo la siguiente línea en la configuración de Terraform.

```
data "aws_caller_identity" "defaultidentity" {}
```

Para los archivos Terraform que implementan recursos en varias cuentas a través de proveedores definidos, esto se puede hacer añadiendo las siguientes líneas para cada proveedor en la configuración de Terraform. En el siguiente ejemplo, «ingeniería» y «preparación» son dos proveedores diferentes.

```
data "aws_caller_identity" "engineering" {
  provider = aws.engineering
}
data "aws_caller_identity" "staging" {
  provider = aws.staging
}
```

## Integra tus tarifas personalizadas y añade la información de uso para obtener una estimación de costes más precisa

- Consulte la documentación de IBM Cloudability [aquí](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=governance-preferences-configuration "(se abre en una pestaña o una ventana nueva)") para ver cómo obtener una estimación de costes más precisa, que incluya sus precios personalizados.
- Consulte la documentación de IBM Cloudability [aquí](https://www.ibm.com/docs/en/cloudability-commercial/cloudability-premium/saas?topic=governance-usage-configuration-based-cost-estimation "(se abre en una pestaña o una ventana nueva)") para añadir información de uso y obtener una estimación de costes más precisa

**Tema principal:** [Configuración Cloudability Governance](../admin/governance-setup-cldy-governance.html)
