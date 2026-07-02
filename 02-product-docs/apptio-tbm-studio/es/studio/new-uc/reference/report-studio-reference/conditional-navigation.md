---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Navegación condicional"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Navegación"
source_path: "studio/new-uc/reference/report-studio-reference/conditional-navigation.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Navegación condicional

Controla la visibilidad y el comportamiento de los componentes de navegación en función de los valores de los datos, los roles de los usuarios u otras condiciones. La navegación condicional garantiza que los usuarios solo vean las opciones de navegación relevantes.

**Condiciones de los botones**

Utiliza fórmulas en el campo «Habilitado» de las propiedades del botón para controlar la disponibilidad del botón:

**Activar el botón cuando el coste supere el umbral:**

`<%=IF(Cost>5000,"enabled","disabled")%>`

**Ocultar el botón cuando no haya datos:**

`<%=IF(RowCount()=0,"hidden","enabled")%>`

**Visibilidad de los componentes por rol**

Controla qué componentes de navegación se muestran en función del rol asignado al usuario:

1. Selecciona el componente de navegación (botón, cuadro de grupo que contenga elementos de navegación, etc.)
2. En el grupo «Avanzado» de la pestaña «Informe», haz clic en «Visibilidad»
3. Selecciona el rol actual del usuario y elige los roles que deben tener acceso a este componente
4. Los usuarios que no tengan asignados los roles seleccionados no verán el componente

**Visibilidad dinámica del texto**

Utiliza la opción de visibilidad «El texto dinámico no se evalúa como "oculto"» para mostrar u ocultar la navegación de forma condicional en función de valores calculados. Si la fórmula devuelve «oculto», el componente desaparece.

**Tema principal:** [Componentes del informe: Navegación](../../../../studio/new-uc/reference/report-studio-reference/report-component-navigation.html)
