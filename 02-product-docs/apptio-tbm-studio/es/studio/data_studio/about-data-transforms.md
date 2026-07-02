---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Adquisición y transformación de datos"
breadcrumb: []
source_path: "studio/data_studio/about-data-transforms.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Adquisición y transformación de datos

**Se aplica a** : TBM Studio 12.0 y posteriores

## Acerca del proceso de transformación de tablas

Para modificar los datos de una tabla, puede añadir o modificar pasos en la cadena de transformación. En proyecto, puedes:

- Ver todos los pasos de transformación en el orden en que se ejecutan.
- Añada, edite y elimine pasos de transformación para modificar la salida.
- Arrastre para reordenar los pasos individuales.
- Navegue por los vídeos de la [comunidad Apptio](https://community.apptio.com/communities/community-home/librarydocuments/viewdocument?DocumentKey=c7ec37da-b3ef-41af-9671-3039095fa2a9 "(se abre en una pestaña o una ventana nueva)") (el enlace requiere credenciales de TBM Connect).

Nota: Las tablas editables no son transformaciones de tablas y no se tratan en este artículo. Para más información, consulte [Tablas editables: Adaptación de las entradas del usuario](editabletables.htm "(se abre en una pestaña o una ventana nueva)").

## Pasos del proceso de transformación de tablas

Al crear una nueva tabla, los siguientes pasos del pipeline se rellenarán automáticamente independientemente de la fuente de los datos:

- **Fuente** : Determina el tipo de datos en los que se basará una tabla.
- **Tabla** : Previsualiza la tabla de datos creada por la transformación.

En función de la opción Fuente seleccionada, se añadirán automáticamente otros pasos del pipeline:

Opciones de fuente de carga de archivos:

- **Cargar** : Permite al usuario seleccionar el archivo a subir.
- **Importar** : Muestra la configuración utilizada para definir cómo el sistema debe importar un archivo.

Opción de fuente de tabla existente:

- **Tabla existente** : Define la transformación de la tabla en la que debe basarse la tabla.

Puede añadir los siguientes pasos de canalización a cualquier tabla:

- **Añadir** : Añade las filas de una tabla a las filas de otra tabla. Véase [Añadir datos](append-data.htm "(se abre en una pestaña o una ventana nueva)").
- **Asignar filas** : Se añaden automáticamente al utilizar Asignar columnas para asignar a conjuntos de datos maestros con capacidades de aprendizaje automático y se pueden volver a añadir a tablas válidas mediante el proceso Añadir paso. Utiliza el aprendizaje automático y las reglas creadas por el usuario para asignar conceptos a ATUM. Véase [Asignar grupos de costes con aprendizaje automático](assigncostpools.htm "(se abre en una pestaña o una ventana nueva)").
- **Partición** de fechas Utilice las fechas del archivo, ya sea en filas o columnas, para distribuir automáticamente los datos en periodos de tiempo. Véase [Partición de datos por fecha](partition-data-by-date.htm "(se abre en una pestaña o una ventana nueva)").
- **Filtrar** : Elimine filas específicas en función de los valores de una o varias columnas.
- **Aplanar jerarquía** : Proporciona la mayor flexibilidad al utilizar rebanadoras. Este paso del pipeline añade a una tabla una columna por cada nivel de la jerarquía. A continuación, puede crear rebanadoras para cada una de las columnas. Véase [Aplanar una jerarquía de datos](flatten-hierarchy.htm "(se abre en una pestaña o una ventana nueva)").
- **Fórmulas** : Añade nuevas columnas de fórmulas basadas en datos, cambia los tipos de columna (por ejemplo, cambia un número por una etiqueta) o anula los valores existentes. Véase [Añadir y editar columnas](add-edit-columns.htm "(se abre en una pestaña o una ventana nueva)") y [Fórmulas y funciones](../formulas-and-functions/introduction-to-formulas-and-functions.htm "(se abre en una pestaña o una ventana nueva)").
- **Agrupar** : Agrupa la tabla por los valores de una o varias columnas de texto.
- **Ocultar y renombrar** : oculta o renombra columnas de los datos.
- **Unir** : Combinar datos de dos o más tablas en las mismas filas basándose en valores comunes en una o más columnas. Ver [datos de Join](join-data.htm "(se abre en una pestaña o una ventana nueva)").
- **Asignar columnas** : Conforma la salida de la tabla para que coincida con el esquema de ATUM y añade las filas al conjunto de datos maestros. Véase [Columnas del mapa](mapcolumns.htm "(se abre en una pestaña o una ventana nueva)").
- **Modelo** : Permite utilizar la tabla como un objeto en un modelo en el que los usuarios pueden definir controladores y asignar valores. Ver [Acerca de los modelos](../model%20studio/about-models.htm "(se abre en una pestaña o una ventana nueva)").
- **Pivotar** : Convierte filas en columnas. Véase [Datos pivotantes](pivot-tables.htm "(se abre en una pestaña o una ventana nueva)").
- **Eliminar duplicados** : Filtra las filas de una tabla que tienen el mismo valor en una columna o conjunto de columnas.
- **Seguridad a nivel de fila** : Permite a los usuarios filtrar tablas e informes en función del usuario actual. Véase [Aplicar seguridad a nivel de filas](apply-row-level-security.html "(se abre en una pestaña o una ventana nueva)").
- **Unpivotar** : Convertir columnas en filas.
