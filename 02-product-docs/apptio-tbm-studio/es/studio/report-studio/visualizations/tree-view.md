---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Vista de árbol"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "ApptioIBM Report Studio (Nuevo)"
  - "Visualizaciones"
  - "Tabla"
source_path: "studio/report-studio/visualizations/tree-view.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Vista de árbol

**La vista de árbol** te permite visualizar datos jerárquicos directamente en una tabla. En lugar de mostrar todas las filas en una lista plana, la vista de árbol organiza los datos en niveles que se pueden expandir y contraer, lo que facilita explorar las relaciones y profundizar en los detalles de forma progresiva.

Esto resulta especialmente útil cuando los datos presentan relaciones jerárquicas naturales, como por ejemplo:

- Centros de coste → Cuentas → Subcuentas
- Unidades de negocio → Equipos → Aplicaciones
- Categorías → Subcategorías → Artículos

**Úsalo cuando**

- Tu tabla utiliza varios campos en la configuración de «Filas»
- Prefieres navegar por los datos de forma jerárquica, en lugar de recorrer una tabla larga y plana
- Quieres controlar la cantidad de detalles que se ven a la vez

**Cómo utilizar la vista de árbol**

1. Abrir una mesa
2. Activa la opción **«Mostrar como árbol»** en las propiedades de formato
3. Asegúrate de añadir varios campos a la sección «Filas»
4. Una vez activada, al principio solo se muestran las filas de nivel superior (raíz).
5. Los iconos para expandir y contraer aparecen junto a las filas que contienen datos secundarios.
6. Despliega una fila para ver el siguiente nivel de la jerarquía.
7. Oculta una fila para ocultar todas las filas secundarias que contiene.

Nota:

- Las filas secundarias aparecen justo debajo de la fila principal, conservando así el contexto. Esto te permite explorar los datos de forma gradual sin perder de vista la relación con el elemento principal.
- La vista de árbol solo funciona con dimensiones de un único objeto, y no con dimensiones de varios objetos.

**Creación de jerarquías**

Cuando la vista en árbol está activada:

- La jerarquía de la tabla se crea utilizando los campos añadidos a la sección «Filas».
- El orden de los campos define la jerarquía:
- Primer campo → Nivel raíz
- Segundo campo → Nivel secundario
- Campos siguientes → Niveles más profundos

Cada fila se puede desplegar para mostrar sus elementos secundarios directos.

Cuando la vista en árbol está desactivada:

- La tabla se muestra como una tabla plana estándar
- No se muestran jerarquías ni controles para expandir o contraer
- Todas las filas aparecen al mismo nivel

**Configuración de número máximo de niños**

La configuración «Número máximo de hijos» te permite controlar cuántas filas secundarias se muestran debajo de cada nodo principal.

Cómo funciona

- Predeterminado (Mostrar todo):

  Cuando se despliega, se muestran todas las filas secundarias de una fila principal.
- Valor definido por el usuario (n):

  Solo se muestran las primeras n filas secundarias de cada fila principal.

Esto resulta útil para:

- Evitar ampliaciones de gran envergadura
- Mejorar la legibilidad y el rendimiento
- Centrarse en los primeros registros de hijos

Nota: El valor de «Max Children» se aplica por nodo, no a toda la tabla.

## Ajusta el texto automáticamente a las cabeceras y celdas de las tablas

Las tablas ahora admiten el ajuste automático del texto tanto en los encabezados de columna como en las celdas, lo que mejora la legibilidad y garantiza que el contenido sea totalmente visible sin necesidad de cambiar manualmente el tamaño.

La tabla admite fórmulas personalizadas y dimensiones de fórmula. Para obtener más información, consulta [«Fórmulas personalizadas»](../create-first/custom-formula.html "Las fórmulas personalizadas (también denominadas «dimensiones de fórmula») te permiten definir nuevas dimensiones calculadas utilizando campos existentes en tu modelo de datos. Esto permite realizar análisis más exhaustivos y obtener información más detallada sin necesidad de modificar el conjunto de datos ni el esquema subyacentes.")

**Tema principal:** [Tabla](../../../studio/report-studio/visualizations/rs-table.html "El componente de tabla muestra los datos en un formato tabular estructurado. Es ideal para mostrar información detallada, resumir métricas y facilitar el filtrado interactivo dentro de un informe.")
