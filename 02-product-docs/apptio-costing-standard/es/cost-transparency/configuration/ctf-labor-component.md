---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "CTF - Componente laboral: instalar y configurar"
breadcrumb: []
source_path: "cost-transparency/configuration/ctf-labor-component.html"
images:
  - "sout.gif"
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# CTF - Componente laboral: instalar y configurar

Utilice el componente CTF - Mano de obra para importar los costes del proyecto. Este componente no se instala automáticamente con el proyecto estándar Costing Standard . El componente de mano de obra proporciona información sobre el gasto en proyectos por tipo, centro de costes, proyectos y torres de TI.

Se aplica a: Costing Standard en TBM Studio 12.4 y posteriores

## Introducción

La tabla Datos maestros de mano de obra define los datos necesarios para rellenar los informes relacionados con costes y presupuestos. Los datos proporcionan un análisis en profundidad de los costes laborales, tanto de los ETC como de los empleados contratados, incluida la comparación de los costes reales y los efectivos con el plan. Para rellenar la tabla de datos maestros de mano de obra, cargue una tabla de datos de mano de obra y asígnela a la tabla de datos maestros de mano de obra.

## Usos

Utilice los informes del componente CTF - Mano de obra para hacer lo siguiente:

- Gestionar los gastos según el presupuesto
- Identificar las palancas del gasto
- Alinear los gastos con los objetivos empresariales
- Ajustar el gasto a la estrategia
- Confirmar valor o cancelar proyectos

## Instalar el componente

El componente CTF - Labor no se instala con el proyecto estándar Costing Standard .

Para instalar los componentes:

1. Abra el proyecto Costing Standard .
2. En la pestaña Proyecto, haga clic en **Componentes**.
3. Haga clic en el componente **CTF - Mano de obra**.
4. Haga clic en **Instalar**.

La tabla Datos maestros de mano de obra define los datos necesarios para rellenar los informes relacionados con costes y presupuestos. Los datos proporcionan un análisis en profundidad de los costes laborales, tanto de los ETC como de los empleados contratados, incluida la comparación de los costes reales y los efectivos con el plan. Para rellenar la tabla de datos maestros de mano de obra, cargue una tabla de datos de mano de obra y asígnela a la tabla de datos maestros de mano de obra.

## Fuentes de datos habituales

Las cifras laborales suelen extraerse de aplicaciones de RRHH como Oracle EBS, PeopleSoft, Workday y SAP. Los datos deben incluir una lista de empleados e información sobre el seguimiento del tiempo.

La aplicación requiere que los empleados o las actividades de los empleados se asignen a la taxonomía ATUM Torre/Subtorre. Un enfoque común es crear una tabla de asignación fuera de la aplicación y luego cargar la tabla.

## Una carga

Normalmente se carga una única tabla de datos laborales que se anexa a la tabla de Datos Maestros Laborales. La tabla de datos debe contener campos que puedan asignarse a los campos apropiados de la tabla Datos maestros de personal.

## Datos maestros

Para una descripción de los campos de la tabla de datos maestros, véase la información en la página del componente CTF - Mano de obra en el producto. Para visualizar la página:

1. Haga clic en la pestaña **Proyecto**.
2. Haga clic en **Componentes**.
3. Haga clic en el componente **CTF - Mano de obra**.

## Campos obligatorios y recomendados

A continuación se enumeran los campos obligatorios y recomendados necesarios para iluminar los informes laborales estándar de Costing Standard .

- Tipo de compensación (obligatorio)
- Centro de costes (obligatorio)
- Nombre del centro de costes (obligatorio)
- Pool de costes (obligatorio)
- Subgrupo de costes (recomendado)
- Tipo de empleado (obligatorio)
- Subpotencia de recursos informáticos (obligatorio)
- Torre de recursos informáticos (obligatorio)
- Plantilla laboral (obligatorio)
- Identificación laboral (obligatoria)
- Nombre del trabajador (obligatorio)
- Lugar (obligatorio)
- Plantilla prevista (obligatorio)
- Cargo (obligatorio)
- ID del proyecto (recomendado)
- Región (obligatorio)
- Identificador único (obligatorio)

## Información relacionada

- ![](../../../../../03-media/apptio-costing-standard/sout.gif)[Enviar comentarios sobre el Centro de ayuda](productfeedback@apptio.com "(se abre en una pestaña o una ventana nueva)")
