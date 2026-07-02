---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Visibilidad a nivel de componente"
breadcrumb:
  - "TBM Studio"
  - "Conceptos y arquitectura"
  - "Modelo de seguridad"
  - "Permisos de informes y componentes"
source_path: "studio/new-uc/concepts-architecture/security-model/component-level-visibility.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Visibilidad a nivel de componente

Para un control más preciso, puedes configurar los componentes individuales del informe para que se muestren u oculten en función de determinadas condiciones.

**Opciones de visibilidad**

Cada componente del informe admite varias opciones de visibilidad:

- **El componente contiene datos:** oculta el componente si no contiene ni calcula datos.
- **El rol actual del usuario es:** muestra el componente solo a los usuarios con roles específicos. Esto te permite crear un único informe que muestre diferentes elementos a distintos públicos.
- **El texto dinámico da como resultado «oculto»:** oculta el componente en función de una condición calculada; por ejemplo, oculta un componente de varianza cuando la varianza es positiva.

**Patrón de visibilidad de componentes basado en roles**

Una práctica habitual consiste en crear grupos de informes que contengan componentes específicos para cada función y, a continuación, superponer estos grupos en la misma superficie de informe. Cada grupo está configurado para que solo sea visible para un rol. Cuando un usuario abre el informe, solo ve los componentes correspondientes a su función.

Nota:

**Varios roles**

Si un usuario tiene dos de los roles a los que pueden acceder diferentes grupos, verá los componentes del rol cuyo grupo se encuentre en la parte superior de la pila. Diseña cuidadosamente la estructura de tu grupo de informes para poder gestionar a los usuarios con múltiples roles.

**Tema principal:** [Permisos de informes y componentes](../../../../studio/new-uc/concepts-architecture/security-model/report-component-permission.html)
