---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Opciones de filtrado"
breadcrumb:
  - "TBM Studio"
  - "Referencia"
  - "Referencia de Report Studio"
  - "Componentes del informe: Tablas"
source_path: "studio/new-uc/reference/report-studio-reference/filtering-options.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Opciones de filtrado

Las tablas se pueden filtrar para mostrar solo las filas que cumplan criterios específicos. Los filtros se configuran en la sección «Filtros» del panel «Configuración de componentes».

**Añadir filtros**

1. Arrastra un campo desde el Explorador de proyectos hasta el área de Filtros.
2. Haz clic con el botón derecho del ratón en el filtro y selecciona «Editar filtro».
3. Selecciona valores o configura los criterios de filtrado.

**Operadores de filtro**

|  |  |  |
| --- | --- | --- |
| **Operador** | **Descripción** | **Ejemplo** |
| Igual que | Coincidencia exacta. | El tipo de gasto es « OpEx » |
| No igual | Excluye las filas coincidentes. | El tipo de gasto no es igual a « CapEx » |
| Contiene | El valor incluye el texto especificado. | La cuenta contiene 2111 |
| No contiene | El valor no incluye el texto indicado. | Descripción: No contiene pruebas |
| Empieza por | El valor comienza con el texto indicado. | La cuenta empieza por ACCT |
| Termina por | El valor termina con el texto especificado. | Descripción: Servicios |
| Está en | El valor coincide con cualquiera de los elementos de la lista separados por comas. | La cuenta está en 2111, 2112, 2113 |
| No está en | El valor no coincide con ninguno de los de la lista. | El tipo no está en la prueba ni en la demostración |
| Es nulo | El valor está vacío. | La categoría es nula |
| No es nulo | El valor no está vacío. | La categoría no es nula |
| > (Mayor que) | Valor numérico superior al especificado (solo numérico). | Coste > 10 000 |
| < (menor que) | Valor numérico inferior al especificado (solo numérico). | Equivalente a tiempo completo < 5 |

**Función de búsqueda automática**

Activa los campos de búsqueda debajo de cada encabezado de columna para permitir a los usuarios aplicar filtros.

**Para activar la búsqueda automática:**

1. Haz clic con el botón derecho del ratón en la tabla y selecciona «Propiedades».
2. En la pestaña «Datos», activa la opción «Búsqueda automática».
3. Pulse Aceptar. Los campos de búsqueda aparecen debajo de los encabezados de las columnas.

**Tema principal:** [Componentes del informe: Tablas](../../../../studio/new-uc/reference/report-studio-reference/report-component-table.html)
