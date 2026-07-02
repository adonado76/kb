---
source_system: "cloudability-premium"
practice: "finops"
language: "es"
doc_type: "admin"
title: "Organizar los datos mediante asignaciones empresariales jerárquicas"
breadcrumb:
  - "Cloudability Premium"
  - "Configuración"
  - "Organiza tus gastos en la nube"
  - "Cartografía empresarial"
source_path: "admin/hierarchical-business-mapping.html"
images:
  - "images/hier-business-mapping-create-add-layer.png"
  - "images/hier-business-mapping-create-add-layer2.png"
  - "images/hier-business-mapping-create-add-name-layer.png"
  - "images/hier-business-mapping-create-name.png"
  - "images/hier-business-mapping-create-start.png"
  - "images/hier-business-mapping-create-upload-mapping.png"
  - "images/hier-business-mapping-listing.png"
  - "images/hier-business-mapping-upload-rev.png"
capability_ids: []
last_updated: "2026-06-29"
summary: ""
---
# Organizar los datos mediante asignaciones empresariales jerárquicas

Nota:

Las asignaciones jerárquicas de negocios tienen actualmente un límite de 1000 filas de asignaciones de negocios.

Un Mapeo Jerárquico de Negocio es una forma especializada de Mapeo de Negocio diseñada para crear y mantener relaciones jerárquicas de datos entre Dimensiones de Negocio (hasta cinco). Las dimensiones de negocio son dimensiones sintéticas generadas utilizando lógica de negocio (declaraciones de mapeo de negocio) para asignar etiquetas específicas de la nube y del proveedor a conceptos de negocio significativos.

Una Asignación Jerárquica de Negocio (HBM) le permite crear un conjunto relacionado de Dimensiones de Negocio que pueden soportar rollups de costes en Cloudability Reporting, View Filters y Plans. Este enfoque simplifica la creación y el mantenimiento de la lógica empresarial necesaria para mantener sincronizadas las Dimensiones Empresariales relacionadas.

## ¿Cómo funciona?

Imagine que necesita informar sobre los costes en diferentes niveles de propiedad de costes dentro de su organización: Equipo, Departamento y Grupo. Usted desea una Dimensión de Negocio para cada nivel y típicamente necesitaría crear Mapeos de Negocio separados para cada uno. Sin embargo, estas dimensiones siguen una estructura jerárquica: los equipos dan paso a los departamentos, que a su vez dan paso a los grupos.

Para definir estas relaciones usando Mapeos de Negocio estándar, usted necesitaría crear declaraciones especificando cómo cada Equipo se mapea a un Departamento y cómo cada Departamento se mapea a un Grupo. Aunque este enfoque puede funcionar para un pequeño número de equipos, departamentos y grupos, resulta difícil de gestionar a gran escala, especialmente cuando las relaciones de rollup cambian con el tiempo (por ejemplo, se añaden nuevos equipos o departamentos, o se reorganizan las estructuras de informes).

Un Mapeo Jerárquico de Negocio (HBM) simplifica este proceso permitiéndole definir un único Mapeo de Negocio que se aplica a múltiples Dimensiones de Negocio en una jerarquía de rollup estructurada. En lugar de definir manualmente cada uno de los Business Mappings utilizando una lógica compleja e interdependiente de estilo IF-THEN, puede crear toda la jerarquía utilizando un sencillo enfoque declarativo:

1. Seleccione una Dimensión de Negocio para utilizarla como base de su jerarquía (por ejemplo, Equipo).
2. Especifique los niveles jerárquicos adicionales que desee (por ejemplo, Departamento y Grupo).
3. Cargue un archivo de asignación que especifique cómo se relacionan los valores de cada nivel con su nivel superior.

Cloudability genera automáticamente nuevas Business Dimensions y Business Mapping statements para cada nivel jerárquico. Si las relaciones de rollup cambian, como la adición o eliminación de Departamentos o Grupos, sólo tiene que cargar un nuevo archivo de asignación y el sistema actualizará todas las declaraciones de Business Mapping en consecuencia. Esto asegura que los valores correctos de Equipo, Departamento y Grupo se asignen de forma consistente para garantizar rollups de costes precisos.

