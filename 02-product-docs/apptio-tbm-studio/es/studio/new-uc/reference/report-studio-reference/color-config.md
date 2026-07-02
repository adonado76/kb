---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Configuración de colores"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/color-config.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Configuración de colores

**Paletas de colores personalizadas**

**Aplicable a:** TBM Studio 12.10.10 y versiones posteriores

Puedes aplicar paletas de colores personalizadas a la mayoría de los tipos de gráficos. Accede a las paletas de colores desde la pestaña «Informe» > opción «Paleta de colores». Las paletas se pueden aplicar a nivel de informe o a nivel de colección de informes.

**Limitaciones:** Las paletas de colores personalizadas no se pueden aplicar a los gráficos de árbol ni a los gráficos en cascada. Las paletas de colores tampoco afectan a las tablas, los colores de las fuentes y las etiquetas, los segmentadores, los fondos ni los componentes de los KPI.

**Sintaxis de Color Spec**

Para controlar con precisión los colores de cada métrica, utiliza la propiedad «Color Spec». Introduzca las especificaciones de color en el siguiente formato:

`metric=color-spec[;metric=color-spec]`

**Ejemplo:** `Cost=blue;Budget=green;!purple`

Esto establece el color azul para «Coste», el verde para «Presupuesto» y excluye el morado de la asignación automática de colores.

**Palabras clave de colores disponibles**

**Colores lisos:** negro, gris, gris claro, gris oscuro, blanco, transparente

**Colores degradados:** azul, rojo, verde, amarillo, violeta, marrón, azul cielo, verde claro, naranja, azul oscuro, verde oscuro, morado, aguamarina, rosa, verde azulado, carmesí

**Consejo:** Añade el prefijo «flat» a los colores degradados para obtener versiones sin degradado (por ejemplo, flatblue). También se admiten códigos hexadecimales (por ejemplo, Cost=#082f6d ).

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
