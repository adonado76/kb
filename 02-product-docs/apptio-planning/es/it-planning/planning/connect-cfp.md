---
source_system: "apptio-planning"
practice: "tbm"
language: "es"
doc_type: "it-planning"
title: "Conéctate a Cloudability Financial Planning"
breadcrumb:
  - "Planning"
  - "Integraciones"
source_path: "it-planning/planning/connect-cfp.html"
images: []
capability_ids: []
last_updated: "2026-06-23"
summary: ""
---
# Conéctate a Cloudability Financial Planning

Importante: Disponible con la *suscripción* ***al estándar de planificación « Apptio ».***

Recuerde: La nueva vista está habilitada.

La integración de Cloud Financial Planning (CFP) permite a Apptio Planning incorporar presupuestos y previsiones en la nube directamente desde IBM Cloudability en los flujos de trabajo de planificación.

Con esta integración, las organizaciones pueden alinear los planes financieros en la nube creados en CFP con los presupuestos y previsiones departamentales en Apptio Planning. Las partidas de previsión en la nube importadas desde CFP se asignan automáticamente a las estructuras financieras de Planning, lo que reduce la duplicación de esfuerzos y mejora la coherencia entre la planificación financiera en la nube y la de la empresa.

La integración es opcional. Los clientes pueden utilizar la pestaña «Cloud» en Apptio Planning para gestionar los gastos específicos de la nube independientemente de CFP. Cuando se conecta CFP, los presupuestos y previsiones importados de la nube pueden coexistir con los gastos de la nube introducidos directamente en Planning, lo que proporciona flexibilidad para complementar los datos de CFP cuando sea necesario.

Esta función permite una planificación financiera en la nube más precisa, optimizada y conectada entre sistemas.

**Características principales:**

**Pestaña Nube**

- Los clientes pueden habilitar una nueva **pestaña «Cloud»** en la nueva vista «Expenses» para gestionar los costes de la nube directamente desde « Apptio » «Budgets and Forecasts».
- La pestaña Cloud se puede habilitar de forma independiente y no requiere integración con CFP.

**Integración CFP**

- Los clientes pueden conectar Apptio Planning con Cloud Financial Planning (CFP) para importar presupuestos y previsiones en la nube desde CFP con una sola acción.
- Los gastos de nube importados se asignan automáticamente a la estructura financiera de Planning.

## Requisitos previos

Antes de habilitar Cloud Planning o la integración CFP:

1. Apptio Se requiere una licencia estándar de planificación.
2. La integración CFP **solo** admite calendarios fiscales gregorianos (no se admiten los calendarios 445 y 13‑Period ). La pestaña Nube funciona con todos los calendarios fiscales compatibles
3. Se debe habilitar **la nueva experiencia de la página Gastos (Beta)**.

## Habilitación de la planificación en la nube y la integración de CFP

***Nota:*** *Para realizar estas tareas se requieren los roles de administrador o responsable del proceso presupuestario.*

1. Vaya a **Configuración** **(icono de engranaje)** → **Perfil de la empresa**.
2. Asegúrate de que **la experiencia de la página Nuevos gastos (Beta)** esté habilitada primero; la pestaña Nube no se puede utilizar sin ella. Para habilitar la función, siga estos pasos:
   - **Configuración general** → **Acceso y permisos** → Seleccionar **Habilitar nueva experiencia de página de gastos (Beta)**
3. Seleccione **Planificación en la nube** → **Habilitar planificación en la nube.** Este paso habilita la pestaña Nube en Gastos.
4. Para conectarse a la planificación financiera en la nube (CFP) de IBM Cloudability, seleccione **Planificación en la nube** → **Habilitar integración de planificación financiera en la nube.**
5. Haga clic en el botón **Guardar y salir.**

## Permisos

Puedes controlar quién puede ver o editar los gastos en la nube:

- **ViewCloud -** Permite ver y editar líneas en la pestaña Nube.
- **CanImportFromCloudability -** Permite importar datos desde CFP y eliminar las líneas importadas.
- De forma predeterminada, ambos permisos se conceden a los roles **de administrador** y **propietario del proceso presupuestario**, y **el propietario del centro de costes** solo tiene un permiso **de ViewCloud**.

- **[Gestionar los gastos en la nube (sin integración con CFP)](../../it-planning/planning/manage-cfp-wo-int.html)**
- **[Configurar y gestionar la integración de la planificación financiera en la nube](../../it-planning/planning/cfp-integration.html)**
