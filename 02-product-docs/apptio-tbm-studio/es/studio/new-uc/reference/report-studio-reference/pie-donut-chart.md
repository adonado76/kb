---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Gráficos circulares y de rosquilla"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/pie-donut-chart.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Gráficos circulares y de rosquilla

Los gráficos circulares representan los datos en forma de porciones proporcionales de un círculo, lo que los hace ideales para mostrar cómo las partes contribuyen al todo. TBM Studio ofrece cuatro variantes de gráficos circulares para adaptarse a las distintas necesidades de presentación.

**Variantes del gráfico circular**

|  |  |
| --- | --- |
| **Variante** | **Descripción** |
| Estándar | Gráfico circular completo en el que todas las porciones se representan como segmentos proporcionales. |
| Media estándar | Gráfico circular semicircular que muestra los datos en un arco de 180 grados. Útil cuando el espacio vertical es limitado. |
| Anillo | Un círculo completo con el centro hueco, que deja espacio para los KPI o un texto resumen. |
| Media rosquilla | Gráfico de rosquilla semicircular que combina el formato de semicírculo con un centro hueco. |

**Comportamiento del gráfico circular**

**Importante:** Los gráficos circulares solo funcionan con números positivos. Si tus datos contienen valores negativos, en lugar del gráfico aparecerá un mensaje indicando que hay datos incorrectos.

Un gráfico circular siempre muestra sectores que representan el total (100 %) del valor que se representa en el gráfico. Si limitas la visualización para que solo se muestren los elementos principales (mediante la opción «Máximo de filas»), se añade automáticamente una sección adicional denominada «Otros» para representar el porcentaje restante. La otra sección no se puede ocultar.

**Sección desmontada**

Puedes resaltar una porción concreta «separándola», lo que hace que la porción quede ligeramente separada del resto del gráfico circular. Hay dos formas de crear una sección desmontada:

- Haz clic con el botón derecho del ratón en un segmento del gráfico y selecciona «Descomponer» en el menú contextual.
- Introduce el nombre de la sección en el campo «Sección desglosa» del cuadro de diálogo «Propiedades del gráfico».

**Propiedades del gráfico circular**

Las propiedades del gráfico circular se encuentran en la pestaña «Circular» del cuadro de diálogo «Propiedades». Entre las opciones principales se incluyen la ubicación de las etiquetas, los porcentajes de los segmentos y el estilo visual. Prueba las diferentes opciones hasta conseguir la presentación que deseas.

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
