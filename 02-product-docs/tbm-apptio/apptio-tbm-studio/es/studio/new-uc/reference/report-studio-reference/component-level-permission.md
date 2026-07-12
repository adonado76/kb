---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Permisos a nivel de componente"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Permisos del informe"
source_path: "studio/new-uc/reference/report-studio-reference/component-level-permission.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Permisos a nivel de componente

**Ocultar componentes por función**

Los componentes individuales de un informe pueden ocultarse a determinados roles, sin dejar de ser visibles para otros. Esto permite crear informes polivalentes que muestran información diferente en función del rol del usuario.

**Configuración de la visibilidad de los componentes:**

1. Selecciona el componente en el informe
2. En la pestaña Informe, en el grupo Avanzadas, haz clic en Visibilidad
3. Seleccionar el rol actual del usuario es una opción
4. Selecciona los roles que deben tener acceso al componente
5. Guarda y revisa el informe

**Opciones de visibilidad**

El cuadro de diálogo «Visibilidad de los componentes del informe» ofrece varias condiciones de visibilidad:

|  |  |
| --- | --- |
| **Opción** | **Comportamiento** |
| **El componente contiene datos** | Ocultar el componente si no contiene datos |
| **El rol actual del usuario es** | Mostrar solo a los roles seleccionados |
| **El texto dinámico no se evalúa como «oculto»** | Visibilidad condicional basada en una fórmula |

**Tema principal:** [Permisos de informes](../../../../studio/new-uc/reference/report-studio-reference/report-permissions.html)
