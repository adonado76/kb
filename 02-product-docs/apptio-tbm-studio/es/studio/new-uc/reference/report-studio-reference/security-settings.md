---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Valores de seguridad"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Propiedades de informe"
source_path: "studio/new-uc/reference/report-studio-reference/security-settings.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Valores de seguridad

La configuración de seguridad de los informes determina qué usuarios y roles pueden ver los informes e interactuar con ellos. Los permisos se pueden configurar a nivel de la colección de informes y ser heredados por los informes individuales, o bien establecerse específicamente para cada informe.

**Permisos del informe**

**Para configurar los permisos de los informes:**

1. Echa un vistazo al informe
2. Ve a la pestaña «Informes» > «Permisos» (o a la pestaña «Proyecto» > grupo «Avanzado» > «Permisos»)
3. Selecciona los roles que deben tener acceso
4. Haz clic en «Aceptar» para aplicar los cambios

**Opciones de permisos:**

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Todo el mundo | Todos los usuarios con acceso al proyecto pueden ver el informe. Esta es la configuración más permisiva. |
| Funciones específicas | Solo los usuarios asignados a los roles seleccionados pueden ver el informe. Se pueden seleccionar varias opciones. |

**Permisos para la recopilación de informes**

Los permisos establecidos a nivel de la colección de informes se aplican a todos los informes de la colección, a menos que se anulen a nivel de cada informe concreto. Esto permite gestionar de forma eficaz los permisos para grupos de informes relacionados.

**Visibilidad de los componentes**

Los componentes individuales de un informe pueden tener reglas de visibilidad que controlan cuándo y a quién se muestran:

|  |  |
| --- | --- |
| **Regla de visibilidad** | **Comportamiento** |
| El componente contiene datos | Oculta el componente si no contiene ni calcula datos |
| El rol actual del usuario es | Muestra el componente solo a los usuarios con los roles especificados |
| El texto dinámico se evalúa como «oculto» | Oculta el componente en función de una fórmula o una condición de datos |

**Para configurar la visibilidad de un componente:** Selecciona el componente y, a continuación, ve a la pestaña Informe > grupo Avanzado > Visibilidad

**Tema principal:** [Propiedades del informe](../../../../studio/new-uc/reference/report-studio-reference/report-properties.html)
