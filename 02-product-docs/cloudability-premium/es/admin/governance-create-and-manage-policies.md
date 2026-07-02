---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Crear y gestionar políticas"
breadcrumb:
  - "Cloudability Premium"
  - "Gobernabilidad"
source_path: "admin/governance-create-and-manage-policies.html"
images: []
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Crear y gestionar políticas

La gobernanza permite a los equipos aplicar las mejores prácticas de FinOps mediante políticas de gobernanza:

## Tipos de políticas

1. **Políticas de etiquetado** : Asegúrese de que los recursos tengan las etiquetas necesarias (por ejemplo, "Entorno: Producción").
2. **Políticas de tipo de recurso ( AWS / Azure Resource)** : definen reglas para los atributos de los recursos (por ejemplo, establecen el tamaño de la instancia y la memoria).
3. **Guardarraíles de costes** : Establezca los deltas de coste máximos permitidos para los cambios en IaC.

## Niveles de ejecución

- **Aviso** : Estos fallos de política no bloquean el flujo de trabajo de Pull Request. Se muestra una advertencia, permitiendo que el flujo de trabajo continúe sin interrupción. **Recomendamos utilizar este nivel de aplicación como punto de partida.**
- **Bloqueado** : Estos fallos de política detienen el flujo de trabajo de Pull Request cuando se combinan con la configuración en el repositorio de Github para bloquear PR para ejecuciones fallidas de comprobación de Gobernanza. Los usuarios con el rol Cloudability Governance PR Approver Role pueden anular y continuar el flujo de trabajo desde la página Governance Pull Request Details.

## Implicaciones para los clientes de HCP Terraform o Terraform Enterprise

HCP Terraform aplica su propio nivel de cumplimiento a las tareas de ejecución, que puede establecerse como **Consultivo** u **Obligatorio**. En ocasiones, esta configuración puede entrar en conflicto con los niveles de aplicación definidos en las políticas de Cloudability.

Recomendamos configurar el nivel de ejecución de la tarea HCP Terraform Run Task como **Advisory**. Por ejemplo:

- Si falla una política de **asesoramiento** de Cloudability, el PR no se bloquea y los ingenieros pueden seguir aplicando el cambio en HCP Terraform.
- Si falla una política de Cloudability **Gated**, el PR se bloquea y los ingenieros no pueden aplicar el cambio en HCP Terraform hasta que se resuelva el problema.
  - Una vez revisado y aprobado el cambio en Cloudability, los ingenieros pueden fusionar el PR, y debe activarse una nueva ejecución en HCP Terraform para aplicar el cambio.
  - Este flujo de trabajo de aprobación **no** funciona si la Tarea de ejecución de HCP está establecida como **Obligatoria**, porque Cloudability no puede anular el estado de HCP.

## Aplicación de la política

Las políticas pueden aplicarse en el:

- **Nivel de organización** : Se aplica a todos los flujos de trabajo.
- **Nivel de proyecto** : Se aplica a implantaciones concretas.

Los resultados de la evaluación de las políticas se muestran como comentarios PR que destacan los recursos y las normas que fallan.

Nota: Las políticas a nivel de organización se aplican a cloudability org; GitHub org no es relevante, es decir, una política a nivel de organización afectará a todos los despliegues independientemente de a qué GitHub org estén asociados.

## Creación de una política

Vaya a la página "Políticas" y seleccione "Recursos y etiquetas". Sigue los 4 pasos:

- **Crear política** : Seleccione un nombre de política y un tipo de política (proveedor o etiquetado)
- **Tipo de póliza** :

  - Seleccione uno de los dos niveles de aplicación.

    Tiene la opción de aplicar las políticas seleccionadas a todos los recursos existentes definidos en su código de infraestructura dentro de ese directorio, no sólo a los recursos que han cambiado en el PR.
  - **Para el tipo de política de etiquetado:** puede añadir claves de etiquetado y valores de etiquetado. Puede dejar vacío el campo "valores de etiqueta" si desea permitir todos los valores

    **Ejemplo:** Clave de etiqueta: "Aplicación"
  - **Para la política de tipos de recursos:** Puede crear reglas seleccionando tipos de recursos, atributos, operadores y un valor o valores. Puede introducir varios valores y separarlos con una coma. **Ejemplo:** Tipo de recurso = "Compute Instance ( EC2 )"; Atributo = "Instance Type"; Operador : "Not In"; Valor: “t4g.medium, t4g.small, t3a.medium”
- **Alcance de la implantación** : Seleccione al menos un proyecto o toda la organización
- **Detalles generales** : Revisar y validar la información introducida

## Creación de una barandilla de costes

Vaya a la página "Políticas" y seleccione "Cost Guardrails". Puede definir un nombre, seleccionar un nivel de aplicación y especificar un límite de coste / delta máximo permitido para cada cambio
