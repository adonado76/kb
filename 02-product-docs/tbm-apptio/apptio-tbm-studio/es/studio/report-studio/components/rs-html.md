---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "HTML"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Componentes"
source_path: "studio/report-studio/components/rs-html.html"
images:
  - "resources/images/studio_images/html.png"
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# HTML

El componente HTML le permite incrustar contenido HTML personalizado directamente en un informe. Es útil para añadir texto enriquecido, enlaces, imágenes o diseños personalizados que no están disponibles a través de los componentes estándar.

## Cuándo utilizar HTML

Utilice el componente HTML cuando desee:

- Añadir texto con formato, como encabezados, párrafos o listas
- Incluye hipervínculos a recursos externos o internos
- Mostrar imágenes estáticas o iconos
- Proporcionar contenido explicativo, avisos legales o anotaciones dentro de un informe

## Añadir un componente HTML al informe

1. Añadir un HTML desde el panel Componentes de la barra de herramientas
2. Haga clic en el HTML para habilitar los paneles Datos y Formato.
3. Panel de datos
   1. Seleccione el objeto modelo en la lista desplegable
   2. Arrastre las dimensiones desde el Explorador de dimensiones a las secciones de filas, columnas, valores y filtros del panel de datos
4. Panel de formato
   1. Propiedades generales: consulte [Propiedades de los componentes.](components.html#abt-comp__comprop)
   2. Propiedades específicas de HTML
      1. Haga clic en el icono de maximizar o introduzca el **contenido** HTML en el cuadro de texto.

Ejemplo: HTML

![html](../../../../../../03-media/apptio-tbm-studio/resources/images/studio_images/html.png)

HTML admite fórmulas personalizadas y dimensiones de fórmulas. Para obtener más información, consulte [Fórmulas personalizadas.](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas dimensiones de fórmula) le permiten definir nuevas dimensiones calculadas utilizando campos existentes en su modelo de datos. Esto permite realizar análisis más profundos y obtener información más detallada sin necesidad de realizar cambios en el conjunto de datos o el esquema subyacentes.")
