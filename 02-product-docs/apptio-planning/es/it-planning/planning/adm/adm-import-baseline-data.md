---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Importar planes de referencia desde Apptio Cálculo de costes"
breadcrumb:
  - "Planning"
  - "Integraciones"
  - "Conéctese a Apptio Costing"
source_path: "it-planning/planning/adm/adm-import-baseline-data.html"
images:
  - "resources/images/it_planning_images/impbaseline.png"
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Importar planes de referencia desde Apptio Cálculo de costes

Esta función le permite importar datos del plan de referencia desde Apptio Costing a Apptio Planning. Esto resulta útil cuando se desea utilizar un conjunto de datos existente de Apptio Costing como punto de partida para la elaboración de presupuestos o previsiones.

Nota: Estas tareas requieren el rol de administrador con el DataOrchestrationServiceFeatureFullAccess permiso.

Recuerde: La función automatizada Data Management (ADM) está habilitada

## Antes de empezar

Asegúrese de que se cumplan los siguientes requisitos previos:

- **Automatizado Data Management (ADM)** se aprovisiona en su entorno
- ADM está habilitado en Apptio Planificación:
  - Ve a **Configuración (⚙) → Perfil de la empresa.**
  - Seleccionar **Habilitar integración Data Management automatizada**
- **Los conjuntos de datos de integración de planificación** necesarios se instalan en Apptio Costing
- Tienes el rol de administrador con el **DataOrchestrationServiceFeatureFullAccess** permiso.

## Gestión de entidades

Cuando se habilita Automated Data Management (ADM), la página Entity Mapping (Asignación de entidades) de ADM se actualiza automáticamente con las siguientes entidades nuevas:

- **Importar plan de mano de obra** : muestra las partidas de mano de obra en **«Gastos > Mano de obra»**
- **Importar contrato del plan** : muestra las partidas del contrato en **«Gastos > Contratos»**
- **Importar activo del plan** : representa las partidas de activos en **«Gastos > Activos»**
- **Importar datos financieros del plan** : muestra las partidas financieras en **«Gastos > Otros»**
- **Importar plan de actividad laboral** : representa las partidas de actividad laboral en **«Gastos > Actividad laboral»**

Estas entidades permiten la asignación a los conjuntos de datos correspondientes en Apptio Costing. Una vez asignados, los datos de Apptio Costing se pueden importar directamente a las pestañas de gastos correspondientes al plan seleccionado en Apptio Planning.

## Cómo importar un plan de referencia

1. En Apptio Planificación, vaya a **Plan → Gastos**.
2. Habilite la **Nueva Vista** (la importación de planes de referencia desde Apptio Costing solo es compatible con la Nueva Vista).
3. Seleccione la **pestaña Gastos** a la que desea importar (Mano de obra, Actividad de mano de obra, Contratos, Activos u Otros).
4. Abre **el menú de acciones de la tabla de elipsis** y selecciona **Importar desde Apptio Cálculo de costes...**
5. Elija cómo se deben aplicar los datos:
   1. **Reemplazar todos los datos** para sobrescribir los datos existentes, o
   2. **Actualizar datos** para fusionar las actualizaciones en el plan existente utilizando el código de partida individual.
6. Seleccione el **período de Apptio cálculo de costes** del que desea importar los datos.
7. Haga clic en **Importar**. Los datos de referencia se importan al plan utilizando el conjunto de datos de entidades asignadas de Apptio Costing.

![](../../../../../../03-media/apptio-planning/resources/images/it_planning_images/impbaseline.png)

Nota: La *Importar con* ***Actualizar datos*** opción solo está disponible cuando la **Código externo** función está activada. Esta opción actualiza las líneas de plan existentes buscando la coincidencia de un identificador único en los datos importados. Dado que los datos de Planificación proceden de Cálculo de costes, se requiere un identificador único definido por el usuario para garantizar una correspondencia precisa entre los registros de Cálculo de costes y los de Planificación.

Para obtener más información sobre los códigos externos, visita [la sección «Códigos externos».](https://www.ibm.com/docs/en/apptio-commercial/planning-standard/saas?topic=administration-external-codes "(se abre en una pestaña o una ventana nueva)")

**Tema principal:** [Conectarse al sistema de cálculo de costes de « Apptio »](../../../it-planning/planning/adm/adm_capabilities.html "Apptio La planificación se integra con Apptio el cálculo de costes mediante el sistema automatizado Data Management (ADM). ADM es un servicio de plataforma compartida diseñado para proporcionar una experiencia de intercambio de datos unificada, segura y escalable entre Apptio aplicaciones.")
