---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Conceptos básicos de los informes"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Informes principales"
source_path: "studio/new-uc/reference/report-studio-reference/master-report-concepts.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Conceptos básicos de los informes

**¿Qué es un informe maestro?**

Un informe maestro es un tipo especial de informe que define elementos de diseño reutilizables que pueden aplicarse a varios informes secundarios, a modo de plantilla. El concepto es similar al de las diapositivas maestras en aplicaciones de presentaciones como PowerPoint. Cuando se aplica un informe maestro a un informe personalizado, los componentes del informe maestro aparecen como una capa de fondo (a menudo denominada «fondo de pantalla») que proporciona una estructura visual coherente.

Los informes maestros pueden incluir todos los componentes disponibles en los informes normales, como botones, cuadros de grupo, elementos de acción, encabezados y elementos de navegación. Sin embargo, su objetivo principal es establecer un marco coherente en el que se incluya el contenido específico de cada informe.

**Diferencias entre el informe maestro y el informe estándar**

|  |  |  |
| --- | --- | --- |
| **Aspecto** | **Informe general** | **Informe periódico** |
| **Finalidad** | Plantilla para varios informes | Informe independiente para usuarios finales |
| **Nivel de jerarquía** | Siempre de nivel superior por defecto | Puede ser cualquier nivel de la jerarquía |
| **Edición de componentes** | Componentes estáticos en los informes secundarios | Todos los componentes son totalmente editables |
| **Disponibilidad** | Aparece en el menú desplegable «Masters» | Aparece en el Explorador de proyectos |
| **Eliminación** | Las plantillas estándar no se pueden eliminar | Se puede eliminar (excepto el contenido predeterminado) |

**Casos de uso de los informes maestros**

Los informes maestros son ideales para situaciones en las que se necesita una presentación uniforme en varios informes:

- **Identidad corporativa** : Utiliza los logotipos, colores y estilo de la empresa de forma coherente en todos los informes de un proyecto
- **Estructuras de navegación** : Establecer botones y enlaces de navegación uniformes que guíen a los usuarios a través de un conjunto de informes
- **Estandarización del diseño** : definir una ubicación coherente de los encabezados, los pies de página y las áreas de contenido
- **Conjuntos de filtros comunes** : proporcionan segmentadores y filtros compartidos que se aplican a todos los informes relacionados
- **Colecciones de informes** : Crea una imagen y un estilo coherentes para un conjunto de informes analíticos relacionados

**El modelo del papel pintado**

Piensa en los informes maestros como si fueran un papel pintado. Cuando se aplican a un informe personalizado, los componentes de un informe maestro:

- No se puede editar ni modificar desde el informe secundario
- Aparecer como una capa de fondo estática
- Los componentes que añadas al informe secundario se sitúan «por encima» de los componentes principales
- Solo se puede modificar editando directamente el informe maestro

Consejo: Por ejemplo, si el informe principal incluye un cuadro de grupo, puedes colocar los componentes en el informe secundario de manera que, aunque visualmente aparezcan dentro del cuadro de grupo, en realidad no estén vinculados ni agrupados con el cuadro de grupo del informe principal.

**Tema principal:** [Informes maestros](../../../../studio/new-uc/reference/report-studio-reference/master-report.html)
