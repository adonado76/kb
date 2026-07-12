---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Reglas de visibilidad de las pestañas"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Componentes"
  - "Tabuladores"
source_path: "studio/report-studio/components/tab-visible.html"
images:
  - "resources/images/studio_images/tbr2.png"
  - "resources/images/studio_images/tvr1.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Reglas de visibilidad de las pestañas

Puedes controlar si una pestaña es visible u oculta para los usuarios que consultan los informes definiendo una regla de visibilidad.

**Configuración de una regla de visibilidad**

![Imagen de la opción de regla de visibilidad de pestañas](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/tvr1.png)

![Imagen de la ventana emergente de visibilidad de la pestaña con regla de visibilidad](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/tbr2.png)

Cada pestaña de un grupo de pestañas (Pestañas) incluye un **menú desplegable** que ofrece opciones de configuración adicionales.

Para definir una regla de visibilidad:

1. Abre el **menú de opciones** de la pestaña.
2. Selecciona «**Regla de visibilidad** ».
3. Introduce la expresión que determina si la pestaña debe estar visible.

La pestaña se mostrará u ocultará a los usuarios en el visor de informes en función del resultado de la expresión de visibilidad.

**Comportamiento predeterminado**

- La primera pestaña de un grupo de pestañas siempre permanece visible.
- Por este motivo, la opción «Regla de visibilidad» está desactivada en la primera pestaña.
- Las reglas de visibilidad solo se pueden configurar para las pestañas siguientes.

**Estados de visibilidad**

Una pestaña puede encontrarse en uno de los siguientes estados:

- **Visible** : la pestaña se muestra a los usuarios cuando consultan el informe.
- **Oculto** : la pestaña no se muestra a los usuarios cuando consultan el informe.

El estado de visibilidad viene determinado por el **resultado de la expresión configurada**.

**Ejemplo**

Puedes crear una regla de visibilidad que permita a los administradores ver una pestaña, pero que la mantenga oculta para los usuarios finales.

Regla de visibilidad: `<%=IF(eval({$CurrentUser}:
{Users.Role})=Admin,enabled,hidden)%>`

Esto permite a los administradores de informes mostrar información específica solo a determinados roles de usuario.

**Tema principal:** [Pestañas](../../../studio/report-studio/components/rs-tabs.html "El componente «Pestañas» te permite organizar el contenido de un informe en varias pestañas dentro de un mismo informe. Cada pestaña puede contener su propia disposición de componentes y visualizaciones, lo que ayuda a estructurar informes complejos en secciones claras y fáciles de navegar.")
