---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Permisos del proyecto"
breadcrumb:
  - "Planning"
  - "Planificación de proyectos"
source_path: "it-planning/planning/iip/project-level-access-control.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Permisos del proyecto

Importante: *Disponible con la* *suscripción* ***Apptio Planning Standard***.

Recuerde: *la función de planificación integrada de inversiones (IIP) está habilitada.*

La planificación integrada de inversiones (IIP) admite diferentes modelos de propiedad presupuestaria en las organizaciones. Dado que las estructuras presupuestarias operativas y de proyectos varían, Apptio Planning proporciona **controles de acceso** flexibles a nivel de proyecto que se ajustan a la jerarquía de su organización, al modelo de responsabilidad de costes y al flujo de trabajo de planificación.

Esta guía describe casos de uso comunes en la planificación de proyectos y explica cómo configurar los permisos a nivel de proyecto utilizando **Proyectos → Permisos** y **Permisos de objetos de coste**.

## Caso de uso 1: Los gestores de proyectos son responsables de todos los costes del proyecto (departamentos dedicados a proyectos)

**Visión general**

Se utiliza cuando cada proyecto tiene su propio centro de costes dedicado y theProjectManageris es el único responsable de todos los costes de ese proyecto.

**Objetivo**

Los gestores de proyectos planifican y gestionan todos los gastos de los proyectos de los que son responsables.

**Estructura organizativa**

- Los proyectos tienen centros de costes dedicados que se agrupan en un «Departamento de Proyectos» diferenciado
- Los responsables del presupuesto del proyecto son independientes de los responsables del presupuesto operativo de los departamentos.

**Requisitos de acceso**

- Los gestores de proyectos solo pueden ver/editar los departamentos de sus proyectos.
- Los gestores de proyectos pueden introducir los gastos directamente en los centros de costes de sus proyectos.
- Los gestores de proyectos pueden enviar presupuestos para su aprobación.

**Implementación**

- Asigne a los gestores de proyectos el rol de propietario del centro de costes (o equivalente) en Frontdoor.
- Conceda acceso de edición a los centros de coste del proyecto mediante los permisos de objetos de coste.
- Utilice los «departamentos de consolidación de proyectos» para separar las finanzas exclusivas de los proyectos.

**Resultado**

- Los gestores de proyectos pueden introducir los costes de los proyectos dentro de su departamento asignado.
- El acceso sigue estando restringido a los departamentos específicos del proyecto.

## Caso de uso 2: Los propietarios de centros de costes gestionan tanto los costes operativos como los costes de los proyectos

**Visión general**

Se utiliza cuando un único responsable del presupuesto gestiona tanto los gastos operativos como los gastos de proyectos de su departamento.

**Objetivo**

Los responsables de los centros de costes gestionan todos los gastos, tanto de proyectos como operativos, de su departamento.

**Estructura organizativa**

- No hay personas separadas; los propietarios de los centros de costes son responsables de todos los costes.
- Los proyectos pueden asignar costes a cualquier centro de costes.

**Requisitos de acceso**

- Los propietarios solo pueden ver/editar sus propios departamentos.
- Los propietarios pueden enviar presupuestos a través del flujo de trabajo estándar.

**Implementación**

- Asignar a los propietarios de centros de coste la función **de propietario de centro de coste**.
- Conceda permisos de edición a los departamentos pertinentes a través de **los permisos de objetos de coste**.
- Habilite «Permitir cualquier centro de costes» en Proyectos si se necesita una asignación entre departamentos.

**Resultado**

- Una persona se encarga de todas las actividades presupuestarias.
- Acceso completo a los gastos operativos y de proyectos a nivel departamental.

**Limitación**

- No se puede restringir a un propietario de centro de costes únicamente a los gastos del proyecto. Verán todos los gastos de su departamento.

## Caso de uso 3: Modelo híbrido — Propietarios de departamentos + Gestores de proyectos (costes de proyectos compartidos)

**Visión general**

Se utiliza cuando los gestores de proyectos asignan los gastos del proyecto a los departamentos, mientras que los responsables de los departamentos siguen siendo responsables de los gastos operativos y de aprobar las asignaciones del proyecto.

**Objetivo**

- Los responsables de departamento planifican los gastos operativos y aprueban las asignaciones de proyectos.
- Los gestores de proyectos solo introducen los gastos del proyecto en todos los departamentos.

**Estructura organizativa**

- Tanto los departamentos como los proyectos tienen centros de coste.
- Los gestores de proyectos asignan los gastos a cualquier centro de costes autorizado.
- Los responsables de departamento aprueban las asignaciones de proyectos dentro de sus departamentos.

**Requisitos de acceso**

- **Propietarios de departamentos:** acceso completo a todos los gastos de sus departamentos.
- **Gerentes de proyecto:** solo pueden ver/editar los gastos de los proyectos que se les han asignado.
- Ambos perfiles deben ver únicamente los datos relevantes del proyecto/departamento.

**Implementación**

- Asignar a los propietarios de centros de coste la función **de propietario de centro de coste**.
- Conceda permisos de edición a los departamentos pertinentes a través de **los permisos de objetos de coste**.
- Asigne a los gestores de proyectos la función **de gestor de proyectos IIP** o la función **de gestor de cartera IIP**. Los gestores de cartera de IIP pueden gestionar la lista de proyectos y los permisos de los proyectos.
- Habilite «Permitir cualquier centro de costes» en Proyectos si se necesita una asignación entre departamentos.

**Resultado**

- Los propietarios de departamentos ven todos los gastos (de proyectos y operativos).
- Los gestores de proyectos solo ven las líneas en las que **Proyecto = proyecto asignado**.
- Los gestores de proyectos pueden añadir/editar/eliminar gastos de proyectos.
- Los responsables de departamento siguen presentando presupuestos.

**Limitaciones**

- El acceso del gestor de proyectos siempre se filtra para mostrar únicamente los gastos relacionados con el proyecto.

## Funciones y permisos del proyecto

**Funciones estándar:**

- **Gestor de cartera de IIP**
  - Acceso para editar/ver toda la cartera de proyectos.
  - Puede gestionar permisos a nivel de proyecto.
- **Gerente de proyectos del IIP**
  - Editar/ver solo los gastos de los proyectos asignados.

    |  |  |
    | --- | --- |
    | **Permiso** | **Descripción** |
    | **IIPProjectExpenseEdit** | Ver/editar gastos solo para proyectos asignados. |
    | **IIPProjectPermissionManage** | Gestiona los permisos en Proyectos → Permisos. |
    | **IIPProjectManage** | Crear y eliminar proyectos. |

Los usuarios necesitan permisos tanto en Permisos de proyectos como en Permisos de objetos de coste:

|  |  |
| --- | --- |
| **Área de permisos** | **Por qué es necesario** |
| **Proyectos** → **Permiso** | Determina qué proyectos gestiona el usuario. |
| **Permiso de objeto de coste** | Controla el acceso a los departamentos donde se acumulan los costes de esos proyectos. |
