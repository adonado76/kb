---
source_system: "apptio-tbm-studio"
practice: "tbm"
language: "es"
doc_type: "studio"
title: "Añadir componentes editables a los informes"
breadcrumb:
  - "TBM Studio"
  - "Guías prácticas (basadas en tareas)"
  - "Crear informes"
  - "Informes avanzados"
source_path: "studio/new-uc/howtoguides/create-reports/add-et-rep.html"
images: []
capability_ids: []
last_updated: "2026-06-18"
summary: ""
---
# Añadir componentes editables a los informes

**Objetivo:** Incorporar tablas editables en los informes para habilitar flujos de trabajo de introducción de datos por parte del usuario final, de modo que los usuarios puedan introducir o modificar datos directamente desde la interfaz del informe sin necesidad de acceder a TBM Studio.

**Cuándo utilizarlo:** Cuando los usuarios necesiten introducir o actualizar datos como asignaciones de mano de obra, atributos de centros de coste, partidas presupuestarias o explicaciones de desviaciones.

**Tiempo estimado:** 15-25 minutos

## Comprensión de los componentes editables

Las tablas editables de los informes crean una capa de introducción de datos que alimenta las tablas de transformación de TBM Studio y, en última instancia, el modelo de costes. Admiten situaciones como:

- Asignaciones de personal (asignación de personal a soluciones, categorías o grupos de costes)
- Atributos de los centros de coste (añadir metadatos o clasificaciones)
- Explicaciones de las desviaciones presupuestarias (incluyendo los comentarios de los responsables de los centros de coste)
- Correcciones directas de los datos (que permiten realizar modificaciones controladas en los datos de origen)

**Requisitos previos**

- Una tabla editable ya existente creada en Data Studio (consulte la sección 3.1.3 para saber cómo crear tablas editables)
- Un informe para añadir el componente editable a
- Permisos adecuados (los usuarios necesitan acceso a Dev y a Stage para publicar los cambios)

## Pasos

**Paso 1: Añade el componente de tabla editable**

1. Abre el informe de destino en Report Studio y échale un vistazo.
2. En la pestaña Informe, haz clic en Tabla editable. Se añade un componente de tabla editable al informe y se abre el panel de configuración de componentes.
3. En el menú desplegable de selección de tablas situado en la parte superior del panel «Configuración de componentes», selecciona la tabla editable que desees mostrar.

**Paso 2: Configurar las columnas visibles**

1. Arrastra las columnas desde el Explorador de proyectos hasta el área «Columnas incluidas» del panel «Configuración de componentes».
2. Organiza las columnas en el orden de visualización que desees arrastrándolas hacia arriba o hacia abajo en la lista.
3. Las columnas que no se han incluido siguen estando disponibles en la tabla editable, pero no se muestran en la vista del informe.

Consejo: Muestra solo las columnas que los usuarios necesitan ver y editar. Las columnas ocultas conservan sus datos y no se ven afectadas por las modificaciones que el usuario realice en las columnas visibles.

**Paso 3: Configurar el comportamiento de edición**

1. Haz clic con el botón derecho del ratón en el componente de tabla editable y selecciona «Propiedades».
2. En la pestaña «Edición de datos», configura:
   - **Habilitar la adición de filas:** permite a los usuarios añadir nuevas filas (en tablas editables en blanco)
   - **Habilitar la eliminación de filas:** permite a los usuarios eliminar filas (solo en tablas editables en blanco)
   - **Habilitar duplicación de filas:** permite a los usuarios duplicar filas existentes
   - **Habilitar el arrastre:** copia automáticamente los valores numéricos al pasar de una celda a otra con la tecla Tab
3. Haz clic en Aceptar para guardar la configuración.

**Paso 4: Añadir la función de carga de archivos (opcional)**

Para que los usuarios puedan cargar datos a través de Excel:

1. Desplázate hasta la parte inferior del componente de tabla editable del informe.
2. Las opciones «Abrir en Excel» y «Hacer clic o arrastrar el archivo» aparecen automáticamente para los componentes de tabla editables.
3. Los usuarios pueden descargar los datos actuales a Excel, realizar cambios y volver a cargar el archivo modificado.

**Paso 5: Guardar y registrar**

1. Coloca y ajusta el tamaño del componente de tabla editable según sea necesario.
2. Guarda y revisa el informe.

## Flujo de trabajo del usuario para la introducción de datos

Una vez que hayas configurado un componente editable, los usuarios finales seguirán este flujo de trabajo:

1. Ve al informe que contiene la tabla editable.
2. Haz clic en las celdas para editar los valores directamente. Las columnas desplegables muestran los valores permitidos.
3. Haz clic en «Guardar» para guardar los cambios localmente (los cambios se almacenan en el dispositivo del usuario hasta que se publiquen).
4. Haz clic en «Publicar» en la parte inferior del informe para aplicar los cambios a la tabla de transformación subyacente.
5. Introduce una descripción y haz clic en «Publicar» para completar la publicación.

Advertencia: Al publicar se guardan TODAS las modificaciones pendientes de toda la tabla editable, no solo las filas filtradas que se ven en pantalla. Si la seguridad a nivel de fila está activada, los usuarios solo pueden ver y editar las filas para las que tienen autorización, pero las filas ocultas se conservan durante la publicación.

## Columnas especiales para el seguimiento de auditorías

Las tablas editables incluyen columnas especiales de auditoría que puedes mostrar u ocultar:

- **Columna.pk:** la columna de clave principal. Muestra esto para permitir operaciones de copiar y pegar y ordenar de forma coherente.
- **Columna «Nombre de usuario»:** muestra quién realizó la última modificación en cada fila.
- **.EditDate columna:** Muestra cuándo se realizó la última modificación en cada fila.

Para mostrar estas columnas: pasa el cursor por encima del encabezado de la columna, haz clic con el botón derecho del ratón y selecciona «Mostrar» en el menú.

## Concurrencia y bloqueo

Las tablas editables aplican un bloqueo a nivel de celda para evitar conflictos:

- Cuando un usuario empieza a editar una celda, esta se bloquea para los demás usuarios
- El bloqueo se mantiene hasta que el usuario guarde o cancele
- Otros usuarios pueden editar diferentes celdas de la misma tabla al mismo tiempo

## Resultados previstos

- Las celdas editables se resaltan cuando los usuarios hacen clic en ellas
- Las columnas desplegables muestran los valores permitidos configurados
- Los errores de validación se muestran como advertencias o errores junto a las celdas afectadas
- Los botones «Guardar» y «Publicar» aparecen en la parte inferior del componente

## Errores habituales

- **Los usuarios no pueden añadir ni eliminar filas:** solo las tablas editables en blanco permiten añadir y eliminar filas. Las tablas editables enriquecidas (derivadas de tablas de transformación) no permiten eliminar filas, ya que estas proceden de la transformación de origen.
- **Los cambios no se reflejan en el modelo:** los usuarios deben publicar los cambios, no basta con guardarlos. Los cambios guardados solo se aplican en el lado del cliente hasta que se publiquen.
- **Errores de validación que impiden la publicación:** las filas no válidas no se pueden publicar. Los usuarios deben corregir los errores de validación antes de que se pueda completar la publicación.

## Tareas relacionadas

- Crear tablas editables (Sección 3.1.3 )
- Configurar listas desplegables para columnas editables (Sección 3.1.3 )
- Configurar programaciones de publicación periódicas (Sección 6.1 )
- Configurar la seguridad a nivel de fila (Sección 4.4 )

**Tema principal:** [Informes avanzados](../../../../studio/new-uc/howtoguides/create-reports/adv-rep.html)
