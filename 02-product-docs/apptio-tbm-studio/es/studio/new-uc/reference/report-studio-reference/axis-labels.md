---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Etiquetas y formato de ejes"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/axis-labels.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Etiquetas y formato de ejes

**Truncamiento de etiquetas**

Las etiquetas que aparecen en los ejes X e Y tienen una longitud máxima de 20 caracteres. Si una etiqueta supera esta longitud, se eliminan caracteres del centro de la misma y se sustituyen por puntos suspensivos. Esto garantiza que las etiquetas sigan siendo legibles y que quepan en el espacio disponible.

**Ejemplo:** «aaaa bbbb cccc dddd eeee ffff 0001» se truncaría y se mostraría como «aaaa bb...fff 0001»

**Formato de los números**

Utiliza la propiedad «Formato numérico del gráfico» para controlar cómo se muestran los números en los ejes del gráfico. El formato utiliza patrones de formato numérico estándar:

|  |  |  |
| --- | --- | --- |
| **Patrón** | **Ejemplo de entrada** | **Ejemplo de resultado** |
| #,### | 5000000 | 5 000 000 |
| # | 5000000 | 5 000 000 (sin formato) |
| ¤#,### | 5000000 | 5 000 000 $ (moneda local) |

Consejo: Utiliza el símbolo universal de la moneda (¤) en el campo de prefijo o formato para que se muestre el símbolo de la moneda correspondiente a la configuración regional. Para introducir este símbolo, cópialo de la documentación o del cuadro de diálogo de propiedades.

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