Adicionalmente, el Mapeo Jerárquico de Negocios puede ser utilizado para crear Vistas que se alineen con la estructura de rollup de costos de HBM. Consulte [Organizar vistas mediante vistas jerárquicas](hierarchical-views.html) para obtener más información.

## ¿Qué es un fichero cartográfico?

Un archivo de asignación es una forma estructurada de definir cómo los valores de cada nivel de Asignación jerárquica de empresas (HBM) se transfieren a su nivel superior. Es una tabla (archivo CSV ), en la que:

- La columna de la izquierda representa la dimensión base.
- Cada columna siguiente representa un nivel superior en la jerarquía.
- Cada fila define cómo se asigna un valor de la dimensión base a sus niveles superiores.

Por ejemplo, la siguiente tabla muestra un archivo de asignación para un HBM en el que Equipo es la dimensión base, que se desglosa en Departamento y después en Grupo. Hay 10 Equipos (del Equipo 1 al Equipo 10), y cada fila especifica cómo se asigna un Equipo a su correspondiente Departamento y Grupo.

| Equipo | Departamento | Grupo |
| --- | --- | --- |
| Equipo 1 | Departamento A | Grupo X |
| Equipo 2 | Departamento D | Grupo Y |
| Equipo 3 | Departamento B | Grupo X |
| Equipo 4 | Departamento A | Grupo X |
| Equipo 5 | Departamento C | Grupo Y |
| Equipo 6 | Departamento B | Grupo X |
| Equipo 7 | Departamento C | Grupo Y |
| Equipo 8 | Departamento D | Grupo Y |
| Equipo 9 | Departamento B | Grupo X |
| Equipo 10 | Departamento C | Grupo Y |

A título ilustrativo, he aquí la misma tabla pero reformateada para resaltar las relaciones jerárquicas entre Equipos, Departamentos y Grupos. Este formato facilita ver cómo los Grupos se componen de varios Departamentos y, a su vez, cómo cada Departamento contiene Equipos específicos.

| Equipo | Departamento | Grupo |
| --- | --- | --- |
| Equipo 1 | Departamento A | Grupo X |
| Equipo 4 |
| Equipo 3 | Departamento B |
| Equipo 6 |
| Equipo 9 |
| Equipo 5 | Departamento C | Grupo Y |
| Equipo 7 |
| Equipo 10 |
| Equipo 2 | Departamento D |
| Equipo 8 |

En este archivo de asignación de ejemplo:

- El grupo X incluye los departamentos A y B :
  - El Departamento A está formado por el Equipo 1 y el Equipo 4.
  - El Departamento B está formado por el Equipo 3, el Equipo 6 y el Equipo 9.
- El grupo Y incluye los departamentos C y D :
  - El Departamento C está formado por el Equipo 5, el Equipo 7 y el Equipo 10.
  - El Departamento D está formado por el Equipo 2 y el Equipo 8.

## Conceptos de dimensión empresarial jerárquica (HBM)

Nombre

El nombre de la jerarquía general. Este atributo es obligatorio. Elija un nombre que transmita claramente su estructura o propósito general, ya que aparecerá como el nodo raíz de la jerarquía, es decir, el nombre de la Vista de nivel superior si crea una estructura de Vista jerárquica para el HBM.

Dimensión de la base

Cada jerarquía se construye sobre una dimensión empresarial base. Debe ser una dimensión empresarial existente y no puede ser una dimensión utilizada en otro HBM.

Capas jerárquicas

Capas jerárquicas adicionales (enrollables). Cada capa debe tener un nombre, y ese nombre debe ser único (no puede ser el nombre de una dimensión empresarial existente). Éstas se generarán como nuevas dimensiones empresariales una vez completada la configuración de HBM.

## Cómo configurar asignaciones jerárquicas de empresas

Enumerar y revisar las dimensiones jerárquicas de la empresa

En la página de inicio de Business Mappings, en la pestaña Dimensiones jerárquicas, puede ver una lista de todas las dimensiones jerárquicas de negocio que ha configurado.

![nueva dimensión empresarial captura de pantalla](../../../../03-media/cloudability-premium/images/hier-business-mapping-listing.png)

Creación de dimensiones empresariales jerárquicas

Para crear una nueva dimensión empresarial jerárquica:

