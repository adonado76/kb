---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Tipos de componentes de filtro y segmentador"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: filtros y segmentadores"
source_path: "studio/new-uc/reference/report-studio-reference/filter-slicer-types.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Tipos de componentes de filtro y segmentador

**Componentes de la cortadora**

TBM Studio ofrece varios tipos de cortadores para adaptarse a las distintas necesidades de filtrado:

**Filtro de filas (Filtro de lista)**

El tipo de segmentador predeterminado para campos de texto y categóricos. Muestra los valores en forma de lista en la que se puede seleccionar, y los usuarios pueden hacer clic para filtrar los datos.

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Tipo de datos | Campos de texto/etiqueta |
| Modalidad de selección | Selección múltiple (Ctrl + clic para seleccionar varios) |
| Visualización | Lista de valores con sus estados (Seleccionado, Relacionado, No relacionado) |
| Valores máximos | 250 valores por segmentador |

**Cuándo utilizarlo:** filtrado por categorías, selección de dimensiones y cualquier campo de texto en el que los usuarios deban elegir entre valores concretos.

**Control deslizante numérico**

Se crea automáticamente al añadir un campo numérico a un filtro. Ofrece un control deslizante de rango para filtrar datos numéricos.

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Tipo de datos | Campos numéricos |
| Modalidad de selección | Selección de rango mediante controles deslizantes |
| Visualización | Control deslizante horizontal con controles de mínimo y máximo |
| Operadores | Admite «mayor que», «menor que» y «entre» |

**Cuándo utilizarlo:** umbrales de coste, rangos de cantidad y cualquier métrica numérica en la que los usuarios necesiten filtrar por rangos de valores.

**Filtro jerárquico**

Permite aplicar filtros de desglose a través de varios niveles de una jerarquía (por ejemplo, Tipo → SubType o → Detalle).

|  |  |
| --- | --- |
| **Propiedad** | **Descripción** |
| Base | Grupo de perspectivas personalizado con campos ordenados |
| Navegación | Estructura de árbol desplegable |
| Selección | La selección del elemento principal filtra los valores secundarios |
| Para usar con | Compatible con cortadoras compactas |

**Cuándo utilizarlo:** jerarquías geográficas, estructuras organizativas, taxonomías de productos y cualquier clasificación de varios niveles.

**Cortadora compacta**

Combina varios filtros en una interfaz desplegable que ahorra espacio. Disponible en dos versiones:

**Cortadora compacta local**

- Utiliza tanto campos bloqueados como desbloqueados
- Las selecciones no se guardan entre sesiones
- Se aplica igual que los filtros estándar (ámbito de informe o de grupo)

**Cortadora Global Compact**

- Solo se pueden incluir los campos vinculados a un objeto
- Las selecciones del usuario se mantienen entre sesiones y al cerrar y abrir sesión
- Los cambios se aplican a todos los informes que contengan el mismo filtro «Global Compact»
- Sustitución recomendada para los filtros globales heredados

Consejo: Utiliza segmentadores compactos globales en lugar de filtros globales siempre que sea posible. Ofrecen una mejor experiencia de usuario y ajustes de filtro permanentes.

**Tipos de filtros y configuración**

**Filtros a nivel de componente (Área de filtros)**

Los filtros añadidos al área «Filtros» del panel «Configuración de componentes» restringen los datos antes de que lleguen a la tabla o al gráfico.

**Pasos de configuración:**

1. Arrastra un campo desde una perspectiva al área de filtros
2. Haz clic con el botón derecho del ratón en el campo y selecciona «Editar filtro»
3. Selecciona los valores que deseas incluir o excluir
4. Haz clic en «Aceptar» para aplicar los cambios

**Opciones del cuadro de diálogo de filtro:**

|  |  |
| --- | --- |
| **Opción** | **Descripción** |
| Selección de valores | Marca o desmarca los valores específicos que desees incluir |
| Añadir filtro personalizado | Introduce valores de filtro personalizados que no figuren en la lista |
| Valores que no se muestran actualmente | Incluir los valores que superen el límite de visualización de 1.000 value1,000-value |
| Cuadro de búsqueda con filtro | Buscar valores concretos cuando la lista es extensa |

**Nota:** Si hay más de 1.000 valores para un campo de filtro, utilice el cuadro de búsqueda «Filtro» para encontrar valores adicionales.

**Filtro de búsqueda automática (filtrado dentro de la tabla)**

Las tablas permiten filtrar directamente en la página mediante los campos de búsqueda situados debajo de los encabezados de las columnas.

**Operadores de búsqueda:**

|  |  |  |  |
| --- | --- | --- | --- |
| **Operador** | **Columna de números** | **Columna de texto** | **Descripción** |
| Texto | Nee | Sí | Buscar filas que contengan el texto |
| !texto | Nee | Sí | Buscar filas que NO contengan el texto |
| = | Sí | Sí | Coincidencia exacta (distingue entre mayúsculas y minúsculas en el texto) |
| > < >= <= != | Sí | Nee | Comparaciones numéricas |
| BLANK | Sí | Sí | Buscar celdas vacías |
| !BLANK | Sí | Sí | Buscar celdas que no estén vacías |
| && | Sí | Sí | Lógica «Y» (por ejemplo, «Guardar» Y «Maestro») |
| || | Sí | Sí | Lógica OR (por ejemplo, Save || Master) |

Nota: Puedes utilizar varios operadores && o varios operadores || en una búsqueda, pero no puedes combinar ambos operadores en la misma búsqueda.

**Tema principal:** [Componentes de los informes: Filtros y segmentadores](../../../../studio/new-uc/reference/report-studio-reference/report-component-filters-slicers.html)
