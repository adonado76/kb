---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Herencia"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Informes principales"
source_path: "studio/new-uc/reference/report-studio-reference/inheritance.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Herencia

**Cómo los informes secundarios heredan de los principales**

Cuando se aplica un informe maestro a un informe personalizado (secundario), el contenido del informe maestro aparece como una capa de fondo. El informe secundario hereda el aspecto visual y los elementos interactivos definidos en el informe principal, pero el modelo de herencia sigue el concepto de «fondo»:

- Los componentes principales se representan primero, formando la capa base
- Los componentes del informe secundario se muestran sobre la capa principal
- Las dos capas se combinan visualmente, pero siguen estando separadas funcionalmente

**¿Qué es Inherited?**

- **Estructura de diseño** : cuadros de grupo, contenedores visuales y organización espacial
- **Componentes estáticos** : botones, notas, logotipos y elementos de marca
- **Elementos interactivos** : componentes con pestañas (las pestañas funcionan cuando se aplica el elemento principal)
- **Navegación** : enlaces y botones que permiten desplazarse entre informes

**Lo que NO se hereda**

- **Edición** : los componentes principales no se pueden modificar desde el informe secundario
- **Agrupación de componentes** : los cuadros de grupo pierden su funcionalidad de agrupación en los informes secundarios
- **Áreas de contenido de los componentes de las pestañas** : no se pueden añadir componentes a pestañas concretas dentro del informe secundario
- **Enlaces de datos** : las configuraciones de datos específicas de cada informe son exclusivas de cada uno de ellos

**Tema principal:** [Informes maestros](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