1. En la pestaña Dimensiones Jerárquicas, seleccione Nueva Jerarquía de Dimensión de Negocio del menú Añadir.
2. Se abrirá el cajón Crear jerarquía de cotas en el paso Visión general > Seleccione Siguiente para avanzar al siguiente paso (Definir capas ).

   ![crear pantalla de jerarquía de dimensiones](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-start.png)
3. Dé un nombre a la jerarquía > escriba el nombre deseado (por ejemplo, Cost Org ) en el campo Hierarchy Name.

   ![coste org BD captura de pantalla](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-name.png)

   Nota:

   El nombre de la jerarquía se utiliza como nombre de la Vista raíz su correspondiente Vista jerárquica. Consulte [Organizar vistas mediante vistas jerárquicas](hierarchical-views.html) para obtener más información.
4. Seleccione una dimensión empresarial existente como base de la jerarquía > Haga clic en el desplegable Seleccionar la dimensión base y elija una dimensión de la lista (por ejemplo, Equipo ).

   ![captura de pantalla de la dimensión base](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-add-layer.png)

   Nota:

   Debe seleccionar una cota base antes de poder añadir capas jerárquicas.
5. Añada capas adicionales a la jerarquía > haga clic en el botón Añadir capa jerárquica e introduzca el nombre de la dimensión deseada (por ejemplo, Departamento ) en el modal que aparece. Haz clic en Añadir.

   ![añadir capa jerárquica captura de pantalla](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-add-name-layer.png)

   Nota:

   El valor por defecto no se utiliza y puede ignorarse.
6. Repita el paso 5 para añadir más capas jerárquicas. Puede añadir hasta un total de cuatro (4) capas sobre la dimensión base. Haga clic en Siguiente para terminar de añadir capas y avanzar al siguiente paso (Importar valores ).

   ![crear captura de pantalla DH](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-add-layer2.png)
7. Sube un archivo de asignación que describa cómo se asignan los valores de las dimensiones base a los valores del nivel superior > haz clic en «Examinar» para buscar un archivo o arrastra y suelta un archivo « CSV » en el cuadro de importación. Haga clic en Importar para importar el archivo de asignación y crear el HBM.

   ![explorar dimensión captura de pantalla](../../../../03-media/cloudability-premium/images/hier-business-mapping-create-upload-mapping.png)

   Nota:

   Al hacer clic en el enlace «Exportar la plantilla de la dimensión base» ( CSV ), se descargará un archivo de plantilla de la dimensión base ( CSV ) que ya contiene los valores actuales de la dimensión base, listo para completar con los valores de la dimensión principal.

Edición de dimensiones empresariales jerárquicas

Para modificar una asignación empresarial jerárquica existente:

1. Seleccione la opción Editar Mapeo de Negocio del menú Opciones (engranaje). Esto abrirá el cajón Editar Jerarquía de Dimensiones en el paso Importar Valores.
2. Cambie el nombre de la dimensión empresarial jerárquica > haga clic en «Siguiente» para actualizar.
3. Sube un archivo de mapeo revisado > haz clic en «Examinar» para buscar un archivo o arrastra y suelta un archivo. CSV en el cuadro de importación. Haga clic en Actualizar para importar el archivo de asignación y actualizar el HBM con las nuevas asignaciones.

   ![editar pantalla de dimensión empresarial](../../../../03-media/cloudability-premium/images/hier-business-mapping-upload-rev.png)

   Nota:

   Cualquier vista jerárquica asociada se actualizará automáticamente para reflejar los cambios en la asignación revisada.

   Para más información, consulte [Organizar vistas mediante vistas jerárquicas.](hierarchical-views.html)

Supresión de dimensiones empresariales jerárquicas

Para eliminar una asignación jerárquica de empresa existente, seleccione la opción Eliminar asignación de empresa del menú Opciones (engranaje). Esto eliminará la asignación empresarial jerárquica del sistema y borrará las dimensiones empresariales de nivel HBM, pero no la dimensión empresarial base.

Nota:

Antes de eliminar un HBM, como práctica recomendada, debería eliminar primero su Vista jerárquica asociada.

Para más información, consulte [Organizar vistas mediante vistas jerárquicas.](hierarchical-views.html)

**Tema principal:** [Cartografía empresarial](../admin/business-tags.html)
