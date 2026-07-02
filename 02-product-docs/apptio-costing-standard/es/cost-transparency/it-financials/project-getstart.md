---
source_system: "apptio-costing-standard"
practice: "tbm"
language: "es"
doc_type: "cost-transparency"
title: "Proyectos Primeros pasos"
breadcrumb:
  - "Costing Standard"
  - "Casos de uso financiero"
  - "Proyectos"
source_path: "cost-transparency/it-financials/project-getstart.html"
images: []
capability_ids: []
last_updated: "2026-06-09"
summary: ""
---
# Proyectos Primeros pasos

## Cómo empezar

Utilice la función Proyectos para realizar un seguimiento, analizar y gestionar el gasto en proyectos de TI en todos los centros de costes, proyectos y torres de TI. El componente **CTF – Proyectos** permite visualizar las inversiones en proyectos, el cumplimiento del presupuesto y las tendencias de gasto, lo que favorece un mejor control financiero y una mayor alineación estratégica.

Antes de utilizar los informes de proyectos, instale el componente necesario y cargue los datos de costes del proyecto en la tabla de datos maestros.

## Instalación de componentes

**CTF - Proyectos**

El componente CTF-Proyectos proporciona la estructura de datos necesaria para analizar el gasto de los proyectos por tipo, centro de costes, proyecto y torre de TI.

**Requisitos previos**

- CTF: Fuente de costes
- CTF- Trabajo
- CTF: Unidades de trabajo o CTF: Seguimiento del tiempo

Después de instalar el componente, debe cargar los datos del proyecto y asignarlos a la tabla **de datos maestros de proyectos** para habilitar la generación de informes y el análisis del gasto del proyecto.

**Fuentes comunes de datos**

Los datos del proyecto suelen proceder de aplicaciones de gestión de proyectos y carteras que realizan un seguimiento de las finanzas, los plazos y la propiedad del proyecto. Estos sistemas proporcionan detalles como los presupuestos de los proyectos, el gasto real, el estado de los proyectos y la clasificación de las inversiones.

Las fuentes comunes incluyen ServiceNow, Project Portfolio Suite, Clarity PPM, Jira Align / Jira Advanced Roadmaps, MS Project Online / Project Server, Planview, etc.

## Conjuntos de datos maestros

**Tabla de datos maestros de proyectos:** Define los datos necesarios para la presentación de informes sobre los costes y el presupuesto de los proyectos. Para rellenar esta tabla, cargue un conjunto de datos del proyecto y asígnelo a los campos correspondientes de la tabla de datos maestros. Normalmente, se carga un único conjunto de datos de proyecto, que se añade y se asigna a la tabla de datos maestros de proyectos.

**Tabla de correspondencias entre proyectos y aplicaciones:** esta tabla se utiliza para asociar los proyectos con las aplicaciones a las que afectan. Este mapeo permite visualizar cómo las inversiones en proyectos contribuyen a los esfuerzos de modernización, cambio y costes de las aplicaciones.
