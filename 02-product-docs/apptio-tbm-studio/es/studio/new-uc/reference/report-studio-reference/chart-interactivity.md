---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Funciones interactivas de los gráficos"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Gráficos"
source_path: "studio/new-uc/reference/report-studio-reference/chart-interactivity.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Funciones interactivas de los gráficos

**Información sobre herramientas**

Cuando los usuarios pasan el cursor por encima de los elementos del gráfico, aparecen ventanas emergentes con información contextual:

- Gráficos de barras: La información sobre herramientas muestra el valor de la barra.
- Gráficos de barras apiladas: La información sobre herramientas muestra tanto el valor como el porcentaje del segmento.
- Gráficos circulares: La información sobre herramientas muestra el valor de cada sector y su porcentaje respecto al total.
- Gráficos en cascada: cuando la opción «Explicación en las descripciones emergentes» está activada, la descripción emergente incluye el texto explicativo.

**Interacción con la leyenda**

En todos los gráficos que incluyen leyendas, los usuarios pueden hacer clic en los elementos de la leyenda para mostrar u ocultar series de datos específicas. Los elementos ocultos aparecen en gris. Esto permite a los usuarios centrarse en datos concretos sin modificar la configuración del gráfico. Cuando se ocultan elementos, los cálculos porcentuales (como en los gráficos apilados) se ajustan para reflejar únicamente los elementos visibles.

**Acercar (gráficos de líneas)**

Los gráficos de líneas permiten el zoom interactivo. Haz clic y arrastra el cursor horizontalmente por el gráfico para ampliar un periodo de tiempo concreto. En la esquina superior derecha aparece un enlace «Restablecer zoom» para volver a la vista completa. Los niveles de zoom se restablecen automáticamente al salir del informe.

**Integración de Slicer**

Los gráficos creados con la configuración de componentes ad hoc responden a los filtros de datos del mismo informe. Cuando los usuarios seleccionan valores en un filtro, el gráfico se filtra automáticamente para mostrar solo los datos que coinciden. Esto se aplica a todos los tipos de gráficos, excepto a los gráficos en cascada (que responden a los filtros, pero con un comportamiento especial en los pasos intermedios).

**Tema principal:** [Componentes del informe: Gráficos](../../../../studio/new-uc/reference/report-studio-reference/report-component-charts.html)
